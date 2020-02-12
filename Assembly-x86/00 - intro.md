Assembly Language Concepts
---------------------------


- O ponto mais básico para definir a linguagem assembly: É UMA CLASSE DE LÍNGUAGENS, não uma linguagem. Cada plataforma de computador possui uma linguagem de montagem própria, que geralmente é bem diferente de todas as outras.

- Outro conceito importante, é o código de máquina (geralmente chamado de código binário ou código de objeto). As pessoas às vezes cometem o erro de pensar que o código de máquina é "mais rápido" e "de nível inferior". Isso é um equívoco: código de máquina e linguagem de montagem são duas reações diferentes da mesma coisa. Uma CPU lê o código da máquina, que nada mais é que seqüências de bits que contêm uma lista de instruções para a CPU executar. A linguagem de montagem é simplesmente uma representação textual desses bits. Nomeamos elementos nessas sequências de código para torná-los legíveis por humanos. Em vez de números hexadecimais enigmáticos, podemos ver o nome da instrução textual, como MOV (mover), XCHG (troca) e assim por diante.

- Cada comando assembly é representado por um número, chamado código de operação ou "opcode". O código de objeto é essencialmente uma seqüência de opcodes e outros números usados ​​em conexão com os opcodes para executar operações. A CPU lê constantemente o código-objeto da memória, decodifica-o e age com base nas instruções incorporadas. Quando os desenvolvedores escrevem código em linguagem assembly (uma ocorrência bastante rara nos dias de hoje), eles usam um programa assembler para traduzir o código da linguagem assembly textual em código binário, que pode ser decodificado por uma CPU. Na outra direção e mais relevante para a nossa narrativa, um desasembly faz exatamente o oposto. Ele lê o código do objeto e gera o mapeamento textual para cada instrução nele. Essa é uma operação relativamente simples de executar porque a linguagem de montagem textual é simplesmente uma representação diferente do código do objeto. Os disassemblers são ferramentas fundamentais para os reversores.


### Próximos conceitos de base:

!Instruções[] :




----

_Fontes_

Secrets of Reverse Engineering by Eldad Eilam