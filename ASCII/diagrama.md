# Tabela ASCII (0–127)

Representação visual completa dos 128 códigos ASCII de 7 bits. Inclui decimal (Dec), hexadecimal (Hex), binário (Bin 7b), caractere (Char) e categoria. Caracteres de controle recebem abreviação padrão.

## Legenda de Categorias

* **CTRL**: Caractere de controle (não imprimível)
* **PUNC**: Pontuação / símbolo
* **DIG**: Dígito
* **UP**: Letra maiúscula
* **LOW**: Letra minúscula
* **SPACE**: Espaço

> Observação: Binário mostrado com 7 bits sem o bit de paridade.

## 0–31: Controle

| Dec | Hex | Bin 7b  | Char | Nome / Função             | Categoria |
| --: | --: | :------ | :--- | :------------------------ | :-------- |
|   0 |  00 | 0000000 | NUL  | Null                      | CTRL      |
|   1 |  01 | 0000001 | SOH  | Start of Heading          | CTRL      |
|   2 |  02 | 0000010 | STX  | Start of Text             | CTRL      |
|   3 |  03 | 0000011 | ETX  | End of Text               | CTRL      |
|   4 |  04 | 0000100 | EOT  | End of Transmission       | CTRL      |
|   5 |  05 | 0000101 | ENQ  | Enquiry                   | CTRL      |
|   6 |  06 | 0000110 | ACK  | Acknowledge               | CTRL      |
|   7 |  07 | 0000111 | BEL  | Bell (alerta)             | CTRL      |
|   8 |  08 | 0001000 | BS   | Backspace                 | CTRL      |
|   9 |  09 | 0001001 | HT   | Horizontal Tab (TAB)      | CTRL      |
|  10 |  0A | 0001010 | LF   | Line Feed (\n)            | CTRL      |
|  11 |  0B | 0001011 | VT   | Vertical Tab              | CTRL      |
|  12 |  0C | 0001100 | FF   | Form Feed                 | CTRL      |
|  13 |  0D | 0001101 | CR   | Carriage Return (\r)      | CTRL      |
|  14 |  0E | 0001110 | SO   | Shift Out                 | CTRL      |
|  15 |  0F | 0001111 | SI   | Shift In                  | CTRL      |
|  16 |  10 | 0010000 | DLE  | Data Link Escape          | CTRL      |
|  17 |  11 | 0010001 | DC1  | Device Control 1 (XON)    | CTRL      |
|  18 |  12 | 0010010 | DC2  | Device Control 2          | CTRL      |
|  19 |  13 | 0010011 | DC3  | Device Control 3 (XOFF)   | CTRL      |
|  20 |  14 | 0010100 | DC4  | Device Control 4          | CTRL      |
|  21 |  15 | 0010101 | NAK  | Negative Acknowledge      | CTRL      |
|  22 |  16 | 0010110 | SYN  | Synchronous Idle          | CTRL      |
|  23 |  17 | 0010111 | ETB  | End of Transmission Block | CTRL      |
|  24 |  18 | 0011000 | CAN  | Cancel                    | CTRL      |
|  25 |  19 | 0011001 | EM   | End of Medium             | CTRL      |
|  26 |  1A | 0011010 | SUB  | Substitute                | CTRL      |
|  27 |  1B | 0011011 | ESC  | Escape                    | CTRL      |
|  28 |  1C | 0011100 | FS   | File Separator            | CTRL      |
|  29 |  1D | 0011101 | GS   | Group Separator           | CTRL      |
|  30 |  1E | 0011110 | RS   | Record Separator          | CTRL      |
|  31 |  1F | 0011111 | US   | Unit Separator            | CTRL      |

## 32–47: Espaço e Pontuação

