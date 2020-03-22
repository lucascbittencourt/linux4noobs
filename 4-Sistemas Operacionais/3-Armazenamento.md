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

Por ultimo vamos falar sobre log, o linux mantem um sistema de log, aonde se mantem informação sobre o que aconteceu e o que esta acontecendo na maquina. E é aqui aonde os logs do sistema moram, e aqui nos temos um arquivo especial chamado dmesg, que é aonde se tem as mensagens do Kernel, se você der um CAT nele vai ver todas as informações da maquina desde quando ela foi ligada 

