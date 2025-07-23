# Modelo STRIDE

**STRIDE** é um modelo desenvolvido por Praerit Garg e Loren Kohnfelder na Microsoft, com o objetivo de ajudar na identificação e classificação de ameaças à segurança cibernética de sistemas. Ele organiza as ameaças em seis categorias principais:

## Ameaças STRIDE

- **S – Spoofing (Falsificação de identidade)**  
  Ato de se passar por outro usuário ou sistema legítimo, comprometendo a autenticidade.

- **T – Tampering (Violação/Alteração)**  
  Modificação não autorizada de dados ou componentes de um sistema.

- **R – Repudiation (Repúdio)**  
  Situação em que um agente nega ter realizado uma ação e não há evidências suficientes para provar o contrário.

- **I – Information Disclosure (Divulgação de Informação / Vazamento de Dados)**  
  Exposição não autorizada de informações sensíveis.

- **D – Denial of Service (Negação de Serviço, DoS)**  
  Ameaça que torna um recurso indisponível ou degradado para usuários legítimos.

- **E – Elevation of Privilege (Elevação de Privilégio)**  
  Quando um usuário ou processo obtém privilégios maiores do que os originalmente concedidos.
# Definições Importantes do Modelo STRIDE

O modelo **STRIDE**, criado por Praerit Garg e Loren Kohnfelder na Microsoft, classifica as ameaças à segurança em seis categorias. Abaixo, as definições em inglês e suas traduções para o português:

| Sigla | Termo em Inglês                                          | Definição em Inglês                                    | Tradução (PT-BR)                                                   |
|:-----:|:---------------------------------------------------------|:-------------------------------------------------------|:-------------------------------------------------------------------|
| **S** | **Spoofing**                                             | Impersonating another person/process                   | **Falsificação:** Fingir ser outra pessoa/processo                 |
| **T** | **Tampering**                                            | Unauthorized alterations                               | **Adulteração:** Alterações não autorizadas                       |
| **R** | **Repudiation**                                          | Denying claims/unproven actions                        | **Repúdio:** Negar reivindicações/ações não comprovadas           |
| **I** | **Information Disclosure**                               | Exposure to unauthorized person/process                | **Vazamento de informação:** Exposição a pessoa/processo não autorizado |
| **D** | **Denial of Service (DoS)**                              | Service unavailability                                 | **Negação de serviço:** Indisponibilidade de serviço              |
| **E** | **Elevation of Privileges**                              | Increasing person/process access level                 | **Elevação de privilégios:** Aumento do nível de acesso de pessoa/processo |

----



----

O DREAD é um modelo de **análise e priorização de riscos** que costuma ser usado em conjunto com o STRIDE. Enquanto o STRIDE te ajuda a **identificar** tipos de ameaça, o DREAD te ajuda a **avaliar** e **priorizar** cada uma delas segundo o risco que representam.

---

## O que é o DREAD

Cada letra do DREAD corresponde a um critério de avaliação:

| **D** | **Damage Potential** (Potencial de Dano) | Quão grave seria o impacto se o ataque ocorresse?          |
| :---: | :--------------------------------------- | :--------------------------------------------------------- |
| **R** | **Reproducibility** (Reprodutibilidade)  | Com que facilidade alguém conseguiria reproduzir o ataque? |
| **E** | **Exploitability** (Explorabilidade)     | Quão difícil é encontrar ou desenvolver um exploit?        |
| **A** | **Affected Users** (Usuários Afetados)   | Quantas pessoas/sistemas seriam impactados?                |
| **D** | **Discoverability** (Descobribilidade)   | Com que facilidade um atacante descobriria essa falha?     |

Em cada critério você atribui uma nota (por ex. de 0 a 10) e depois calcula uma **pontuação total** (soma ou média) para priorizar o tratamento.

---

## Como complementar o STRIDE com DREAD

1. **Mapear** todas as ameaças usando STRIDE (Spoofing, Tampering, …).
2. Para **cada** ameaça identificada, **avaliar** os cinco fatores do DREAD.
3. **Pontuar** e **ordenar**. As ameaças com maiores pontuações DREAD são aquelas que você deve mitigar primeiro.

### Exemplo de tabela combinada

| Ameaça STRIDE               | D (0–10) | R (0–10) | E (0–10) | A (0–10) | D (0–10) | **Score** |
| :-------------------------- | :------: | :------: | :------: | :------: | :------: | :-------: |
| Spoofing de sessão (S)      |     8    |     4    |     6    |     7    |     5    |   30/50   |
| Alteração de parâmetros (T) |     6    |     5    |     7    |     6    |     4    |   28/50   |
| …                           |     …    |     …    |     …    |     …    |     …    |     …     |

> **Interpretando:**
>
> * **Score alto** → ameaça de maior prioridade.
> * **Score baixo**  → pode ser tratada depois.

---

### Passos práticos

1. **Defina escala** (0–5, 0–10, etc.) e critérios claros para cada fator.
2. **Crie uma planilha** (Excel/Markdown) para registrar STRIDE × DREAD.
3. **Revise periodicamente**: conforme mudanças no sistema, reavalie scores.

Dessa forma você junta a **classificação qualitativa** do STRIDE com a **quantificação de riscos** do DREAD, garantindo um roadmap de mitigação focado nas ameaças mais críticas.
