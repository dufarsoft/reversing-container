PE Format 	
==========

- A sigla PE vem de "Portable Executable", a Microsoft criou um padrão para estruturar os binários do SO, que tornou-se capaz de fazer um binário rodar em qualquer versão do Windows.

- O formato PE, tem uma estrutura de dados que encapsula informações necessárias para que o Loader do SO consiga identificar que se trata de um binário do Windows na hora de  carregar-lo. Então esse é o formato "padrão" de como deve ser composto um binário do Windows. ( como por exemplo, os binários : .exe , .dll, .cpl, .sys, ocx etc..)

- Um arquivo PE consiste em vários cabeçalhos e seções que informam ao Linker como mapear o binário em memória.

- Uma Imagem do Executável(.exe), consiste em várias regiões diferentes; cada uma das quais requer proteção de memória diferentes; portanto o início de cada uma dessas seções do binário PE deve estar alinhada com o limite de uma página. Uma das partes do Linker é mapear cada seção para a memória individualmente e atribuir permissões corretas as regiões resultantes, de acordo com o que está informado nos cabeçalhos.

- Uma característica interessante sobre os arquivos PE é que na maioria das vezezs eles são armazenados na memória da mesma forma que eles ficam em disco, mantendo a estrutura no arquivo praticamente idêntica nos dois casos.


![Imgur](https://i.imgur.com/TsO7N0W.png)



- Cada campo possui seu devido TIPO, que também já define seu respectivo tamanho.

_Exemplo : Se dissermos que o primeiro cabeçalho do arquivo é do tipo WORD, estamos afirmando que o mesmo tem 2 bytes de tamanho_.

- Há também campos do arquivo PE, que possuem o que chamamos de Máscara de bits. Nestes campos, cada bit de seus Bytes podem significar alguma coisa. Por exemplo o campo Characteristics do formato PE.
