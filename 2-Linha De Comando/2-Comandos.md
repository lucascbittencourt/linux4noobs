# 02 - Comandos básicos

> # cd

O comando `cd` é um acrônimo para "change directory" e serve para navegar do diretório atual para outro especificado em seguida.

Sintaxe:

```console
cd [diretório]
```

Exemplo:

```console
lucashe4rt@He4rt:~$ cd / 
```

* O caractér `/` identifica o diretório raiz do nosso sistema de arquivos.

Resultado:

```console
lucashe4rt@He4rt:/$
```

> # ls

Com o comando `ls` podemos visualizar o conteúdo de um diretório e também informações sobre arquivos, informando dados como nomes de arquivos, permissões, proprietários e datas de criação, além de inúmeras opções para exibir as informações de diversas formas.

Sintaxe:

```console
ls [opções]
```

Algumas opções do `ls`:

* `-a` - Mostra todos os arquivos, incluindo os ocultos. Exemplo:

```console
lucashe4rt@He4rt:~$ ls -a
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
lucashe4rt@He4rt:~$ ls -A
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
lucashe4rt@He4rt:~$ ls -l
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
lucashe4rt@He4rt:~$ ls -m
Desktop, Documents, Downloads, Games, Games-Wine, Images, aur, go
```

* `-n` - Semelhante ao `-l`, porém mostra UID E GID Em vez de nomes de proprietário e grupo. Exemplo:

```console
[23:42:15] lucashe4rt@He4rt:~$ ls -n
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
lucashe4rt@He4rt:~$ ls -p
Desktop/  Documents/  Downloads/  Games/  Games-Wine/  Images/  aur/  go/
```
* `-r` - Ordem reversa. Exemplo:
```console
lucashe4rt@He4rt:~$ ls -r
go  aur  Images  Games-Wine  Games  Downloads  Documents  Desktop
```

*Nós também podemos juntar os comandos, por exemplo `ls -la`*.

> # df

O comando `df` mostra o espaço livre/ocupado de cada partição. Pode ser utilizado junto com várias opções, se for utilizado sozinho, mostrará o espaço usado e disponível de todos os sistemas de arquivos atualmente montados.

Sintaxe:

```console
df [opções]
```

Exemplo:
```console
lucashe4rt@He4rt:~$ df
Filesystem     1K-blocks     Used Available Use% Mounted on
dev              4028428        0   4028428   0% /dev
run              4036824      892   4035932   1% /run
/dev/sda1      114041020 10761904  97443136  10% /
tmpfs            4036824    56924   3979900   2% /dev/shm
tmpfs            4036824        0   4036824   0% /sys/fs/cgroup
tmpfs            4036824        4   4036820   1% /tmp
tmpfs             807364       12    807352   1% /run/user/1001
```
Algumas opções do  `df`:

* `-a` - Inclui sistema de arquivos com 0 (zero) blocos. Exemplo:
```console
lucashe4rt@He4rt:~$ df -a
Filesystem     1K-blocks     Used Available Use% Mounted on
proc                   0        0         0    - /proc
sys                    0        0         0    - /sys
dev              4028428        0   4028428   0% /dev
run              4036824      892   4035932   1% /run
/dev/sda1      114041020 10761900  97443140  10% /
securityfs             0        0         0    - /sys/kernel/security
tmpfs            4036824    47708   3989116   2% /dev/shm
devpts                 0        0         0    - /dev/pts
tmpfs            4036824        0   4036824   0% /sys/fs/cgroup
cgroup2                0        0         0    - /sys/fs/cgroup/unified
cgroup                 0        0         0    - /sys/fs/cgroup/systemd
pstore                 0        0         0    - /sys/fs/pstore
none                   0        0         0    - /sys/fs/bpf
cgroup                 0        0         0    - /sys/fs/cgroup/devices
cgroup                 0        0         0    - /sys/fs/cgroup/hugetlb
cgroup                 0        0         0    - /sys/fs/cgroup/pids
cgroup                 0        0         0    - /sys/fs/cgroup/rdma
cgroup                 0        0         0    - /sys/fs/cgroup/cpuset
cgroup                 0        0         0    - /sys/fs/cgroup/perf_event
cgroup                 0        0         0    - /sys/fs/cgroup/net_cls,net_prio
cgroup                 0        0         0    - /sys/fs/cgroup/freezer
cgroup                 0        0         0    - /sys/fs/cgroup/cpu,cpuacct
cgroup                 0        0         0    - /sys/fs/cgroup/blkio
cgroup                 0        0         0    - /sys/fs/cgroup/memory
systemd-1              0        0         0    - /proc/sys/fs/binfmt_misc
mqueue                 0        0         0    - /dev/mqueue
hugetlbfs              0        0         0    - /dev/hugepages
debugfs                0        0         0    - /sys/kernel/debug
configfs               0        0         0    - /sys/kernel/config
tmpfs            4036824        4   4036820   1% /tmp
tmpfs             807364       12    807352   1% /run/user/1001
```
* `-h` - Mostra o espaço livre/ocupado em MB, KB, GB em vez de bloco. Exemplo:

```console
lucashe4rt@He4rt:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
dev             3.9G     0  3.9G   0% /dev
run             3.9G  892K  3.9G   1% /run
/dev/sda1       109G   11G   93G  10% /
tmpfs           3.9G   47M  3.9G   2% /dev/shm
tmpfs           3.9G     0  3.9G   0% /sys/fs/cgroup
tmpfs           3.9G  4.0K  3.9G   1% /tmp
tmpfs           789M   12K  789M   1% /run/user/1001
```
* `-k` - Lista em Kbyts. Exemplo:
```console
lucashe4rt@He4rt:~$ df -k
Filesystem     1K-blocks     Used Available Use% Mounted on
dev              4028428        0   4028428   0% /dev
run              4036824      892   4035932   1% /run
/dev/sda1      114041020 10762012  97443028  10% /
tmpfs            4036824    47692   3989132   2% /dev/shm
tmpfs            4036824        0   4036824   0% /sys/fs/cgroup
tmpfs            4036824      100   4036724   1% /tmp
tmpfs             807364       12    807352   1% /run/user/1001
```

* `-l` - Somente lista sistema de arquivos locais. Exemplo:
```console
lucashe4rt@He4rt:~$ df -l
Filesystem     1K-blocks     Used Available Use% Mounted on
dev              4028428        0   4028428   0% /dev
run              4036824      892   4035932   1% /run
/dev/sda1      114041020 10761976  97443064  10% /
tmpfs            4036824    47676   3989148   2% /dev/shm
tmpfs            4036824        0   4036824   0% /sys/fs/cgroup
tmpfs            4036824      148   4036676   1% /tmp
tmpfs             807364       12    807352   1% /run/user/1001
```

* `-m` - Lista em Mbytes. Exemplo:
```console
lucashe4rt@He4rt:~$ df -m
Filesystem     1M-blocks  Used Available Use% Mounted on
dev                 3935     0      3935   0% /dev
run                 3943     1      3942   1% /run
/dev/sda1         111369 10510     95160  10% /
tmpfs               3943    47      3896   2% /dev/shm
tmpfs               3943     0      3943   0% /sys/fs/cgroup
tmpfs               3943     1      3943   1% /tmp
tmpfs                789     1       789   1% /run/user/1001
```

* `-T` - Lista o tipo de sistema de arquivos de cada partição. Exemplo:
```console
lucashe4rt@He4rt:~$ df -T 
Filesystem     Type     1K-blocks     Used Available Use% Mounted on
dev            devtmpfs   4028428        0   4028428   0% /dev
run            tmpfs      4036824      892   4035932   1% /run
/dev/sda1      ext4     114041020 10761984  97443056  10% /
tmpfs          tmpfs      4036824    47708   3989116   2% /dev/shm
tmpfs          tmpfs      4036824        0   4036824   0% /sys/fs/cgroup
tmpfs          tmpfs      4036824      116   4036708   1% /tmp
tmpfs          tmpfs       807364       12    807352   1% /run/user/1001
```
> # cat

O comando `cat`, derivação da palavra concatenate, permite que a gente crie, una e exiba arquivos no formato padrão de tela ou em outro arquivo, entre outras funcionalidades.

Sintaxe:

```console
cat [opção] [arquivo]
```
Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cat arquivo.txt 
da estrela ai se vc ta curtindo
manda pros amigo tb
vc é d+++
```
Algumas opções do comando `cat`:

* `-E` - Marca o término de linha mostrando o caractere __$__ ao final de cada uma delas. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cat -E arquivo.txt 
da estrela ai se vc ta curtindo$
manda pros amigo tb$
vc é d+++$
```

* `-n` - Mostra a quantidade de linas do arquivo. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ cat -n arquivo.txt 
     1	da estrela ai se vc ta curtindo
     2	manda pros amigo tb
     3	vc é d+++
```

* `-v` - Exibe caracteres não exibíveis. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ cat -v arquivo.txt 
da estrela ai se vc ta curtindo
manda pros amigo tb
vc M-CM-) d+++
```

* `-T` - Exibe tabulação mostradas como __^I__. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ cat -T arquivo.txt 
da estrela ai se vc ta curtindo
manda pros amigo tb
vc é d+++




^ISegue o melhor grupo de desenvolvimento lá
^Ino 
^I
^Itwitter: @He4rtDevs
```

* `-s` - Remove linhas repetidas em branco. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ cat -s arquivo.txt 
da estrela ai se vc ta curtindo
manda pros amigo tb
vc é d+++

	Segue o melhor grupo de desenvolvimento lá
	no 
	
	twitter: @He4rtDevs
```

*Obs: essa opção mantém uma linha vazia e remove as linhas repetidas em branco.*

* `-b` - Numera as linhas que possuem algum conteúdo. Exemplo:
```console
lucashe4rt@He4rt-PC:~$ cat -b arquivo.txt 
     1	da estrela ai se vc ta curtindo
     2	manda pros amigo tb
     3	vc é d+++




     4		Segue o melhor grupo de desenvolvimento lá
     5		no 
     6		
     7		twitter: @He4rtDevs
```
*Obs: essa opção sobrescreve a opção `-n`.*

* `tac` - Exibe o conteúdo do arquivo em ordem contrária, da primeira à ultima linha. Exemplo:

```console
twitter: @He4rtDevs
	
	no 
	Segue o melhor grupo de desenvolvimento lá




vc é d+++
manda pros amigo tb
da estrela ai se vc ta curtindo
```
> # man

> # find

> # date

> # kill

> # ifconfig

> # exit

---
## Referencias:
[Devmedia - comando importantes linux](https://www.devmedia.com.br/comandos-importantes-linux/23893)

[vivaolinux - usando o comando df](https://www.vivaolinux.com.br/dica/Usando-o-comando-df)