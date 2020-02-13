MessageBoxA
-------------

User32.dll

## Protótipo :

	int WINAPI MessageBox(
	    _In_opt_ HWND    hWnd,
	    _In_opt_ LPCTSTR lpText,
	    _In_opt_ LPCTSTR lpCaption,
	    _In_     UINT    uType
	);


## Parâmetros da função MessageBoxA:

### hWnd [entrada, opcional]

Um handle que identifica qual janela é dona da caixa de mensagem. Isso serve para atrelar uma mensagem a uma certa janela (e impedi-la de ser fechada antes da caixa de mensagem, por exemplo). Como é opcional, este parâmetro pode ser NULL, o que faz com que a caixa de mensagem não possua uma janela dona.

### lpText [entrada, opcional]

Um ponteiro para um texto (uma string) que será exibido na caixa de mensagem. Se for NULL, a mensagem não terá um conteúdo, mas ainda assim aparecerá.

### lpCaption [entrada, opcional]

Um ponteiro para o texto que será o título da caixa de mensagem. Se for NULL a caixa de mensagem não terá um título, mas ainda aparecerá.

### uType [entrada]

Configura o tipo de caixa de mensagem. É um número inteiro que pode ser definido por macros para cada flag, definida na documentação da função. Se passada a macro MB_OKCANCEL (0x00000001L), por exemplo, faz com que a caixa de mensagem tenha dois botões: OK e Cancelar. Se passada a macro MB_ICONEXCLAMATION (0x00000030L), a janela terá um ícone de exclamação. Se quiséssemos combinar as duas características, precisaríamos passar as duas flags utilizando uma operação OU entre elas, assim: MB_OKCANCEL | MB_ICONEXCLAMATION


- Observação: Dizer que um parâmetro é opcional não quer dizer que você não precise passá-lo ao chamar a função, mas sim que ele pode ser NULL, ou zero, dependendo do que a documentação da função diz.

---

- Exemplo em C :

		int main(void)

		{

			MessageBoxA(
				NULL,
				"Eduardo",
				"d0x75",
				MB_OK | MB_ICONEXCLAMATION
			);
		return 0;

		}


---


## Disassembly da MessageBoxA





https://docs.microsoft.com/pt-br/windows/win32/api/winuser/nf-winuser-messagebox?redirectedfrom=MSDN