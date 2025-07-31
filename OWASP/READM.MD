Se você **descobre a rota de acesso para logs** (ex: `/support/logs`) e consegue acessar **informações sensíveis** como:

* Stack traces
* Erros detalhados
* Logs de requisições com dados de usuários, tokens, senhas, etc.

👉 Isso é considerado uma **Information Disclosure (Exposição de Informações Sensíveis)**.

No **OWASP Top 10**, ela pode se enquadrar em:

### 🔹 **A05:2021 – Security Misconfiguration**

Porque a aplicação **não restringiu o acesso** a uma rota administrativa (`/support/logs`) ou deixou **logs acessíveis publicamente**.

### 🔹 **A04:2021 – Insecure Design**

Se os logs **foram mal projetados** e expõem dados sensíveis (como senhas em texto puro ou tokens).

### 🔹 **A01:2021 – Broken Access Control**

Se **qualquer usuário** consegue acessar uma rota **que deveria ser restrita a admins ou devs**.

---

📌 **Resumo:**
Se você só descobre a rota → **Security Misconfiguration**
Se consegue acessar e ver dados → **Broken Access Control** + **Sensitive Data Exposure**