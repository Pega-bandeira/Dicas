# Glossário de Cibersegurança

Este repositório contém um glossário de termos essenciais na área de cibersegurança, oferecendo definições claras e concisas para facilitar a compreensão de conceitos importantes. Seja você um estudante, profissional da área ou apenas alguém interessado em segurança digital, este glossário será uma ferramenta útil.

---

## Termos e Definições

Aqui estão os termos e suas respectivas definições, organizados em ordem alfabética para fácil consulta:

* **Autenticação de Dois Fatores (2FA):** Método de confirmação da identidade de um usuário, utilizando duas formas distintas de identificação.
* **Breach:** Incidente em que dados são acessados ou divulgados sem autorização.
* **BYOD (Bring Your Own Device):** Política que permite aos funcionários trazer seus dispositivos pessoais para o local de trabalho e usá-los para acessar recursos da empresa.
* **Cibersegurança:** Proteção de sistemas de computador contra roubo ou danos ao hardware, software ou dados, assim como de interrupções ou desvios dos serviços que eles fornecem.
* **Cloud Security:** Conjunto de políticas e tecnologias destinadas a proteger dados e infraestrutura em ambientes de nuvem.
* **Codificação Segura (AppSec):** Práticas de desenvolvimento de software que visam garantir que os aplicativos estejam protegidos contra vulnerabilidades de segurança.
* **Criptografia:** Prática de proteger informações transformando-as em um código, para impedir o acesso não autorizado.
* **Cryptography Key Management:** Processo de gerenciar chaves criptográficas em um sistema de criptografia.
* **DAST (Dynamic Application Security Testing):** Processo de testar um aplicativo ou sistema em execução para encontrar vulnerabilidades que um invasor poderia explorar.
* **Data Privacy:** Práticas voltadas para garantir que os dados pessoais sejam manuseados de forma segura, ética e legal.
* **DDoS (Distributed Denial of Service):** Ataque que visa tornar um serviço ou recurso de rede indisponível para seus usuários pretendidos, sobrecarregando o serviço com um fluxo excessivo de dados.
* **DevOps:** Prática que combina desenvolvimento de software (Dev) com operações de TI (Ops) para encurtar o ciclo de desenvolvimento e fornecer entrega contínua com alta qualidade de software.
* **DevSecOps:** Extensão do DevOps, integrando segurança (Sec) no ciclo de vida do desenvolvimento de software para garantir que a segurança seja considerada em todas as etapas.
* **Endpoint Security:** Proteção de dispositivos finais como desktops, laptops e dispositivos móveis contra ameaças cibernéticas.
* **Firewall:** Sistema de segurança de rede que monitora e controla o tráfego de rede com base em regras de segurança predefinidas.
* **HTTPS (Hypertext Transfer Protocol Secure):** Extensão do HTTP usada para comunicação segura em uma rede de computadores.

# Protocolo HTTP

HTTP (Hypertext Transfer Protocol) é, sem dúvida, um dos mais importantes protocolos, sendo o mais utilizado na transferência de arquivos hipertexto e seus recursos entre aplicações e clientes web.

## Características do HTTP

- **Baseado na troca de requisições e respostas** entre cliente e servidor.  
- **Stateless**: não guarda estado entre as conexões; a cada requisição é estabelecida uma nova conexão com o servidor.  
- **Camada de Aplicação** do modelo TCP/IP.  
- **Entrega confiável de dados** entre a origem e o destino.

---

## Métodos HTTP

Dois métodos são geralmente utilizados para um pedido e resposta entre cliente e servidor HTTP: **GET** e **POST**.

### GET

- Operação apenas de leitura (read-only).  
- Utilizada, por exemplo, quando um cliente solicita uma página específica de um site.  
- Os parâmetros de entrada são incluídos na URL da requisição.  
- A resposta retorna na própria URL solicitada.  
- Facilita marcações (bookmarking) e armazenamento em cache.  
- É o método padrão para envio de formulários em HTML.

### POST

- Usada para **enviar** dados ao servidor (ex.: informações de clientes, upload de arquivos, envio de formulários HTML).  
- Os parâmetros de entrada são passados **no corpo** da requisição.  
- Não oferece facilidades de bookmarking ou cache.  
- Não é o método padrão para envio de formulários em HTML; deve ser especificado explicitamente.  
- Do ponto de vista de segurança, é importante atentar para o caminho pelo qual os dados de entrada chegam à aplicação web.  

---


