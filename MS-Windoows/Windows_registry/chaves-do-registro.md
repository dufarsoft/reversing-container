CHAVES DO REGISTRO DO WINDOWS "HKEYS"
=====================================

Caminho para colcoar programas para inicializar no windows

	HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > RunOnce

HKEY_CLASSES_ROOT

- Uma chave mantida por compatibilidade com vers�es do windows anteriores a mesma foi substitu�da pela chave que se encontra em : HKEY_LOCAL_MACHINE > SOFTWARE > Classes


HKEY_CURRENT_USER

- Chave referente ao usu�rio que est� logado no momento no sistema. Altera��es feitas aqui ter�o efeitos apenas no usua�rio que est� logado.


HKEY_LOCAL_MACHINE

- Aqui temos op��es que s�o utilizadas por todos os usu�rios do computador ent�o qualquer altera��o feitas aqui ter�o efeito em todo o computador EM GERAL.
- Temos tamb�m as subchaves : SAM,SOFTWARE,SYSTEM,SECURITY,HARDWARE.


HKEY_USERS

- Uma chave que armazena a listagem de todos usu�rios do sistema. Por exemplo, quando fazemos o logoff � essa chave que traz as informa��es de todos usu�rio a fazer login


HKEY_CURRENT_CONFIG

- Atalho para HK_LOCAL_MACHINE e tamb�m � mantida para compatibilidades com vers�es anteriores do windows.


CRIANDO SCRIPTS PRO REGISTRO DO WINDOWS
========================================

- Podemos escrever os scripts em um documento texto qualquer, mais temos que salva-lo com a extens�o  .reg ( de regedit ).
- Tamb�m temos que setar algumas informa��es no cabecalho do arquivo em que o script ser� escrito, para que o windows entenda que se trata de um script para o registro do sistema.

		Windows Registry Editor Version 5.00

- Nos registros do windows temos as CHAVES que foram mencionadas acima e dentro delas temos as SUBCHAVES que sua vez arnmazena arquivos de configura��o que na maioria das vezes tem os seguintes valores : REG_Z ( Z quer dizer strings "conjunto de caracteres ") e DWORD que s�o uma sequ�ncia de bytes. Na maioria das vezes na tela do regedit temos informa��es desses arquivos que ficam nas subchaves como : Nome,Tipo(Z , DWORD etc..) e Dados.


- Para criar uma nova chave, por exemplo dentro de CURRENT_USER, podemos utilizar um script dessa forma:

		Windows Registry Editor Version 5.00

		[HKEY_CURRENT_USER\MyKey]

- Se por acaso quiser excluir a chave que criamos acima ou at� mesmo outra, utilizamos o opera��o de SUBTRA��O antes da chave principal, o script ficara desse jeito:

		Windows Registry Editor Version 5.00

		[-HKEY_CURRENT_USER\MyKey]


- Tamb�m posso criar uma nova chave j� com um arquivo dentro da mesma, no exemplo um arquivo do tipo texto : 


		Windows Registry Editor Version 5.00

		[HKEY_CURRENT_USER\MyKey]
		*TextArea*=*Eduardo Barbosa*





OTHERS
=======


HLM > SYSTEM > CurrentControlSet > Control > hivelist  =  arquivos respons�veis de montar o a estrutura de pastas do REGEDIT ( registro do windows )

arquivos do hivelsit 

REGISTRY\USER\.DEFAULT : onde fica setado o padr�o de configura��es dos usu�rios.Podemos setar um padr�o os usu�rios a serem criados etcc...

 
REGISTRY\MACHINE\SAM
and
REGISTRY\MACHINE\SECURITY : � onde s�o respons�veis pelos controles de usu�rios e permiss�es para acessar diret�rios,arquivos etc..


REGISTRY\MACHINE\ : Tudo que � par�metro de configura�ao relacionado a SOFTWARES vai estar aqui


REGISTRY\MACHINE\SYSTEM : Configura��es do sistema operacional, ou seja tudo que � par�metro relacionado ao windows vai estar aqui.



REGISTRY\USER\S-1-5-19

REGISTRY\USER\S-1-5-20 : Arquivo onde cont�m as configura��es do usu�rio pr�priamente dito, ou melhor podemos ver apenas os dados do usu�rio que est� logado no momento.


BACKUP DO REGISTRO DO WINDOWS
=============================

- Os arquivos citados acima s�o os que entraram no backup ou seja s�o os fundamentais.

1. Reiniciar o computador apertando F8
2. Escolher a op��o ' Modo de repara��o ' ou mode of Debugin
3. Agora quando chegar na tela System Recovery Options (op��es de repara��o do sistema), escolhemos a �ltima op��o do PROMPT de comandos (cmd)
4. Faremos a copia do registro do windows via prompt da seguinte forma:

	criar uma pasta no diret�rio raiz( c:,d: ou e:) com o seguinte comando:
		md backup-windows
	
	entrar no diret�rio onde est�o os arquivos do registro do windows que precisam ser copiados:
		cd windows\system32\config

	copiar os arquivos do system32\config
		copy SAM d:\backup-windows
		copy DEFAULT d:\backup-windows
		copy SECURITY d:\backup-windows
		copy SOFTWARE d:\backup-windows
		copy SYSTEM d:\backup-windows
	

	agora para restaurar o backup, copiamos os 5 arquivos que foram salvos em d:\backup-windows para o seguinte caminho:
		C:\Windows\system32\config
		yes

