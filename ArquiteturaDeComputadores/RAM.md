RAM ( Random Access Memory)
----------------------------


		Main Memory
		===================

		low MemoryAddress
		--------------------
		Stack|
		Heap |
		Code |
		Data |
		--------------------
		High MemoryAddress
		--------------------


_A memória SEMPRE cresce do maior para o menor_



#### Stack ( pilha )

- Armazena variáveis locais, parâmetros de funções e serve para controle de fluxo de alguns programas.

_Exemplo:_

Por exemplo o printf ( da linguagem C ), essa função recebe uma string de texto e exibe em um dispositivo de saída. Então teoricamente essa função tem o parâmetro TEXTO, então um ponteiro pra esse texto será armazenado na função.


- Na arquitetura x86 os endereços de memória são de 32-bits. Ao análisar a Stack, é bom se acostumar com decrementos de 4 bytes (DWORD) _Exemplo:_

		12FF90, 12FF8C, 12FF88, 12FF84, 12FF80, 12FF7C...


#### Heap

- Parte da RAM utilizada como memória dinâmica do programa.. ela pode aumentar e diminuir de acordo com a execução do programa.


#### Code

- Nessa parte é onde ficam as instruções que o programa executa. Entao teóricamente essa parte da memória precisa ter a permissão de EXECUÇÃO, que é diferente da Data.


#### Data


- Por fim na parte Data, ficam os dados globais , estáticos, do programa..  como variáveis globais que não mudam com a execução do programa. Com permissão apenas de leitura.

