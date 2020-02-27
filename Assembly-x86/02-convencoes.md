Convenções x86
---------------


#### Bits, Bytes , Words, Dwords...


- A menor unidade de medida da computação é o Bit, mais temos outras nomeclaturas conforme o Bit(1 unidade) vai aumentando de tamanho. São elas:

Medida      | Tamanho (intel) | Nomeclatura (intel) |C lang
------------|-----------------|---------------------|---------
nibble      | 4 bits          |                     |
byte        | 8 bits          | BYTE                | char
Words       | 16 bits         | WORD                | short int
double word | 32 bits         | DWORD               | int
quad word   | 64 bits         | QWORD               | long int




#### Dicas sobre Strings


- O caractere de "espaço em branco" é o 0x20.
- Os dígitos vão de 0x30 a 0x39.
- As letras maiúsculas vão de 0x41 a 0x5a.
- As letras minúsculas vão de 0x61 a 0x7a.
- ASCII imprimíveis (de 0x20 à 0x7e)



#### CrLf

- Quando falamos de Strings no geral, um dos bytes importante é 0x0a, conhecido também por *\n*, line feed, LF ou simplesmente "caractere de nova linha".

- O MS-DOS e o Windows utilizam na verdade dois caracteres para delimitar uma nova linha. Antes do 0x0a, temos um 0x0d, conhecido também por \r, carriage return ou CR. Essa dupla é também conhecida por CrLf.


