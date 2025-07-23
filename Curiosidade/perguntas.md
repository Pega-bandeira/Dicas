**Questão 1**
* **Pergunta:** O que é um software antivírus?
* **Resposta:** Um programa que detecta e remove malware de um sistema.

***

**Questão 2**
* **Pergunta:** O que significa o termo "vulnerabilidade" em segurança da informação?
* **Resposta:** Uma falha ou fraqueza em um sistema que pode ser explorada.

***

**Questão 3**
* **Pergunta:** Uma transmissão de um e-mail foi interceptada por um criminoso virtual entre o remetente e o destinatário. O criminoso teve acesso ao conteúdo original, depois alterou o conteúdo da mensagem e o encaminhou ao destinatário, se fazendo passar pelo remetente. Para a situação descrita acima, assinale a alternativa correta:
* **Resposta:** Foram comprometidos os princípios da Confidencialidade e da Integridade.

***

**Questão 4**
* **Pergunta:** Qual das seguintes opções não é um exemplo de uma medida de segurança física?
* **Resposta:** Senhas fortes.

***

**Questão 5**
* **Pergunta:** O que é um firewall?
* **Resposta:** Um dispositivo de hardware que filtra o tráfego de rede.

***

**Questão 6**
* **Pergunta:** O que é phishing?
* **Resposta:** Um método de obter informações confidenciais por meio de engenharia social.

***

**Questão 7**
* **Pergunta:** Qual dos seguintes não é um exemplo de um protocolo de segurança na web?
* **Resposta:** FTP.

***

**Questão 8**
* **Pergunta:** Qual das seguintes opções é um exemplo de uma prática recomendada para proteger senhas?
* **Resposta:** Usar senhas longas e complexas.

***

**Questão 9**
* **Pergunta:** Um criminoso virtual utiliza de diversas técnicas para obter sucesso em uma tentativa de invasão ou em um roubo de informações. Em um processo de hacking, um termo muito utilizado é o de “Exploitar” uma aplicação. Assinale a alternativa que corresponde corretamente ao significado do termo Exploitar:
* **Resposta:** Exploitar uma aplicação significa expor e explorar as vulnerabilidades mais críticas de uma aplicação ou sistema, para que o atacante consiga alcançar maior impacto em sua invasão.

***

**Questão 10**
* **Pergunta:** O que significa o termo "phishing" em segurança da informação?
* **Resposta:** Um ataque que redireciona os usuários para um site falso.

---

# Perguntas e Respostas de Segurança Cibernética

## Questão 1
Existe um tipo de ataque cibernético conhecido como MITM - Man in the Middle. Esse ataque é caracterizado por um desenho onde o criminoso virtual consegue se colocar entre a origem e o destino em uma comunicação entre duas partes, tornando possível a interceptação da informação.
Considerando uma situação hipotética onde um servidor A precisa enviar uma informação para o cliente B e um atacante intercepta essa comunicação entre os pontos A e B, mas não consegue acessar o conteúdo da informação e nem alterá-la, porque ela está criptografada, assinale a alternativa que corresponde ao pilar da segurança da informação comprometido nesta situação:

**Resposta Correta:** Nenhum pilar foi comprometido

---

## Questão 2
Uma das formas mais eficientes de proteção da informação em uma transmissão é o uso da Criptografia. A Criptografia altera o conteúdo da mensagem original, de forma que um agente não autorizado não consiga ter acesso ao conteúdo da mensagem sem ter a chave que decifra a mensagem e a recupera em sua totalidade. 
Em relação aos pilares da segurança da informação, assinale a alternativa que corresponde àqueles que são protegidos com o uso da criptografia:

**Resposta Correta:** Confidencialidade, Integridade e Privacidade

---

## Questão 3
O modelo STRIDE foi desenvolvido para ajudar na identificação e classificação de ameaças à segurança cibernética de sistemas. Assinale a alternativa que corresponde corretamente ao significado do acrônimo STRIDE:

**Resposta Correta:** SPOOFING, TAMPERING, REPUDIATION, INFORMATION DISCLOSURE, DENIAL OF SERVICE, ELEVATION

---

## Questão 4
O que é um certificado digital?

**Resposta Correta:** Um arquivo eletrônico que vincula uma chave criptográfica a uma entidade

---

## Questão 5
O que é um firewall?
**Resposta Correta:** Um dispositivo de hardware que filtra o tráfego de rede

---

## Questão 6
Uma transmissão de um e-mail foi interceptada por um criminoso virtual entre o remetente e o destinatário. O criminoso teve acesso ao conteúdo original, depois alterou o conteúdo da mensagem e o encaminhou ao destinatário, se fazendo passar pelo remetente.
Para a situação descrita acima, assinale a alternativa correta:
**Resposta Correta:** Foram comprometidos os princípios da Confidencialidade e da Integridade.

---

## Questão 7
O que é engenharia social?

**Resposta Correta:** Um método de manipulação psicológica para obter informações confidenciais

---

## Questão 8
Existem diversos projetos que auxiliam os profissionais de Segurança Cibernética e Desenvolvimento Seguro de Software a descobrir e reduzir a incidência de vulnerabilidades e problemas de segurança relacionados ao desenvolvimento de aplicações.
Assinale a alternativa que corresponde corretamente ao principal projeto de segurança em aplicações:
**Resposta Correta:** OWASP TOP 10

