# Aonde estão os dados

## Boot

Agora vamos falar um pouco sobre aonde estão os dados do seu Sistema. Vamos começar com o diretorio boot, ele é muito importante e geralmente fica em uma partição separada do disco, já que é la que fica o arquivo do Kernel, para acessar ele utlize o comando.

```shell
cd /
cd boot
ls
```

Aqui nos vamos ter um arquivo chamado vmlinuz, esse arquivo é o Kernel do seus sistema, que é carregado pelo gerenciador de boot da maquina e ele é o coração de todoo sistema operacional. Também vamos ter o initramfs, que ajuda o Kernel montando um pseudo sistema de arquivos para poder carregar alguns modulos do Kernel. E por ultimo vamos ter os arquivos do Grub, que é o gerenciador de boot padrão do Linux

## Proc

Para acessar esse diretorio execute os comandos abaixo.

```shell
cd /
cd proc
```

O diretorio proc não existe no disco, ele é um pseudo sistema de arquivos, e o conteudo desse diretorio é o que mantém diversos arquivos de configurações e também informações de funcionamento do Kernel do sistema. Ele cria um numero para cada um dos processos em execução, aonde você pode entrar em cada um para obter informação do programa que está em execução, você também pode entrar no diretorio meminfo para obter infomações de memoria.

## Dev

Para acessar esse diretorio execute os comandos abaixo.

```shell
cd /
cd dev
```

Esse diretorio abriga todos os dispositivos que estão conectados no seu computador, no Linux tudo são arquivos, então ele cria um arquivo para cada disposito que ele reconhecer no seu computador, seja ele um pen drive, moden ou hd externo. É importante falar que os discos SATA são geramente identificados como 'sa', e acabam ficando em uma ordem parecida com

* sda1
* sda 2

## SYS

Para acessar esse diretorio execute os comandos abaixo.

```shell
cd /
cd sys
```

Aqui temos outro pseudo sistema de arquivos muito parecido com Proc. O /sys mantém as informações do sistema , mas organizado por categorias ou tipos. Ele é mantido pelo sistema de reconhecimento de Hardware do Linux.

## LOG


Para acessar esse diretorio execute os comandos abaixo.

```shell
cd ../
cd /var/log
```

Por ultimo vamos falar sobre log, o linux mantem um sistema de log, aonde se mantem informação sobre o que aconteceu e o que esta acontecendo na maquina. E é aqui aonde os logs do sistema moram, e aqui nos temos um arquivo especial chamado dmesg, que é aonde se tem as mensagens do Kernel, se você der um CAT nele vai ver todas as informações da maquina desde quando ela foi ligada.

# Processos

## PID

Agora vamos nos aprofundar mais nos processos do Linux, mas antes de falar dos comandos que lidam com esses processos precisamos falar sobre o PID(Process ID), cada processo vai receber um numero de identificação unico, o primeiro processo init/systemd sempre terá o PID1. Para os outros o numero é incrementado quando mais processos vão sendo executados

## User ID e GroupID

Um processo também sempre vai ter um UserID e um GroupID, os processos precisam ser executados com os privilégios de uma conta ou grpo associado a ele, isso é importante pois assim o sistema consegue determinar e gerenciar o acesso aos recursos. 

## Processo Pai

Todos processos menos o init/systemd são executados de forma recursiva, ou seja, possuem um processo pai que vai depender de outro processo e por ai vai. Caso o processo pai termine a execução antes do processo filho, o init/systemd vai "cuidar" do processo filho.

## Sinais

Os sinais são utilizados pelo Kernel, processos ou usuários, para avisar um determinado processo sobre algum evento particular. Eles funcionam como uma "interrupção de software", e com isso os processos tomam alguma ação de acordo com o sinal recebido.

# Comandos 

## PS

```shell
ps
```
Esse comando vai mostrar os processos que estão em execução, pelo seu usuário ou terminal.

Se você usar o parametro a, ele vai mostrar todos os processos que estão ou não ligados a o seu usuario ou ao terminal.

```shell
ps a
```

Agora, se você usar o parametro au, ele vai mostrar bem mais informações sobre os processos, mas ainda ligados ao seu usuário.

```shell
ps au
```

Por ultimo, nos podemos usar o parametro aux, para mostrar todos os processos de todos os usuários e terminais. 

```shell
ps aux
```






