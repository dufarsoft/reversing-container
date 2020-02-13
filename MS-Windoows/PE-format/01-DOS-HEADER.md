## DOS Header ( Cabeçalho MZ do DOS )

- O arquivo PE começa com o DOS Header, que sempre ocupa os primeiros 64bytes do arquivo.
- Abaixo a estrutura oficial do DOS Header:

			IMAGE_DOS_HEADER STRUCT
			  e_magic    - WORD : Assinatura "MZ" ( DOS Signature )
			  e_cblp     - WORD : Tamanho da última página.
			  e_cp       - WORD : Total de páginas.
			  e_crlc     - WORD : Itens de relocação.
			  e_cparhdr  - WORD : Tamanho do cabeçalho DOS.
			  e_minalloc - WORD : Tamanho mínimo da memória.
			  e_maxalloc - WORD : Tamanho máximo da memória.
			  e_ss       - WORD : Valor inicial do registrador SS ( Stack Segment )
			  e_sp       - WORD : Valor inicial do registrador SP ( Stack Pointer )
			  e_csum     - WORD : Checksum do cabeçalho DOS
			  e_ip       - WORD : Valor inicial do registrador IP ( Instrution Pointer )
			  e_cs       - WORD : Valor inicial do registrador CS ( Code Segment )
			  e_lfarlc   - WORD : Offset do fragmento stub do DOS.
			  e_ovno     - WORD : Overlay
			  e_res      - WORD : 
			  e_oemid    - WORD : Identificador OEM
			  e_oeminfo  - WORD : Informações OEM
			  e_res2     - WORD : 
			  e_lfanew   - DWORD: Offset do cabeçalho PE COFF

			IMAGE_DOS_HEADER ENDS;


Detalhes dos itens que ficam dentro do IMAGE_DOS_HEADER:
--------------------------------------------------------


##### e_magic

- É um valor de 4 bytes( DWORD ) que identifica um executável DOS, esse valor é representado em ASCII pela sigla "MZ" ( A sigla 'MZ' quer dizer 'Mark Zbikowsky', que foi um dos idealizadores do MS-DOS ). Essa sigla é um dos dados que o Windows Loader checa, na hora de rodar um programa. Caso ela não exista ou esteja mnodificada, o Windows não reconhece o programa/arquivo como um executável.

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

- É um valor de 2 bytes ( WORD ) que armazena o offset( a posição ) onde está localizado o início do DOS-Stub. 

##### e_ovno

##### e_res

##### e_oemid

##### e_oeminfo

##### e_res2

##### e_lfanew

- É um valor de 4 bytes ( DWORD ) que armazena o offset( a posição ) onde está localizado o início do Coff Header ( cabeçalho PE ).