Termos utilizados em intel x86
-------------------------------

### Official Operands

- rel8

- rel16, rel32

- ptr16:16, ptr16:32

- r8

- r16

- r32

- imm8

- imm16

- imm32

- r/m8

- r/m16

- r/m32

- m

- m8

- m16

- m32

- m64

- m16:16, m16:32

- m16&32, m16&16, m32&32

- moffs8, moffs16, moffs32

- Sreg

- m32real, m64real, m80real

- m16int, m32int, m64int

- ST or ST(0)

- ST(i)

- mm

- mm/m32

- mm/m64


### Generalized Operands


- acc

- reg

- r8

- r16

- r32

- imm

- imm8

- imm16

- mem

- mem8

- mem16

- mem32

- mem48

- dest

- short


Termos/Conceitos utilizados pela Microsoft
--------------------------------------------


- A Microsoft usa algumas convenções de nomes que precisam ser detalhadas, para o melhor entendimento dos protótipos das funções da API do Windows /.


		WINAPI : Define que a convenção de chamada da função é a '__ stdcall'
		
		_In_ : Define que o parâmetro é de entrada
		
		_Out_ : Define que o parâmetro é de saída (a função vai escrever nele)
		
		_opt_ : O parâmetro é opcional (pode ser NULL)
		
		HANDLE : Um número identificador de um objeto no ambiente Windows. Um handle é um número que identifica um objeto (arquivo, chave de registro, diretório, etc) 		aberto usado por um processo
		
		HWND : Um handle (identificador) da janela
		
		LPCTSTR : Long Pointer to a Const TCHAR STRing
		
		UINT : unsigned int ou DWORD (32-bits)

- attribute certificate

- date/time stamp

- file pointer

- linker

- object file

- reserved must be 0

- RVA :

- VA : 

Termos diversos
---------------


*uint16_t* =  é um tipo na linguagem C que define uma variável de 16 bits ou 2 bytes

*uint16_t e_res[4]* = que é um array de 4 campos de 16 bits, totalizando em 64 bits ou 8 bytes.

*uint16_t e_res2[10]* = que é um array de 10 campos de 16 bits, totalizando em 160 bits ou 20 bytes.

*uint32_t e_lfanew* = que é um campo de 32 bits ou 4 bytes.