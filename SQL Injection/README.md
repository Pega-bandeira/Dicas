# **Domine o Banco de Dados – Guia Completo em Português**

## **Introdução**

**SQL Injection (SQLi)** é um tipo de ataque em que o usuário consegue executar consultas no banco de dados de um servidor quando a entrada fornecida pelo usuário não é devidamente validada.

É muito comum ver aplicativos ainda vulneráveis a SQLi, apesar dessa falha existir há décadas. Algumas pessoas chamam isso de **ataque Bobby Tables**.

Geralmente, o SQLi é mostrado apenas como uma forma de causar erros no servidor, mas em muitos casos ele pode ser usado para **obter informações sensíveis** diretamente do banco de dados.

Nesta lição, um aplicativo básico em **Node.js** exibe informações de funcionários com base em uma consulta de pesquisa.
Vamos usar **SQL Injection** para retornar informações sensíveis – **datas de nascimento e salários dos funcionários.**

---

## **1️⃣ Testando a funcionalidade esperada**

1. Clique em **"Search employees"** sem inserir nenhum nome de usuário ou senha.

   * Veja **quais conteúdos são retornados** e **qual o código de status** (deve ser 200).
   * Você deverá ver **resultados para dois funcionários**.

2. Digite **termos de pesquisa curtos** que incluam (ou não incluam) partes dos nomes dos dois funcionários para filtrar os resultados.

📌 **Resumo:** Clique em **"Search employees"** no aplicativo web para verificar o funcionamento normal.

---

## **2️⃣ Testando uma SQL Injection básica**

1. Digite **apenas um apóstrofo (`'`)** como termo de pesquisa.

   * O código de status deve ser **200**, mas sem resultados retornados.

2. Em casos simples, isso pode causar **erro no servidor**.
   Neste caso, não houve erro, mas **a consulta ainda pode ter sido interpretada no backend.**

3. Tente agora:

   ```
   '--
   ```

4. O resultado será **diferente do anterior**, o que sugere que **a SQL Injection pode ser possível.**

---

### 🔍 **Por que o resultado mudou?**

* **Com apenas `'`** → Geramos uma consulta inválida no backend:

  ```
  SELECT * FROM employees WHERE name LIKE '%'%'  
  ```

  O servidor não conseguiu executar e retornou **nenhum resultado**.

* **Com `'--`** → Geramos a consulta:

  ```
  SELECT * FROM employees WHERE name LIKE '%'--%'  
  ```

  Como `--` inicia um **comentário no SQLite**, o restante da consulta (`%'`) foi **ignorado**, retornando **todos os resultados**, já que `%` é um **coringa (wildcard)**.

📌 **Resumo:** Digite apenas `'` e verifique que nenhum resultado é retornado. Depois teste com `'--` e veja a diferença.

---

## **3️⃣ Retornando dados personalizados via SQLi**

Agora podemos usar a cláusula **UNION** para **trazer dados de outras colunas**.

### **Etapas:**

1. Precisamos adivinhar:
   ✅ **Nome da tabela** → `employees`
   ✅ **Nome de uma coluna válida** → `name`

2. Descobrir **quantas colunas a consulta original retorna**, pois o **UNION** precisa ter o mesmo número de colunas.

3. Como a tabela exibida tem **cinco colunas**, testamos:

```
' UNION ALL SELECT name, name, name, name, name FROM employees --
```

🔹 Isso deve **retornar duas novas linhas**, com os nomes dos funcionários **repetidos em todas as colunas.**

---

## **4️⃣ Retornando dados sensíveis via SQLi**

Agora podemos substituir os campos `name` por outros campos sensíveis, como **salário**.

Para retornar **os salários dos funcionários**, use:

```
' UNION ALL SELECT name, salary, salary, salary, salary FROM employees --
```

🔹 Isso exibirá **o nome e os salários** no resultado.

### 💡 **Dica:**

Tente variações para ver se consegue executar a injeção **sem precisar usar `--` para comentar o restante da consulta.**

---

## ✅ **Conclusão**

Aprendemos como:

✅ Testar o comportamento esperado da aplicação.
✅ Detectar a possibilidade de SQL Injection.
✅ Usar `UNION` para injetar consultas adicionais.
✅ Obter **dados sensíveis**, como **salários de funcionários**.