---

## Questão 9
O que é uma política de segurança da informação?
**Resposta Correta:** Um conjunto de diretrizes e procedimentos para proteger informações

---

## Questão 10
O que é um backup de dados?
**Resposta Correta:** Uma cópia exata dos dados armazenados em um sistema

---

---

## Perguntas e Respostas Corretas (OWASP TOP 10 - 2021) 🔒

### Questão 1
Um usuário encontra uma forma de executar e executa uma ação a qual apenas usuários administradores têm acesso por padrão. Em qual categoria de risco este cenário deve ser classificado?

**Resposta Correta:** A1:2021 - Quebra de controle de acesso

---

### Questão 2
Uma empresa está desenvolvendo uma nova aplicação e precisa decidir qual a melhor opção para proteger as credenciais dos usuários armazenadas pela empresa:

**Resposta Correta:** Combinar as senhas com SALT e utilizar um algoritmo de HASH considerado seguro

---

### Questão 3
O trecho de código a seguir contém uma vulnerabilidade que pode ser classificada como qual das categorias de risco da OWASP TOP 10 2021?

*Trecho:*
`$search_query = $GET['q'];`
`echo '<h1> search results for: ' . $search_query . '</h1>;'`

**Resposta Correta:** A3:2021 - Injeção

---

### Questão 4
Que tipo de falha pode ser explorada para que um atacante execute código malicioso como sendo código de uma dependência de sua aplicação?

**Resposta Correta:** A8:2021 - Falhas de integridade de software e dados

---

### Questão 5
Servidores de uma empresa são invadidos e somente 3 meses depois, após uma base de dados ser exposta na dark web, o time de segurança da empresa identifica a ação dos atacantes. Qual medida das listadas abaixo poderiam, em conjunto, ter prevenido ou minimizado o cenário descrito?
Selecione duas:

**Respostas Corretas:**
* Geração de alertas automáticos através dos logs dos servidores invadidos
* Uso de um Intrusion Prevention System (IPS) na rede dos servidores

---

### Questão 6
Qual das opções abaixo é a mais recomendada para prevenir ataques contra falhas do tipo A1 - Quebra de controle de acesso?

**Resposta Correta:** Verificar a autorização de toda e qualquer transação ou requisição realizada

---

### Questão 7
Que tipo de falha acontece quando uma aplicação renderiza dados de usuário como parte do código HTML enviado ao lado cliente sem validação?

**Resposta Correta:** Cross-site scripting (XSS)

---

### Questão 8
Qual das categorias de risco abaixo foi adicionada ou renomeada na lista de principais riscos da OWASP TOP 10 2021?

**Resposta Correta:** A4:2021 - Design Inseguro

---

### Questão 9
Roteadores de uma empresa permitem o acesso externo à interface de administração dos equipamentos e a senha de administrador utilizada é a senha fornecida por padrão pelo fabricante. Este é um cenário exemplo de qual categoria de risco:

**Resposta Correta:** A5:2021 - Configuração de segurança incorreta

---

### Questão 10
Que tipo de falha acontece quando dados fornecidos pelo usuário são enviados a um interpretador ou inseridos como parte da consulta de banco de dados, sem validação?

**Resposta Correta:** Falhas da injeção

---

### Questão 11
O que é uma política de segurança de aplicativos da web?

**Resposta Correta:** Um conjunto de diretrizes que definem como o aplicativo da web deve ser configurado e protegido.

---

### Questão 12
Qual é o principal objetivo de uma auditoria de segurança de banco de dados?

**Resposta Correta:** Identificar vulnerabilidades de segurança no banco de dados.

---

### Questão 13
Qual é o principal objetivo de uma política de gerenciamento de patches?

**Resposta Correta:** Proteger o aplicativo da web contra vulnerabilidades conhecidas e corrigidas.

---

### Questão 14
Qual das seguintes opções é uma das melhores práticas para evitar falhas criptográficas?

**Resposta Correta:** Usar algoritmos de criptografia atualizados e fortes.

---

### Questão 15
Qual das seguintes opções é uma das melhores práticas para evitar falhas de autenticação e identificação?

**Resposta Correta:** Usar autenticação multifator.

---

### Questão 16
Qual das seguintes opções é uma das melhores práticas para evitar configurações de segurança incorretas?

**Resposta Correta:** Instalar todos os patches e atualizações de segurança necessários.

---

### Questão 19
Qual das seguintes práticas ajuda a prevenir a vulnerabilidade de Broken Access Control?

**Resposta Correta:** Utilizar sessões e cookies seguros para gerenciar o estado da autenticação

---

### 20
Um sistema de gerenciamento de pedidos online permite que usuários façam pedidos, mas não valida adequadamente se o usuário autenticado tem permissão para visualizar ou modificar os pedidos de outros usuários. Isso permite que um usuário acesse e altere informações confidenciais de outros usuários, incluindo detalhes de pagamento e endereços de entrega. Essa vulnerabilidade está relacionada a:

**Resposta Correta:** 
Insecure Direct Object References (IDOR)