## DOS Header ( Cabeçalho MZ do DOS )

- Cabeçalhos, como o próprio nome diz, são áreas de dados no ínicio de um arquivo. São definidos por conjuntos de diferentes campos que possuem valores.

- O arquivo PE começa com o DOS Header, que sempre ocupa os primeiros 64bytes do arquivo.

_Abaixo a estrutura oficial do "DOS Header"_ :


	typedef struct IMAGE_DOS_HEADER
	{
	     WORD e_magic;    - Assinatura "MZ" ( DOS Signature )
	     WORD e_cblp;     - Tamanho da última página.
	     WORD e_cp;       - Total de páginas.
	     WORD e_crlc;     - Itens de relocação.
	     WORD e_cparhdr;  - Tamanho do cabeçalho DOS.
	     WORD e_minalloc; - Tamanho mínimo da memória.
	     WORD e_maxalloc; - Tamanho máximo da memória.
	     WORD e_ss;       - Valor inicial do registrador SS ( Stack Segment )
	     WORD e_sp;       - Valor inicial do registrador SP ( Stack Pointer )
	     WORD e_csum;     - Checksum do cabeçalho DOS
	     WORD e_ip;       - Valor inicial do registrador IP ( Instrution Pointer )
	     WORD e_cs;       - Valor inicial do registrador CS ( Code Segment )
	     WORD e_lfarlc;   - Offset do fragmento stub do DOS.
	     WORD e_ovno;     - Overlay
	     WORD e_res[4];   - 
	     WORD e_oemid;    - Identificador OEM
	     WORD e_oeminfo;  - Informações OEM
	     WORD e_res2[10]; - 
	     LONG e_lfanew;   - Offset do cabeçalho PE COFF
	} 
	IMAGE_DOS_HEADER;


*Como o cabeçalho do DOS possui um tamanho fixo, seus respectivos campos sempre vão estar em uma posição Fixa no arquivo. Isso se refere aos campos e seu devido tamanho, porém os valores destes campos podem mudar de arquivo para a arquivo.*

---

Detalhes dos campos do IMAGE_DOS_HEADER:
-----------------------------------------


##### e_magic

- É uma WORD (2bytes) que identifica um executável DOS, esse valor é representado em ASCII pela sigla "MZ" ( A sigla 'MZ' quer dizer 'Mark Zbikowsky', que foi um dos idealizadores do MS-DOS ). Essa sigla é um dos dados que o Windows Loader checa, na hora da execução de um programa. Caso ela não exista ou esteja mnodificada, o Windows não reconhece o programa/arquivo como um executável.

##### e_cblp

##### e_cp

##### e_crlc

##### e_cparhdr

##### e_minalloc

##### e_maxalloc

##### e_ss

##### e_sp

##### e_csum

##### e_ip

##### e_cs

##### e_lfarlc

- É uma WORD (2 bytes) que armazena o offset( a posição ) onde está localizado o início do DOS-Stub. 

##### e_ovno

##### e_res

##### e_oemid

##### e_oeminfo

##### e_res2

##### e_lfanew

- O Campo e_lfanew , normalmente fica na posição 0x3c que no caso são os 4 últimos bytes de 64 bytes do IMAGE_DOS_HEADER.

- É uma DWORD(4bytes) que armazena o offset onde está localizado o início do COFF Header(Cabeçalho PE) que contém um sequencia fixa de 4 bytes : 

		54 50 00 00

----