* **IAST (Interactive Application Security Testing):** Ferramenta que combina elementos de DAST e SAST (Static Application Security Testing) para identificar vulnerabilidades em aplicativos em tempo real.
* **IAM (Identity and Access Management):** Estrutura de políticas e tecnologias para garantir que as pessoas certas tenham acesso aos recursos tecnológicos apropriados.
* **Incident Response:** Processo organizado para tratar e gerenciar a resposta a um incidente de segurança ou violação de dados.
* **Injeção de SQL:** Tipo de ataque de segurança que utiliza código SQL malicioso para manipular o banco de dados por trás de uma aplicação.
* **Malware:** Software malicioso projetado para causar danos a um sistema de computador.
* **Mitre ATT&CK:** Framework globalmente acessível de conhecimento sobre táticas e técnicas usadas por atacantes cibernéticos.
* **NIST (National Institute of Standards and Technology):** Agência dos EUA que desenvolve padrões e diretrizes, incluindo os relacionados à cibersegurança.
* **OWASP (Open Web Application Security Project):** Organização online que fornece artigos, metodologias, documentação, ferramentas e tecnologias no campo da segurança de aplicações web.
* **OWASP Top 10:** Lista publicada pela OWASP que enumera as 10 principais vulnerabilidades mais críticas em aplicações web.
* **Patch Management:** Processo de gerenciar patches ou atualizações de software para sistemas e aplicações.
* **PCI-DSS (Payment Card Industry Data Security Standard):** Padrões de segurança para todas as entidades que processam, armazenam ou transmitem informações de cartão de crédito.
* **Penetration Testing (PenTest):** Método de avaliar a segurança de um sistema ou rede de computadores, simulando um ataque de um agente malicioso.
* **Phishing:** Tentativa de obter informações confidenciais de maneira fraudulenta, como nomes de usuário, senhas e detalhes do cartão de crédito.
* **Privacy by Default:** Princípio que garante que as configurações de privacidade mais restritivas sejam aplicadas por padrão, sem a necessidade de intervenção do usuário.
* **Privacy by Design:** Abordagem que promove a incorporação de práticas de privacidade desde o início do design de sistemas e processos.
* **Ransomware:** Tipo de malware que restringe o acesso ao sistema infectado e cobra um resgate para que o acesso possa ser restabelecido.
* **Red Team/Blue Team Exercises:** Simulações de segurança onde a equipe vermelha tenta atacar (imitando adversários externos) e a equipe azul defende (representando as defesas internas da organização).
* **Risk Assessment:** Processo de identificar, analisar e avaliar riscos de segurança.
* **SAMS (Security Automation and Orchestration):** Ferramentas que permitem às organizações automatizar e coordenar tarefas de segurança para melhorar a eficiência operacional e a resposta a incidentes.
* **SDLC (Software Development Life Cycle):** Processo de produção de software, que inclui etapas como planejamento, desenvolvimento, teste e implantação.
* **Segurança da Informação (InfoSec ou SI):** Práticas destinadas a proteger informações de serem acessadas, usadas, divulgadas, interrompidas, modificadas ou destruídas de maneira não autorizada.
* **Security Audit:** Avaliação sistemática da eficácia das medidas de segurança de uma organização.
* **SIEM (Security Information and Event Management):** Solução que fornece monitoramento em tempo real e análise de eventos de segurança.
* **SOC (Security Operations Center):** Instalação centralizada que lida com questões de segurança em uma base organizacional.
* **Social Engineering:** Tática que explora interações humanas para obter ou comprometer informações sobre uma organização ou seus sistemas de computador.
* **Threat Intelligence:** Informações usadas para entender as ameaças que uma organização enfrenta e como melhor se proteger contra elas.
* **Threat Modeling:** Processo para identificar e priorizar potenciais ameaças a um sistema e desenvolver medidas para mitigar ou prevenir essas ameaças.
* **TLS (Transport Layer Security):** Protocolo criptográfico projetado para fornecer comunicação segura pela Internet.
* **Token de Segurança:** Dispositivo físico usado para ganhar acesso a uma rede ou sistema eletrônico protegido.
* **Vulnerabilidade:** Fraqueza em um sistema de computador, procedimento, design ou implementação que pode ser explorada para causar dano ou acesso não autorizado.
* **Vulnerabilidade Zero-Day:** Falha de segurança em um software que é desconhecida para a parte responsável por corrigir a falha.
* **VPN (Virtual Private Network):** Rede privada que permite aos usuários enviar e receber dados através de redes públicas ou compartilhadas como se seus dispositivos de computação estivessem diretamente conectados a uma rede privada.
* **XSS (Cross-Site Scripting):** Tipo de vulnerabilidade de segurança que permite a um invasor injetar código malicioso em páginas web vistas por outros usuários.
* **Zero Trust Security:** Abordagem de segurança que não confia automaticamente em nada dentro ou fora de sua perímetro de rede e verifica tudo tentando se conectar aos seus sistemas antes de conceder acesso.

---