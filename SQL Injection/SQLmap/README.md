O **SQLmap** é a ferramenta de "canivete suíço" para testes de penetração focados em bancos de dados. Ele é uma ferramenta *open-source* (código aberto) escrita em Python que automatiza o processo de detectar e explorar falhas de **SQL Injection (SQLi)**.

Em termos simples: **ele faz o "trabalho sujo" e repetitivo de testar milhares de combinações de códigos maliciosos até encontrar uma brecha no banco de dados.**

Aqui está exatamente o que ele faz, dividido por funções:

### 1. Detecção Automática (Fingerprinting)

Antes de atacar, ele precisa saber com quem está lidando. O SQLmap analisa a URL ou o formulário alvo para descobrir:

* **Qual é o Banco de Dados:** (MySQL, PostgreSQL, Oracle, Microsoft SQL Server, etc.).
* **Qual é o Sistema Operacional:** (Linux, Windows).
* **Qual é a Tecnologia Web:** (PHP, ASP.NET, Java, etc.).

### 2. Exploração de Vulnerabilidades (The Attack)

Uma vez que ele sabe o alvo, ele testa várias técnicas de injeção automaticamente:

* **Boolean-based blind:** Faz perguntas de "Verdadeiro ou Falso" ao banco para adivinhar dados letra por letra.
* **Time-based blind:** Manda o banco "dormir" (pausar) por 10 segundos. Se o site demorar 10 segundos para carregar, a falha existe.
* **Error-based:** Força o banco a gerar um erro que revela informações sobre sua estrutura.
* **UNION query:** Usa o operador `UNION` para combinar resultados de duas tabelas e extrair dados extras.

### 3. Extração de Dados (The Loot)

Se ele encontrar uma falha, você pode usar comandos simples para "saquear" o banco:

* `--dbs`: Lista todos os bancos de dados no servidor.
* `--tables`: Lista as tabelas de um banco específico.
* `--columns`: Lista as colunas de uma tabela (ex: `users`).
* `--dump`: **Baixa todos os dados** da tabela (usuários, senhas, e-mails).

### 4. Quebra de Senhas (Cracking)

Se o SQLmap baixar senhas que estão criptografadas (hashes), ele tem um recurso integrado para tentar quebrá-las usando um ataque de dicionário, revelando a senha real.

### 5. Acesso ao Sistema (Takeover)

Em casos críticos (geralmente quando o banco roda como administrador/root), o SQLmap consegue:

* Ler e escrever arquivos no servidor (`--file-read`, `--file-write`).
* Abrir um **terminal de comando (OS Shell)** no servidor da vítima, permitindo controle total da máquina.

---

### Exemplo Prático de Uso (Educativo)

Imagine que você tem permissão para testar o site: `http://site-teste.com/produto.php?id=1`

1. **Checar se é vulnerável:**
```bash
sqlmap -u "http://site-teste.com/produto.php?id=1"

```


2. **Listar os bancos de dados:**
```bash
sqlmap -u "http://site-teste.com/produto.php?id=1" --dbs

```


3. **Baixar a tabela de usuários:**
```bash
sqlmap -u "http://site-teste.com/produto.php?id=1" -D loja -T usuarios --dump

```



### Resumo para o seu Portfólio/Artigo

Se você for citar o SQLmap, use esta definição profissional:

> *"O SQLmap é uma ferramenta de teste de penetração que automatiza a detecção e exploração de falhas de injeção SQL e a tomada de controle de servidores de banco de dados. Ele suporta uma ampla gama de bancos de dados e técnicas de injeção, sendo essencial para validar a segurança de aplicações web contra roubo de dados."*