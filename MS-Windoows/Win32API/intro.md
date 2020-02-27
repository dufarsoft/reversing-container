Windows API
-------------

A Win32 API , é o conjunto de funções que o Windows oferece para seus programas.

- Uma API (Application Programming Interface) é uma interface para programar uma aplicação. No caso do Windows, consiste num conjunto de funções expostas para serem usadas por aplicativos, inclusive em user mode.

- Os aplicativos do Windows rodam em uma camada do Sistema Operacional conhecida como Ring 3 ou Userland. Porém esses programas precisam ser capazes de interagir com funções que ficam no Kernel do SO, em outra camada do Sistema Operacional que é conhecida como Ring 0 ou KernelLand.Existem funções da API do windows que permitem os aplicativos da Userland(Ring 3), solicitem uma operação específica ao Kernel(Ring 0).

- Se o programa precisar acessar uma função de baixo nível, "Invokar" uma função específica... a API permite interações com o kernel.

- O código das APIs, geralmente ficam nas DLLs do windows ( Ex: A função Y da x.dll ).


----


[Funções da API do Windows](list-Win32API-functions.md)
---------------------------------------------------------