| Dec | Hex | Bin 7b  | Char | Descrição       | Categoria |
| --: | --: | :------ | :--- | :-------------- | :-------- |
|  32 |  20 | 0100000 | (SP) | Espaço          | SPACE     |
|  33 |  21 | 0100001 | !    | Exclamação      | PUNC      |
|  34 |  22 | 0100010 | "    | Aspas duplas    | PUNC      |
|  35 |  23 | 0100011 | #    | Cerquilha       | PUNC      |
|  36 |  24 | 0100100 | \$   | Cifrão          | PUNC      |
|  37 |  25 | 0100101 | %    | Percent         | PUNC      |
|  38 |  26 | 0100110 | &    | E comercial     | PUNC      |
|  39 |  27 | 0100111 | '    | Apóstrofo       | PUNC      |
|  40 |  28 | 0101000 | (    | Parêntese abre  | PUNC      |
|  41 |  29 | 0101001 | )    | Parêntese fecha | PUNC      |
|  42 |  2A | 0101010 | \*   | Asterisco       | PUNC      |
|  43 |  2B | 0101011 | +    | Mais            | PUNC      |
|  44 |  2C | 0101100 | ,    | Vírgula         | PUNC      |
|  45 |  2D | 0101101 | -    | Hífen           | PUNC      |
|  46 |  2E | 0101110 | .    | Ponto           | PUNC      |
|  47 |  2F | 0101111 | /    | Barra           | PUNC      |

## 48–57: Dígitos

| Dec | Hex | Bin 7b  | Char | Categoria |
| --: | --: | :------ | :--- | :-------- |
|  48 |  30 | 0110000 | 0    | DIG       |
|  49 |  31 | 0110001 | 1    | DIG       |
|  50 |  32 | 0110010 | 2    | DIG       |
|  51 |  33 | 0110011 | 3    | DIG       |
|  52 |  34 | 0110100 | 4    | DIG       |
|  53 |  35 | 0110101 | 5    | DIG       |
|  54 |  36 | 0110110 | 6    | DIG       |
|  55 |  37 | 0110111 | 7    | DIG       |
|  56 |  38 | 0111000 | 8    | DIG       |
|  57 |  39 | 0111001 | 9    | DIG       |

## 58–64: Pontuação

| Dec | Hex | Bin 7b  | Char | Descrição       | Categoria |
| --: | --: | :------ | :--- | :-------------- | :-------- |
|  58 |  3A | 0111010 | :    | Dois-pontos     | PUNC      |
|  59 |  3B | 0111011 | ;    | Ponto e vírgula | PUNC      |
|  60 |  3C | 0111100 | <    | Menor que       | PUNC      |
|  61 |  3D | 0111101 | =    | Igual           | PUNC      |
|  62 |  3E | 0111110 | >    | Maior que       | PUNC      |
|  63 |  3F | 0111111 | ?    | Interrogação    | PUNC      |
|  64 |  40 | 1000000 | @    | Arroba          | PUNC      |

## 65–90: Letras Maiúsculas

| Dec | Hex | Bin 7b  | Char | Categoria |
| --: | --: | :------ | :--- | :-------- |
|  65 |  41 | 1000001 | A    | UP        |
|  66 |  42 | 1000010 | B    | UP        |
|  67 |  43 | 1000011 | C    | UP        |
|  68 |  44 | 1000100 | D    | UP        |
|  69 |  45 | 1000101 | E    | UP        |
|  70 |  46 | 1000110 | F    | UP        |
|  71 |  47 | 1000111 | G    | UP        |
|  72 |  48 | 1001000 | H    | UP        |
|  73 |  49 | 1001001 | I    | UP        |
|  74 |  4A | 1001010 | J    | UP        |
|  75 |  4B | 1001011 | K    | UP        |
|  76 |  4C | 1001100 | L    | UP        |
|  77 |  4D | 1001101 | M    | UP        |
|  78 |  4E | 1001110 | N    | UP        |
|  79 |  4F | 1001111 | O    | UP        |
|  80 |  50 | 1010000 | P    | UP        |
|  81 |  51 | 1010001 | Q    | UP        |
|  82 |  52 | 1010010 | R    | UP        |
|  83 |  53 | 1010011 | S    | UP        |
|  84 |  54 | 1010100 | T    | UP        |
|  85 |  55 | 1010101 | U    | UP        |
|  86 |  56 | 1010110 | V    | UP        |
|  87 |  57 | 1010111 | W    | UP        |
|  88 |  58 | 1011000 | X    | UP        |
|  89 |  59 | 1011001 | Y    | UP        |
|  90 |  5A | 1011010 | Z    | UP        |

