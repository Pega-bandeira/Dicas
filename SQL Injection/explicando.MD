# Entendendo a Injeção de SQL (SQL Injection)

Este `README` é um guia de estudo completo sobre uma das vulnerabilidades de segurança mais comuns e destrutivas em aplicações web: a **Injeção de SQL (SQLi)**. O objetivo aqui é educacional, para que desenvolvedores e estudantes de segurança entendam a ameaça para poderem criar sistemas mais seguros.

## O que é SQL Injection? 🕵️

Imagine que você vai a uma repartição pública e precisa preencher um formulário para pedir um documento. O formulário tem um campo: "Seu Nome". Você escreve seu nome, e o funcionário pega essa informação, vai até um arquivo e busca sua pasta.

Agora, imagine que, em vez de escrever apenas seu nome, você escreve: *"Meu nome **E** traga também a pasta de todas as outras pessoas"*. Se o funcionário fosse um robô ingênuo que segue as instruções literalmente, ele faria exatamente isso, comprometendo a privacidade de todos.

**SQL Injection é exatamente isso.** É uma vulnerabilidade que permite a um invasor "injetar" comandos SQL maliciosos dentro de uma consulta que a aplicação já ia fazer ao banco de dados. Ao manipular a consulta original, o atacante pode forçar a aplicação a entregar informações que não deveria.

-----

## Por que é tão Perigoso? (O Impacto) 💥

Uma exploração bem-sucedida de SQLi pode ser catastrófica. O invasor pode:

  * **Roubar dados sensíveis:** Acessar informações de todos os usuários, senhas, números de cartão de crédito, dados pessoais, etc.
  * **Contornar autenticação:** Fazer login como qualquer usuário, incluindo administradores, sem precisar de senha.
  * **Alterar ou destruir dados:** Modificar saldos, apagar registros, ou deletar tabelas inteiras (`DROP TABLE`).
  * **Tomar controle do servidor:** Em algumas configurações, é possível executar comandos no sistema operacional do servidor de banco de dados, comprometendo toda a infraestrutura.

-----

## Como Funciona na Prática?

A causa raiz do SQLi é a **concatenação de strings para montar consultas SQL**, usando dados que vêm diretamente do usuário sem o devido tratamento.

### O Cenário Vulnerável

Veja um exemplo simples de código **vulnerável** em PHP que busca um usuário no banco de dados para fazer login:

```php
// CONEXÃO COM O BANCO DE DADOS (omitida por simplicidade)

// Pega os dados vindos de um formulário de login
$username = $_POST['username']; // Ex: 'admin'
$password = $_POST['password']; // Ex: 'senha123'

// CRIA A CONSULTA SQL CONCATENANDO AS STRINGS - AQUI MORA O PERIGO!
$sql = "SELECT id FROM users WHERE username = '$username' AND password = '$password'";

// Executa a consulta...
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Login bem-sucedido!
} else {
    // Falha no login.
}
```

### O Ataque

Um usuário normal preencheria o campo `username` com `admin`. A consulta ficaria:
`SELECT id FROM users WHERE username = 'admin' AND password = '...';`

Agora, um invasor insere o seguinte "payload" no campo `username`:
` ' OR '1'='1' --  `

E pode deixar a senha em branco. Veja o que acontece com a string `$sql` no código:

```sql
SELECT id FROM users WHERE username = '' OR '1'='1' -- ' AND password = ''
```

Vamos analisar a consulta manipulada:

  * `username = ''`: A primeira parte da condição é falsa.
  * `OR '1'='1'`: MAS, o operador `OR` faz com que a cláusula `WHERE` inteira seja verdadeira se qualquer um dos lados for verdadeiro. Como `'1'='1'` é **sempre verdade**, a condição é satisfeita.
  * ` --  `: Isso é um comentário em SQL. Todo o resto da linha é ignorado pelo banco de dados. A verificação da senha (`AND password = ...`) nunca acontece\!

