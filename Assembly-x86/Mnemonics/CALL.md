CALL ( Chamada )
=================

### Sintaxe:

	CALL ARG1

- Essa instrução faz um salto para o início de uma sub-rotina. Além disso ela coloca na pilha, o endereço RVA(relative virtual address) da próxima instrução.. que será o ponto de retorno após a execução da sub-rotina.

- Em suma, a instrução CALL transfere o controle do programa para uma sub-rotina. Quando a sub-rotina é concluída, o controle é transferido para a linha após a instrução CALL.

#### Exemplos de uso, da instrução CALL :

		CALL 401000   ( call endereço)

		CALL EAX      ( call registrador - executa uma rotina com o endereço == eax )

		CALL DWORD PTR [EAX] ( executa no endereço com valor == eax )

		CALL DWORD PTR [EAX + 5] ( executa no endereço com valor == eax + 5 )
		
		CALL <jmp.MessageBoxA>   ( basicamente : call endereço , porém é um tipo especial, pois executa uma função da API do windows )