Windows API
-------------

A Win32 API , é o conjunto de funções que o Windows oferece para seus programas.

- Uma API (Application Programming Interface) é uma interface para programar uma aplicação. No caso do Windows, consiste num conjunto de funções expostas para serem usadas por aplicativos, inclusive em user mode.

- Os aplicativos do Windows rodam em uma camada do Sistema Operacional conhecida como Ring 3 ou Userland. Porém esses programas precisam ser capazes de interagir com funções que ficam no Kernel do SO, em outra camada do Sistema Operacional que é conhecida como Ring 0 ou KernelLand.Existem funções da API do windows que permitem os aplicativos da Userland(Ring 3), solicitem uma operação específica ao Kernel(Ring 0).

- Se o programa precisar acessar uma função de baixo nível, "Invokar" uma função específica... a API permite interações com o kernel.

- O código das APIs, geralmente ficam nas DLLs do windows ( Ex: Y função A da x.dll ).

### Help :

- A Microsoft usa algumas convenções de nomes que precisam ser detalhadas, para o melhor entendimento dos protótipos das funções da API do Windows /.


		WINAPI : Define que a convenção de chamada da função é a '__ stdcall'
		
		_In_ : Define que o parâmetro é de entrada
		
		_Out_ : Define que o parâmetro é de saída (a função vai escrever nele)
		
		_opt_ : O parâmetro é opcional (pode ser NULL)
		
		HANDLE : Um número identificador de um objeto no ambiente Windows. Um handle é um número que identifica um objeto (arquivo, chave de registro, diretório, etc) 		aberto usado por um processo
		
		HWND : Um handle (identificador) da janela
		
		LPCTSTR : Long Pointer to a Const TCHAR STRing
		
		UINT : unsigned int ou DWORD (32-bits)

