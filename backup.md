# Aq tem umas coisas q da pra reutilizar pq foram tirados do outro

iremos aprender nosso primeiro comando que irá nos mover para pasta raiz do sistema operacional. Para isto, abra um terminal e digite:

```console
lucashe4rt@He4rt-PC:~$ cd / 
```

* O comando `cd` é um acrônimo para "change directory" e serve para navegar do diretório atual para outro especificado em seguida.
* O caractér `/` identifica o diretório raiz do nosso sistema de arquivos.

Resultado:

```console
lucashe4rt@He4rt-PC:/$
```

Como podemos perceber mudou uma coisa na linha de comando de nosso terminal. O caractér `~` foi substituído pelo `/`, ou seja, nós mudamos do diretório **home** para o diretório **raiz**.

* O caractér `~`, por padrão, identifica o nosso diretório **home**, ou seja, a pasta base do nosso usuário (o diretório **home** é onde esta nossos diretórios de Downloads, Documentos, Desktop, etc.).

*Obs: toda vez que navegarmos pelos diretórios este espaço entre o `:` e o `$` mostrará em qual diretório estamos.* 

----
Para voltarmos para o diretório **home**, basta digitar:

```console
lucashe4rt@He4rt-PC:/$ cd ~
``` 

ou simplesmente:

```console
lucashe4rt@He4rt-PC:/$ cd
```

Resultado: 

```console
lucashe4rt@He4rt-PC:~$
```

e pronto ja estaremos no diretório **home** novamente.


```console
lucashe4rt@He4rt-PC:/$ ls
```

* O comando `ls`, nome derivado da palavra "list", exibe quais são os arquivos existentes na nossa pasta corrente, ou seja, da nossa pasta atual, em formato de coluna.

Para melhorar a visibilidade vamos aprender nosso terceiro comando que é uma variação do último, o `ls -l` ou `ll`.

*Obs: o comando `ll`, que é um **ALIAS** de `ls -l` com mais algumas opções, não é padrão, ou seja, não são todas as distribuições que tem esta opção ja definida.*

```console
lucashe4rt@He4rt-PC:/$ ls -l
```
ou 
```console
lucashe4rt@He4rt-PC:/$ ll
```
* O parametro `-l` do comando `ls` serve para exibir os arquivos em formato de lista, mostrando, respectivamente as permissões, usuário que criou, qual grupo pertence, tamanho do arquivo e a ultima modificação do arquivo.

Cada cor representa um tipo de arquivo (a cor pode ser configuravel):

* Azul escuro são os diretórios;
* Verde é um arquivo executavel e com todas persmissões de sistema (escrita, leitura e acesso);
* Azul claro são diretórios links, que faz referência a outro arquivo ou diretório em outra localização.

* Os diretórios do tipo link podem ser identificados pela letra "l" junto a suas permissões e são divididos em dois tipos, **Simbólico e HardLink**.

----
Para sairmos do diretório **bin** e voltarmos para **raiz** vamos utilizar:

```console
lucashe4rt@He4rt-PC:bin/$ cd ..
```
* O parametro `..` significa que estamos voltando um diretório para cima, neste caso o diretório acima é o **/**

ou também podemos optar por:

```console
lucashe4rt@He4rt-PC:bin/$ cd /
```

Resultado:

```console
lucashe4rt@He4rt-PC:/$
```