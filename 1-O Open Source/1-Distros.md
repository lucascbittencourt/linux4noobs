# Distribuições Linux

Sejam bem vindos ao curso de Linux da [He4rt Developers](discord.io/He4rt), aqui nos vamos desbravar esse mundo temido por alguns desenvolvedores e amado por muitos. Veremos tópicos que abrangem desde o mais básico da CLI até tópicos avançados como Segurança do Sistemas.

Para começar preciso explicar uma coisa, o sistemas do Pinguim é um sistema modular, que é composto por varias partes que combinam entre si. Essas partes são compostas desde Softwares que se comunicam com o Hardware diretamente até Interfaces, mas não se assuste, vamos explicar tudo aqui, vamos passar por todos os tópicos abaixo.

* Kernel
* Grenciador de Pacotes
* Drivers
* Ferramentas GNU
* Shell

Só para lembrar, coisas como um ambiente Desktop não precisam estar presente em uma distribuição, mas agora vamos lá!

## Kernel

O Kernel é a central do Sistema Operacional da maior parte dos computadores, ele é como se fosse uma ponte que faz a ligação entre os seus aplicativos e o processamento feito no nível de Hardware. As responsabilidades mais básicas do Kernel são; Gerenciamento De Processos, Gerenciamento De Memoria, Gerenciamento De Dispositivos e Chamadas Do Sistema.

## Gerenciador De Pacotes

Resumidamente um gerenciador de pacotes são feramentas que automatizam o processo de instalação, atualização e remoção de aplicativos de um Sistema Operacional. Suas principais funções são; Verificar checksums, Verificar a assinatura digital e Gerir as dependências para ter certeza de que um pacote vai ter todas as suas dependências necessárias já que instalar um aplicativo funciona de maneira [recursiva](https://pt.wikipedia.org/wiki/Recursividade_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)). Alguns famosos que podemos citar são o Apt, o Yay e o DNF.

## Drivers

A função de um Driver é diminuir a abstração no contexto de Hardware e Software para que o Software não tenha problema ao interagir com o Hardware. Um Driver não é um processo gerado pelo Sistema Operacional, mas sim uma tabela com informações sobre cada periférico. Em resumo, eles são pequenos programas que fazem a comunicação entre o Sistema Operacional e o seu Hardware.

## Ferramentas GNU

As ferramentas GNU fazem parte de um conjunto feito pelo [Projeto GNU](https://pt.wikipedia.org/wiki/GNU), esse conjunto forma um sistema que é usado para desenvolver aplicações e sistemas operacionais. Essas ferramentas são:

* GCC, um conjunto de compiladores de linguagens como; Java, C, Fortran e Pascal.

* GNU make, um utilitário que compila automaticamente programas e bibliotecas. 

* GNU Binutils, um conjunto de ferramentas de programação para criar e gerenciar programas binários, arquivos de objetos, bibliotecas, dados de perfil e código-fonte de montagem.

* GNU Debugger, mais conhecido por GDB, é um depurador de GNU.

* GNU Autoconf, é uma ferramenta para a produção de scripts shell.

## Shell 

O Shell Do Unix é um interpretador de linha de comando(melhor explicado na proxima parte). O usuário indica a operação do computador pela entrada de comandos para o Shell executar ou então cria scripts de texto ou coisa parecida. Agora no começo não precisa se preocupar muito com isso, mas se você quer dar ao seu terminal uma cara mais bonita vou deixar algumas recomendações abaixo.

* ZSH - Oh My Zsh
* Fish - Oh My Fish


