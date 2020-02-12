Alterações/Implementações possíveis na chave de registro HKEY_LOCAL_MACHINE
----------------------------------------------------------------------------


#### No seguinte registro, podemos programar uma DLL/EXE para ser carregado juntamente a qualquer aplicativo que é executado. Uma vez que essa implementação é realizada, toda vez que um aplicativo é executado; também será executado em pararelo a .dll ou .exe que foi setado como valor.


		HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows

		AppInit_DLLs
		value = CAMINHO ONDE A DLL SE ENCONTRA


#### No seguinte registro, é possível alterar a imagem de fundo das propriedades do computador.


		HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OEMInformation



#### Os seguintes registros, devem ser deletados quando precisarmos excluir uma impressora e não conseguimos efetuar a exclusão de maneira convencional pela tela de "Dispositivos e Impressoras" ( Certifique se os registros a serem deletados, tem o nome da impressora como referencia ou valor ) .


		HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\

		HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Providers\ LanMan Print Services\Servers\Printers\