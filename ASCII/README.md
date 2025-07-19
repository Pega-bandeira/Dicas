## 1. Por que o ASCII original é um **padrão de 7 bits**?

Quando o ASCII foi padronizado (década de 1960 – ANSI X3.4-1963), havia **fortes limitações de hardware e custo**:

1. **Economia de largura de banda e memória:** Cada bit “custava” caro (fita perfurada, linhas telegráficas, teletipos). Usar 7 bits em vez de 8 reduzia armazenamento e transmissão em \~12,5%.
2. **Compatibilidade com equipamentos existentes:** Muitos dispositivos (teletipos / TTY) já trabalhavam com **códigos de 5, 6 ou 7 bits** (ex.: Baudot de 5 bits e variantes). Adotar 7 bits era um salto razoável sem exigir mudança radical.
3. **Uso do 8º bit para controle/paridade:** Linhas de comunicação eram ruidosas. O hardware podia transmitir 8 bits fisicamente, mas o bit extra frequentemente era usado como **bit de paridade** (detectar erros simples) ou para protocolos (marcação, extensões proprietárias).
4. **Cobertura suficiente para o inglês “básico”:** O objetivo inicial era representar letras latinas sem acentos, dígitos, sinais de pontuação e caracteres de controle para dispositivos (bell, carriage return, line feed etc.). Para esse conjunto, 128 símbolos era considerado suficiente.

## 2. Por que o intervalo vai de **0 a 127**?

Porque 7 bits permitem **2⁷ = 128** combinações distintas. Se numeramos a partir de zero (binário padrão), os valores possíveis são:

```
0000000₂ = 0
...
1111111₂ = 127
```

Logo, o domínio natural é **\[0, 127]**.

## 3. Como o espaço de 128 posições foi organizado?

O ASCII não distribuiu os códigos aleatoriamente; há uma estrutura intencional:

| Faixa decimal | Descrição                                | Observações                                                           |        |
| ------------- | ---------------------------------------- | --------------------------------------------------------------------- | ------ |
| 0–31          | **Control characters** (não imprimíveis) | NUL, BEL (campainha), CR (carriage return), LF (line feed), ESC, etc. |        |
| 32            | SPACE                                    | Primeiro imprimível (espaço em branco).                               |        |
| 33–47         | Pontuação e símbolos                     | `! " # $ % & ' ( ) * + , - . /`                                       |        |
| 48–57         | Dígitos                                  | `0–9` contíguos (permite aritmética simples manipulando códigos).     |        |
| 58–64         | Pontuação/símbolos                       | `: ; < = > ? @`                                                       |        |
| 65–90         | **Letras maiúsculas A–Z**                | Intervalo contíguo.                                                   |        |
| 91–96         | Símbolos                                 | \`\[ \ ] ^ \_ \`\`                                                    |        |
| 97–122        | **Letras minúsculas a–z**                | Também contíguas; diferença para maiúscula é sempre 32 (0x20).        |        |
| 123–126       | Símbolos finais                          | \`{                                                                   | } \~\` |
| 127           | DEL (delete)                             | Usado para apagar em fitas perfuradas (marcar todos os furos).        |        |

### Observações elegantes da organização:

* Diferença constante entre maiúscula e minúscula: `'a' - 'A' = 32 (0x20)`. Isso facilita **toggle** de caixa manipulando um bit.
* Dígitos são compactos: `'0'` é 48; para converter dígito char → valor numérico: `ord(ch) - 48`.
* O agrupamento facilita faixas em expressões regulares e comparações.

## 4. E o 8º bit que “sobrou” nos computadores de 8 bits?

Quando a memória/linhas passaram a tratar naturalmente **bytes de 8 bits**, o 8º bit (valores 128–255) foi aberto para **extensões**:

* **ASCII estendido (não oficial):** Várias páginas de código (CP437, ISO-8859-1, Windows-1252) colocaram acentos, símbolos gráficos, caracteres de línguas europeias etc. Não existe um “ASCII de 8 bits” oficial — o padrão ASCII mesmo continua sendo só 0–127.
* O 8º bit deixou de ser paridade à medida que **protocolos de camada inferior** começaram a garantir integridade de outra forma (checksums, CRCs).

## 5. Limitações e evolução

ASCII funciona muito bem para inglês, mas:

* Não inclui acentos (`á, ç, ñ, ü`), alfabetos não latinos, símbolos matemáticos amplos, ideogramas, etc.
* A fragmentação de “ASCII estendidos” causou incompatibilidades (um código 0xE9 podia significar coisas diferentes em tabelas distintas).

**UTF-8** surgiu (1992–1993) como solução universal: mantém **identidade com ASCII para 0–127** (mesmos bytes) e permite codificar milhões de pontos de código Unicode com sequência variável de 1–4 bytes.

## 6. Por que *não* usar 6 ou 8 bits desde o início?

* **6 bits (64 símbolos)** não seria suficiente para letras (26), dígitos (10), espaço, pontuação essencial e controles.
* **8 bits (256 símbolos)** teria sido “exagero caro” para o hardware de então, e faltava consenso internacional sobre quais 256 símbolos incluir. O uso de 7 + paridade era um compromisso técnico e econômico.

## 7. Resumo em frases curtas

* ASCII usa 7 bits → 128 códigos (0–127) porque era **barato**, **suficiente** e deixava espaço (8º bit) para paridade/extensão.
* O intervalo 0–127 é simplesmente o conjunto de todas as combinações possíveis de 7 bits.
* A organização interna foi desenhada para facilitar operações algébricas, distinção de classes de caracteres e controle de dispositivos.

## 8. Tabela mini (exemplos)

| Dec | Binário 7b | Char     | Categoria            |
| --- | ---------- | -------- | -------------------- |
| 10  | 0001010    | LF       | Controle (line feed) |
| 32  | 0100000    | (espaço) | Espaço               |
| 48  | 0110000    | 0        | Dígito               |
| 65  | 1000001    | A        | Maiúscula            |
| 97  | 1100001    | a        | Minúscula            |
| 123 | 1111011    | {        | Símbolo              |
| 127 | 1111111    | DEL      | Controle (delete)    |

