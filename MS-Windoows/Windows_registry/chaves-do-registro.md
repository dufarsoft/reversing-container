CHAVES DO REGISTRO DO WINDOWS "HKEYS"
=====================================

Caminho para colcoar programas para inicializar no windows

	HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > RunOnce

HKEY_CLASSES_ROOT

- Uma chave mantida por compatibilidade com versões do windows anteriores a mesma foi substituída pela chave que se encontra em : HKEY_LOCAL_MACHINE > SOFTWARE > Classes


HKEY_CURRENT_USER

- Chave referente ao usuário que está logado no momento no sistema. Alterações feitas aqui terão efeitos apenas no usuaário que está logado.


HKEY_LOCAL_MACHINE

- Aqui temos opções que são utilizadas por todos os usuários do computador então qualquer alteração feitas aqui terão efeito em todo o computador EM GERAL.
- Temos também as subchaves : SAM,SOFTWARE,SYSTEM,SECURITY,HARDWARE.


HKEY_USERS

- Uma chave que armazena a listagem de todos usuários do sistema. Por exemplo, quando fazemos o logoff é essa chave que traz as informações de todos usuário a fazer login


HKEY_CURRENT_CONFIG

- Atalho para HK_LOCAL_MACHINE e também é mantida para compatibilidades com versões anteriores do windows.


CRIANDO SCRIPTS PRO REGISTRO DO WINDOWS
========================================

- Podemos escrever os scripts em um documento texto qualquer, mais temos que salva-lo com a extensão  .reg ( de regedit ).
- Também temos que setar algumas informações no cabecalho do arquivo em que o script será escrito, para que o windows entenda que se trata de um script para o registro do sistema.

		Windows Registry Editor Version 5.00

- Nos registros do windows temos as CHAVES que foram mencionadas acima e dentro delas temos as SUBCHAVES que sua vez arnmazena arquivos de configuração que na maioria das vezes tem os seguintes valores : REG_Z ( Z quer dizer strings "conjunto de caracteres ") e DWORD que são uma sequência de bytes. Na maioria das vezes na tela do regedit temos informações desses arquivos que ficam nas subchaves como : Nome,Tipo(Z , DWORD etc..) e Dados.


- Para criar uma nova chave, por exemplo dentro de CURRENT_USER, podemos utilizar um script dessa forma:

		Windows Registry Editor Version 5.00

		[HKEY_CURRENT_USER\MyKey]

- Se por acaso quiser excluir a chave que criamos acima ou até mesmo outra, utilizamos o operação de SUBTRAÇÃO antes da chave principal, o script ficara desse jeito:

		Windows Registry Editor Version 5.00

		[-HKEY_CURRENT_USER\MyKey]


- Também posso criar uma nova chave já com um arquivo dentro da mesma, no exemplo um arquivo do tipo texto : 


		Windows Registry Editor Version 5.00

		[HKEY_CURRENT_USER\MyKey]
		*TextArea*=*Eduardo Barbosa*





OTHERS
=======


HLM > SYSTEM > CurrentControlSet > Control > hivelist  =  arquivos responsáveis de montar o a estrutura de pastas do REGEDIT ( registro do windows )

arquivos do hivelsit 

REGISTRY\USER\.DEFAULT : onde fica setado o padrão de configurações dos usuários.Podemos setar um padrão os usuários a serem criados etcc...

 
REGISTRY\MACHINE\SAM
and
REGISTRY\MACHINE\SECURITY : É onde são responsáveis pelos controles de usuários e permissões para acessar diretórios,arquivos etc..


REGISTRY\MACHINE\ : Tudo que é parâmetro de configuraçao relacionado a SOFTWARES vai estar aqui


REGISTRY\MACHINE\SYSTEM : Configurações do sistema operacional, ou seja tudo que é parâmetro relacionado ao windows vai estar aqui.



REGISTRY\USER\S-1-5-19

REGISTRY\USER\S-1-5-20 : Arquivo onde contém as configurações do usuário própriamente dito, ou melhor podemos ver apenas os dados do usuário que está logado no momento.


BACKUP DO REGISTRO DO WINDOWS
=============================

- Os arquivos citados acima são os que entraram no backup ou seja são os fundamentais.

1. Reiniciar o computador apertando F8
2. Escolher a opção ' Modo de reparação ' ou mode of Debugin
3. Agora quando chegar na tela System Recovery Options (opções de reparação do sistema), escolhemos a última opção do PROMPT de comandos (cmd)
4. Faremos a copia do registro do windows via prompt da seguinte forma:

	criar uma pasta no diretório raiz( c:,d: ou e:) com o seguinte comando:
		md backup-windows
	
	entrar no diretório onde estão os arquivos do registro do windows que precisam ser copiados:
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

