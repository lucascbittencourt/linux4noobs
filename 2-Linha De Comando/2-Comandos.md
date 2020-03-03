> # CD

O comando `cd` é um acrônimo para "change directory" e serve para navegar do diretório atual para outro especificado em seguida.

Sintaxe:

```console
cd [diretório]
```

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cd / 
```

* O caractér `/` identifica o diretório raiz do nosso sistema de arquivos.

Resultado:

```console
lucashe4rt@He4rt-PC:/$
```

> # LS

Com o comando `ls` podemos visualizar o conteúdo de um diretório e também informações sobre arquivos, informando dados como nomes de arquivos, permissões, proprietários e datas de criação, além de inúmeras opções para exibir as informações de diversas formas.

Sintaxe:

```console
ls [opções]
```

Algumas opções do `ls`:

* `-a` - Mostra todos os arquivos, incluindo os ocultos. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ls -a
.                .bashrc     .java               .themes     Downloads
..               .cache      .local              .viminfo    Games
.ICEauthority    .config     .mozilla            .vscode     Games-Wine
.PhpStorm2019.3  .eclipse    .mysql_history      .wget-hsts  Images
.Xauthority      .gitconfig  .node_repl_history  .wine32     aur
.backgrounds     .gitkraken  .npm                .yarn       go
.bash_history    .gnome      .pki                .yarnrc     
.bash_logout     .gnupg      .pulse-cookie       Desktop
.bash_profile    .icons      .swt                Documents
```

* `-A` - Semelhante ao `-a`, mas não mostra o diretório corrente (`.`) ou o diretório acima (`..`). Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ls -A
.ICEauthority    .config     .mozilla            .vscode     Games-Wine
.PhpStorm2019.3  .eclipse    .mysql_history      .wget-hsts  Images
.Xauthority      .gitconfig  .node_repl_history  .wine32     aur
.backgrounds     .gitkraken  .npm                .yarn       go
.bash_history    .gnome      .pki                .yarnrc     
.bash_logout     .gnupg      .pulse-cookie       Desktop
.bash_profile    .icons      .swt                Documents
.bashrc          .java       .themes             Downloads
.cache           .local      .viminfo            Games
```

* `-i` - Mostra o número do inode de cada arquivo na primeira coluna. Exemplo:

```console 
1195906 Desktop     660779 Games        396790 aur
1319602 Documents  2630465 Games-Wine  2890994 go
1200375 Downloads  1314860 Images      
```

* `-l` - Formato longo, mostra permissões, número de links, propietário, grupo, tamanho, data de modificação e nome do arquivo. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ ls -l
total 1032
drwxrwxr-x  2 lucashe4rt lucashe4rt    4096 Feb 23 11:57 Desktop
drwxr-xr-x 13 lucashe4rt lucashe4rt    4096 Feb 29 23:38 Documents
drwx------  2 lucashe4rt lucashe4rt    4096 Feb 27 15:26 Downloads
drwxr-xr-x  2 lucashe4rt lucashe4rt    4096 Feb 29 22:27 Games
drwxr-xr-x  3 lucashe4rt lucashe4rt    4096 Feb 29 22:20 Games-Wine
drwxr-xr-x  3 lucashe4rt lucashe4rt    4096 Feb 27 22:38 Images
drwxr-xr-x  3 lucashe4rt lucashe4rt    4096 Feb 23 11:20 aur
drwxr-xr-x  3 lucashe4rt lucashe4rt    4096 Feb 29 16:37 go
```

* `-m` - Arquivos listados em sequência, separados por vírgula. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ ls -m
Desktop, Documents, Downloads, Games, Games-Wine, Images, aur, go
```

* `-n` - Semelhante ao `-l`, porém mostra UID E GID Em vez de nomes de proprietário e grupo. Exemplo:

```console
[23:42:15] lucashe4rt@He4rt-PC:~$ ls -n
total 36
drwxrwxr-x  2 1000 1000 4096 Feb 23 11:57 Desktop
drwxr-xr-x 13 1000 1000 4096 Feb 29 23:38 Documents
drwx------  2 1000 1000 4096 Feb 27 15:26 Downloads
drwxr-xr-x  2 1000 1000 4096 Feb 29 22:27 Games
drwxr-xr-x  3 1000 1000 4096 Feb 29 22:20 Games-Wine
drwxr-xr-x  3 1000 1000 4096 Feb 27 22:38 Images
drwxr-xr-x  3 1000 1000 4096 Feb 23 11:20 aur
drwxr-xr-x  3 1000 1000 4096 Feb 29 16:37 go
```

* `-o` - Semelhante ao `-l`, porém não mostra o grupo do arquivo. Exemplo:
```console
total 36
drwxrwxr-x  2 lucashe4rt 4096 Feb 23 11:57 Desktop
drwxr-xr-x 13 lucashe4rt 4096 Feb 29 23:38 Documents
drwx------  2 lucashe4rt 4096 Feb 27 15:26 Downloads
drwxr-xr-x  2 lucashe4rt 4096 Feb 29 22:27 Games
drwxr-xr-x  3 lucashe4rt 4096 Feb 29 22:20 Games-Wine
drwxr-xr-x  3 lucashe4rt 4096 Feb 27 22:38 Images
drwxr-xr-x  3 lucashe4rt 4096 Feb 23 11:20 aur
drwxr-xr-x  3 lucashe4rt 4096 Feb 29 16:37 go
```
* `-p` - Mostra uma barra(/) na frente de nomes de diretórios. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ls -p
Desktop/  Documents/  Downloads/  Games/  Games-Wine/  Images/  aur/  go/
```
* `-r` - Ordem reversa. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ ls -r
go  aur  Images  Games-Wine  Games  Downloads  Documents  Desktop
```

*Nós também podemos juntar os comandos, por exemplo `ls -la`*.