**Resultado:** A consulta retorna o primeiro usuário da tabela (que muitas vezes é o administrador) e o sistema concede o acesso. O login foi contornado com sucesso.

-----

## Principais Tipos de SQL Injection

Existem várias formas de explorar essa falha. As principais são:

### 1\. In-band SQLi (Em Banda)

É o tipo mais comum. O invasor usa o mesmo canal de comunicação para lançar o ataque e obter os resultados diretamente na página.

  * **Baseado em Erro:** Força o banco a produzir uma mensagem de erro que revela informações sobre a estrutura do banco.
  * **Baseado em UNION:** Usa o operador `UNION` para combinar o resultado de uma consulta legítima com os dados de tabelas que o invasor quer acessar.

### 2\. Blind SQLi (Injeção Cega)

Ocorre quando a aplicação não mostra os dados nem erros na tela. O ataque é mais lento e funciona como um jogo de "quente ou frio".

  * **Booleano:** O invasor faz uma pergunta de "sim ou não" e observa se a página muda. Ex: *"O primeiro caractere do nome do banco de dados é 'a'?"*. Se a página carregar normalmente, a resposta é sim. Se der erro, é não.
  * **Baseado em Tempo:** O invasor faz o banco de dados esperar por um tempo específico se uma condição for verdadeira. Ex: *"Se o primeiro caractere da senha do admin for 's', espere 5 segundos"*. Se a página demorar 5 segundos a mais para carregar, a condição é verdadeira.

### 3\. Out-of-band SQLi (Fora de Banda)

É mais rara e complexa. É usada quando o servidor não retorna nenhuma resposta diferente. O invasor força o banco de dados a fazer uma conexão de rede para um servidor externo controlado por ele, enviando os dados por esse outro canal (ex: uma requisição DNS ou HTTP).

-----

## 🛡️ Como se Proteger: A Prevenção

Felizmente, proteger-se contra SQL Injection é relativamente simples se você seguir as boas práticas desde o início.

### A Regra de Ouro: Consultas Parametrizadas (Prepared Statements)

Essa é a forma **mais eficaz** de prevenção. Em vez de concatenar strings, você cria um "molde" da consulta com marcadores (`?` ou `:nome`) e envia os dados do usuário separadamente. O banco de dados trata os dados de entrada sempre como **dados**, nunca como parte do **código** SQL.

Veja o mesmo código de login, agora **seguro**, usando Prepared Statements em PHP:

```php
// Pega os dados vindos de um formulário de login
$username = $_POST['username'];
$password = $_POST['password'];

// 1. PREPARA O "MOLDE" DA CONSULTA com marcadores (?)
$stmt = $conn->prepare("SELECT id FROM users WHERE username = ? AND password = ?");

// 2. VINCULA os dados do usuário aos marcadores. O banco de dados garante que eles serão tratados apenas como texto.
$stmt->bind_param("ss", $username, $password); // "ss" significa que ambas as variáveis são strings

// 3. EXECUTA a consulta de forma segura
$stmt->execute();

$result = $stmt->get_result();

if ($result->num_rows > 0) {
    // Login bem-sucedido!
} else {
    // Falha no login.
}
```

Agora, se o invasor inserir ` ' OR '1'='1' --  ` no campo de usuário, o banco de dados irá procurar literalmente por um usuário com o nome bizarro ` ' OR '1'='1' --  ` e, como não encontrará, o login falhará. O ataque é neutralizado.

### Outras Camadas de Defesa

1.  **Validação de Entrada (Input Validation):** Sempre valide os dados de entrada. Se você espera um número, verifique se é um número. Se espera uma data, verifique o formato.
2.  **Sanitização de Entrada (Input Sanitization):** "Limpe" os dados, escapando caracteres especiais que têm significado em SQL (como `'`). Funções de Prepared Statements já fazem isso automaticamente.
3.  **Princípio do Menor Privilégio:** Crie um usuário no banco de dados para a sua aplicação que tenha apenas as permissões estritamente necessárias. Ele não precisa ter permissão para dar `DROP TABLE`, por exemplo.