## 91–96: Símbolos

| Dec | Hex | Bin 7b  | Char | Descrição       | Categoria |
| --: | --: | :------ | :--- | :-------------- | :-------- |
|  91 |  5B | 1011011 | \[   | Colchete abre   | PUNC      |
|  92 |  5C | 1011100 | \\   | Barra invertida | PUNC      |
|  93 |  5D | 1011101 | ]    | Colchete fecha  | PUNC      |
|  94 |  5E | 1011110 | ^    | Circunflexo     | PUNC      |
|  95 |  5F | 1011111 | \_   | Underscore      | PUNC      |
|  96 |  60 | 1100000 | \`   | Acento grave    | PUNC      |

## 97–122: Letras Minúsculas

| Dec | Hex | Bin 7b  | Char | Categoria |
| --: | --: | :------ | :--- | :-------- |
|  97 |  61 | 1100001 | a    | LOW       |
|  98 |  62 | 1100010 | b    | LOW       |
|  99 |  63 | 1100011 | c    | LOW       |
| 100 |  64 | 1100100 | d    | LOW       |
| 101 |  65 | 1100101 | e    | LOW       |
| 102 |  66 | 1100110 | f    | LOW       |
| 103 |  67 | 1100111 | g    | LOW       |
| 104 |  68 | 1101000 | h    | LOW       |
| 105 |  69 | 1101001 | i    | LOW       |
| 106 |  6A | 1101010 | j    | LOW       |
| 107 |  6B | 1101011 | k    | LOW       |
| 108 |  6C | 1101100 | l    | LOW       |
| 109 |  6D | 1101101 | m    | LOW       |
| 110 |  6E | 1101110 | n    | LOW       |
| 111 |  6F | 1101111 | o    | LOW       |
| 112 |  70 | 1100000 | p    | LOW       |
| 113 |  71 | 1100011 | q    | LOW       |
| 114 |  72 | 1100010 | r    | LOW       |
| 115 |  73 | 1100011 | s    | LOW       |
| 116 |  74 | 1100100 | t    | LOW       |
| 117 |  75 | 1100101 | u    | LOW       |
| 118 |  76 | 1100110 | v    | LOW       |
| 119 |  77 | 1100111 | w    | LOW       |
| 120 |  78 | 1101000 | x    | LOW       |
| 121 |  79 | 1101001 | y    | LOW       |
| 122 |  7A | 1101010 | z    | LOW       |

## 123–127: Símbolos Finais e Controle

| Dec | Hex | Bin 7b  | Char | Descrição       | Categoria      |      |
| --: | --: | :------ | :--- | :-------------- | :------------- | ---- |
| 123 |  7B | 1101011 | {    | Chave abre      | PUNC           |      |
| 124 |  7C | 1101100 |      |                 | Barra vertical | PUNC |
| 125 |  7D | 1101101 | }    | Chave fecha     | PUNC           |      |
| 126 |  7E | 1101110 | \~   | Til             | PUNC           |      |
| 127 |  7F | 1111111 | DEL  | Delete (apagar) | CTRL           |      |

## Notas Extras

* Diferença `'a' - 'A' = 32 (0x20)`.
* Faixas contíguas facilitam verificações: `if '0' <= c <= '9':` para dígitos.
* `DEL` (127) perfurava todos os furos na fita, sobrescrevendo um caractere.