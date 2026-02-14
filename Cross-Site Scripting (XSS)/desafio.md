
### 🧠 Explicação dos Conceitos (Tópicos de Estudo)

Aqui está o que você precisa entender para resolver esses desafios:

#### 1. XSS (Cross-Site Scripting)

É uma vulnerabilidade onde o atacante consegue injetar scripts maliciosos (geralmente JavaScript) em páginas web vistas por outros usuários.

* **Reflected XSS (Refletido):** O script malicioso vem na requisição atual (ex: um link malicioso enviado por e-mail). O servidor "reflete" o script de volta para o navegador do usuário imediatamente.
* *No exercício:* "Can you see your reflection?" foca nisso. O objetivo é fazer o site "repetir" o que você digita, mas executando código.


* **Stored XSS (Armazenado):** O script malicioso é salvo permanentemente no servidor (ex: em um banco de dados, comentário de blog, perfil de usuário). Quando a vítima acessa a página, o script é carregado e executado. É mais perigoso que o refletido.
* *No exercício:* "Classic Stored XSS" e "Down with Uploads" abordam isso.



#### 2. Directory Traversal (Travessia de Diretório)

Uma falha que permite ao atacante acessar arquivos e diretórios que estão fora da pasta raiz da aplicação web.

* **Como funciona:** Usando caracteres como `../` (ponto-ponto-barra) para subir níveis de diretório e acessar arquivos sensíveis do sistema (como `/etc/passwd` no Linux).
* *No exercício:* Em "Down with Uploads", você provavelmente usará o nome do arquivo da imagem para tentar salvar o arquivo em um lugar onde não deveria, ou acessar arquivos indevidos.

#### 3. Uploads de Arquivos Maliciosos

Permitir que usuários enviem arquivos é arriscado.

* **O perigo:** Se o servidor não validar corretamente o tipo e o conteúdo do arquivo, um atacante pode enviar um script (ex: um arquivo `.php` ou `.html` com JS malicioso) disfarçado de imagem. Se o servidor executar esse arquivo ou mostrá-lo para outros usuários sem tratamento, o ataque ocorre.

#### 4. Sanitização e Angular

* **Sanitização:** É o processo de limpar a entrada do usuário para impedir que códigos maliciosos sejam interpretados pelo navegador. O Angular (um framework JavaScript) geralmente faz isso automaticamente.
* **O Desafio:** O exercício "Angular HTML and URL sanitization" sugere que há formas de *burlar* essa proteção automática do Angular, geralmente quando o desenvolvedor usa métodos inseguros propositalmente ou comete erros na manipulação de variáveis.

---

### 📚 Resumo para Estudo

Para se preparar para esses laboratórios, foque nestes pontos chave:

1. **Diferencie XSS:** Saiba explicar a diferença entre **Reflected** (o ataque está no link) e **Stored** (o ataque está salvo no site).
2. **Payloads Básicos:** Memorize *payloads* simples de teste como `<script>alert(1)</script>` ou `<img src=x onerror=alert(1)>`.
3. **Manipulação de Caminhos:** Entenda como o `../` funciona em sistemas de arquivos para o *Directory Traversal*.
4. **Bypass de Filtros:** Estude como atacantes disfarçam arquivos maliciosos (ex: mudando extensão, alterando cabeçalhos MIME) para fazer uploads proibidos.
5. **Contexto do Angular:** Pesquise sobre como o Angular trata HTML seguro (ex: `DomSanitizer`) e onde ele pode falhar se mal configurado.