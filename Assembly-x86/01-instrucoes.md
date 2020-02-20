## Instruções Assembly

_Machine instructions generally fall into three categories: data movement, arithmetic/logic, and control-flow. In this section, we will look at important examples of x86 instructions from each category_.

- Uma instrução assembly completa, terá o Mnemônico da instrução a ser executada, depois o Operador onde ficará o resultado da operação(Operador de destino) e por último podemos ter um Operador origem, que irá fazer parte da operação a ser executada. Exemplo:


Mnemônico   | Op.destino  | Op. Origem 
----------- | ----------- |------------
MOV	        | ECX,        | 0x42	
LEA	        | EDX,		  | [EBP-28]
SUB	        | ESP,		  | 0x0
PUSH        | EBP 		  | 
XOR	        | EAX,		  | EAX
JMP	        | 0x41414141  |


#### Operandos

- Os principais operandos que podemos utilizar são :

1. IMEDIATOS = 0x42, 0x00401828, 0x0C

2. REGISTRADORES = EAX, ECX, EBP

3. ENDEREÇOS DE MEMÓRIA = [0x0012F8D4], [ECX], [EBP + 0x08]

_Os valores de operandos entre colchetes, como [0xff273] ou [EBP + 0xF11] são referentes ao valor contido no endereços de memória apontado dentro dos colchetes_.

#### Opcodes 

- Pelo fato do processador só conseguir decodificar os Opcodes ( hexadecimais ), então cada instrução em assembly que usamos tem seu respectivo opcode.

- Em suma, Opcodes, são os códigos que o processador consegue ler e entender.
- Mnemônicos, é a tradução legível para humanos desses Opcodes.

Exemplo:

		Instrução| MOV EAX, 0x42
		Opcodes | B9 42 00 00 00

_Então os Opcodes são basicamente o código(hexadecimal) que representa respectivos mnêmonicos/operandos assembly_.


