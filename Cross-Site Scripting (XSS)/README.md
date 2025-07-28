## Cross-Site Scripting (XSS)

**Cross-Site Scripting (XSS)** é uma vulnerabilidade de segurança comum em aplicações web que permite a um atacante injetar scripts maliciosos em páginas da web visualizadas por outros usuários. Diferente de outros tipos de ataques que visam o servidor, o XSS tem como alvo os usuários da aplicação, executando o código malicioso diretamente no navegador da vítima.

A falha ocorre quando uma aplicação web incorpora dados fornecidos por um usuário em sua página sem a devida validação ou codificação. Isso permite que um atacante insira código, geralmente em JavaScript, que será executado no contexto do site vulnerável.

### Como Funciona:

O mecanismo básico de um ataque XSS envolve três partes: o atacante, a vítima e a aplicação web vulnerável. O atacante injeta um script malicioso na aplicação. Quando a vítima acessa a página contaminada, o navegador executa o script como se fosse parte legítima do site, concedendo ao atacante acesso a informações sensíveis do usuário, como cookies de sessão, ou a capacidade de realizar ações em nome do usuário.

### Tipos Comuns de XSS:

Existem três tipos principais de ataques de Cross-Site Scripting:

* **XSS Refletido (Reflected XSS):** O script malicioso é injetado através de uma requisição HTTP, como um link malicioso enviado por e-mail ou mensagem. Quando a vítima clica no link, o script é "refletido" pela aplicação web e executado no navegador da vítima. Este é o tipo mais comum de XSS.

* **XSS Armazenado (Stored XSS):** O script malicioso é permanentemente armazenado nos servidores da aplicação, como em um comentário de fórum, um post de blog ou no perfil de um usuário. Toda vez que qualquer usuário visitar a página com o conteúdo malicioso, o script será executado. Este tipo é considerado o mais perigoso devido ao seu amplo alcance.

* **XSS Baseado em DOM (DOM-based XSS):** A vulnerabilidade reside no código do lado do cliente (client-side) da própria página. O ataque ocorre quando a aplicação manipula o Document Object Model (DOM) da página de forma insegura com base em dados fornecidos pelo usuário, permitindo a execução de um script malicioso sem que os dados sequer cheguem ao servidor.

### Impactos Potenciais:

Um ataque de XSS bem-sucedido pode levar a uma variedade de consequências negativas, incluindo:

* Roubo de cookies de sessão, permitindo que o atacante se passe pela vítima.
* Captura de credenciais de login.
* Redirecionamento de usuários para sites maliciosos.
* Modificação do conteúdo da página para enganar os usuários (defacement).
* Execução de ações indesejadas em nome do usuário.

A prevenção de XSS envolve práticas de programação segura, como a validação rigorosa de todas as entradas de usuário e a codificação de saídas para garantir que os dados sejam tratados como texto e não como código executável.