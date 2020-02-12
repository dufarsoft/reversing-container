IsDebuggerPresent
------------------

Função usada para detectar se o aplicativo está sendo debuggado após estar compilado.


### Protótipo :


	BOOL IsDebuggerPresent();


### Parâmetros da função : 

Não contém parâmetros.


### Valores de Retorno :

- Quando o retorno for diferente de 0 , o binário estará rodando em um debugger.

- Se o valor retorno = 0 , o binário não estára rodando em um debugger.