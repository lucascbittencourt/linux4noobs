# 02 - Comandos básicos

## Contéudo do artigo

[cd](#cd)<br>
[ls](#ls)<br>
[df](#df)<br>
[cat](#cat)<br>
[ps](#ps)<br>
[kill](#kill)<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

> ## cd

O comando `cd` é um acrônimo para "change directory" e serve para navegar do diretório atual para outro especificado em seguida.

Sintaxe:

```console
cd [diretório]
```

Exemplo:

```console
lucashe4rt@He4rt:~$ cd /
```

* O caractere `/` identifica o diretório raiz do nosso sistema de arquivos.

Resultado:

```console
lucashe4rt@He4rt:/$
```

> ## ls

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

> ## df

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

* `-k` - Lista em Kbytes. Exemplo:

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

> ## cat

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

* `-n` - Mostra a quantidade de linhas do arquivo. Exemplo:

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

> ## ps

O comando `ps` exibe informações sobre os processos que estão executando na máquina.

Sintaxe:

```console
ps [opções]
```

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps
    PID TTY          TIME CMD
  14461 pts/0    00:00:00 bash
  14466 pts/0    00:00:00 ps
```

Algumas opções do comando `ps`:

* `-a` - Mostra os processos de todos os usuários. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -a
    PID TTY          TIME CMD
  14631 pts/0    00:00:00 ps
```

* `-A` ou `-e` - Mostra todos os processos. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -e
    PID TTY          TIME CMD
      1 ?        00:00:01 systemd
      2 ?        00:00:00 kthreadd
      3 ?        00:00:00 rcu_gp
      4 ?        00:00:00 rcu_par_gp
      6 ?        00:00:00 kworker/0:0H-kblockd
      8 ?        00:00:00 mm_percpu_wq
      9 ?        00:00:03 ksoftirqd/0
     10 ?        00:00:00 rcuc/0
     11 ?        00:00:14 rcu_preempt
     12 ?        00:00:00 rcub/0
     13 ?        00:00:00 migration/0
     14 ?        00:00:00 idle_inject/0
     16 ?        00:00:00 cpuhp/0
     17 ?        00:00:00 cpuhp/1
     18 ?        00:00:00 idle_inject/1
     19 ?        00:00:00 migration/1
     20 ?        00:00:00 rcuc/1
     21 ?        00:00:03 ksoftirqd/1
     23 ?        00:00:00 kworker/1:0H-kblockd
     24 ?        00:00:00 cpuhp/2
     25 ?        00:00:00 idle_inject/2
     26 ?        00:00:00 migration/2
     27 ?        00:00:00 rcuc/2
  14461 pts/0    00:00:00 bash
  14721 pts/0    00:00:00 ps
```

*obs: eu removi alguns processos para o exemplo não tomar um espaço muito grande na tela.*

* `-f` - Mostra a árvore de execução de comandos. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -f
UID          PID    PPID  C STIME TTY          TIME CMD
lucashe+   14461   14455  0 11:10 pts/0    00:00:00 bash
lucashe+   14959   14461  0 11:17 pts/0    00:00:00 ps -f
```

* `-g [grupo]` - Mostra os processos de um determinado grupo. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -g lucashe4rt
    PID TTY          TIME CMD
    607 ?        00:00:00 systemd
    608 ?        00:00:00 (sd-pam)
    614 ?        00:00:03 xfce4-session
    619 ?        00:00:19 dbus-daemon
    645 ?        00:00:00 gvfsd
    650 ?        00:00:00 gvfsd-fuse
    662 ?        00:00:00 at-spi-bus-laun
    668 ?        00:00:00 dbus-daemon
    670 ?        00:00:00 xfconfd
    676 ?        00:00:01 at-spi2-registr
    695 ?        00:00:00 ssh-agent
    698 ?        00:00:01 gpg-agent
    721 ?        00:21:34 pulseaudio
    722 ?        00:00:01 xfsettingsd
    743 ?        00:00:23 xfce4-panel
    752 ?        00:00:00 Thunar
    757 ?        00:00:03 xfdesktop
    768 ?        00:00:04 xfce4-power-man
    769 ?        00:10:09 pulseeffects
    772 ?        00:00:00 polkit-gnome-au
    774 ?        00:00:00 nm-applet
    781 ?        00:00:03 xfce4-screensav
    788 ?        00:00:00 gvfs-udisks2-vo
    796 ?        00:00:01 xfce4-notifyd
    816 ?        00:00:00 gsettings-helpe
    834 ?        00:00:00 dconf-service
    837 ?        00:00:01 panel-6-systray
    838 ?        00:00:49 panel-8-pulseau
    839 ?        00:00:00 panel-4-actions
    840 ?        00:00:01 panel-7-whisker
   5835 ?        00:02:15 xfwm4
  14455 ?        00:00:03 xfce4-terminal
  14461 pts/0    00:00:00 bash
  15181 pts/0    00:00:00 ps
```

* `-x` - Mostra os processos que não foram iniciados no console. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -x
    PID TTY      STAT   TIME COMMAND
    607 ?        Ss     0:00 /usr/lib/systemd/systemd --user
    608 ?        S      0:00 (sd-pam)
    614 ?        Sl     0:04 xfce4-session
    619 ?        Ss     0:19 /usr/bin/dbus-daemon --session --address=systemd: -
    645 ?        Ssl    0:00 /usr/lib/gvfsd
    650 ?        Sl     0:00 /usr/lib/gvfsd-fuse /run/user/1000/gvfs -f
    662 ?        Ssl    0:00 /usr/lib/at-spi-bus-launcher
    668 ?        S      0:00 /usr/bin/dbus-daemon --config-file=/usr/share/defau
    670 ?        Sl     0:00 /usr/lib/xfce4/xfconf/xfconfd
    676 ?        Sl     0:01 /usr/lib/at-spi2-registryd --use-gnome-session
    695 ?        Ss     0:00 /usr/bin/ssh-agent -s
    698 ?        SLs    0:01 /usr/bin/gpg-agent --supervised
    721 ?        S<sl  21:42 /usr/bin/pulseaudio --daemonize=no
    722 ?        Ssl    0:01 xfsettingsd --display :0.0 --sm-client-id 29a399bd9
    743 ?        Sl     0:24 xfce4-panel --display :0.0 --sm-client-id 26ec8bf39
    752 ?        Sl     0:00 Thunar --sm-client-id 21fca4347-2f3d-49a9-87bf-6fa9
    757 ?        Sl     0:03 xfdesktop --display :0.0 --sm-client-id 241e9ced4-5
    768 ?        Ssl    0:04 xfce4-power-manager --restart --sm-client-id 2b0551
    769 ?        Sl    10:15 pulseeffects --gapplication-service
    772 ?        Sl     0:00 /usr/lib/polkit-gnome/polkit-gnome-authentication-a
    774 ?        Sl     0:00 nm-applet
    781 ?        Sl     0:03 xfce4-screensaver
    788 ?        Ssl    0:00 /usr/lib/gvfs-udisks2-volume-monitor
    796 ?        Ssl    0:01 /usr/lib/xfce4/notifyd/xfce4-notifyd
    816 ?        Sl     0:00 /usr/lib/pulse/gsettings-helper
    834 ?        Sl     0:00 /usr/lib/dconf-service
    837 ?        Sl     0:01 /usr/lib/xfce4/panel/wrapper-2.0 /usr/lib/xfce4/pan
    838 ?        Sl     0:49 /usr/lib/xfce4/panel/wrapper-2.0 /usr/lib/xfce4/pan
    839 ?        Sl     0:00 /usr/lib/xfce4/panel/wrapper-2.0 /usr/lib/xfce4/pan
    840 ?        Sl     0:01 /usr/lib/xfce4/panel/wrapper-2.0 /usr/lib/xfce4/pan
   5835 ?        Sl     2:20 xfwm4 --display :0.0 --sm-client-id 2bc0df4e4-72f5-
   6580 ?        Sl     1:02 /usr/lib/firefox/firefox -contentproc -childID 15 -
  14455 ?        Sl     0:03 xfce4-terminal
  14461 pts/0    Ss     0:00 bash
  15533 pts/0    R+     0:00 ps -x
```

* `-u` - Fornece o nome do usuário e a hora de início do processo. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ ps -u
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
lucashe+   14461  0.0  0.0   4376  3804 pts/0    Ss   11:10   0:00 bash
lucashe+   15676  0.0  0.0   5664  2848 pts/0    R+   11:32   0:00 ps -u
```

*Obs: podemos combinar as opções como `ps -aux` que exibe todos os processos do sistema independente de terminal.*

Filtrando processos

Se estiver difícil de encontrar um processo, você pode utilizar o **ps** junto com o **grep**, utilizando o operador **pipe (|)**, onde você irá pegar a saida do comando *ps* e filtrar com o *grep*

Como por exemplo quereremos encontar o processo do *firefox*, então usariamos:

```console
lucashe4rt@He4rt-PC:~$ ps aux| grep firefox
    PID TTY          TIME CMD
      6 ?        00:00:00 /usr/lib/firefox/firefox
```


> ## kill

O comando `kill` serve para matarmos processos, ou seja, finalizar tarefas dentro do nosso sistema operacional.

Sintaxe:

```console
kill [opções] pid
```

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ kill 962
lucashe4rt@He4rt-PC:~$
```

*Acabei de finalizar o processo do discord no meu computador.*

Algumas vertentes do comando `kill`:

* `pkill` - Especificamos o nome do processo ou um padrão para encontrar o processo. Exemplo:

```console
lucashe4rt@He4rt-PC:~$ pkill firefox
lucashe4rt@He4rt-PC:~$
```

ou

```console
lucashe4rt@He4rt-PC:~$ pkill fire
lucashe4rt@He4rt-PC:~$
```

*Obs: este comando pode encerrar o processo errado, principalmente se exitem vários processos com o mesmo nome.*

* `killall` - Pode encerrar o processo pelo nome porém só funciona com o nome exato do processo e não com o nome parcial, assim, sendo mais seguro que o `pkill`.

```console
lucashe4rt@He4rt-PC:~$ killall Discord
lucashe4rt@He4rt-PC:~$
```

`Kill -9` e sua diferença entre o `kill` normal

Muitas vezes não conseguimos matar o processo quando o programa trava e para termos certeza de que conseguiremos finalizá-lo, forçando a finalização, podemos usar o modificador -9 para o comando kill da seguinte forma:

```console
lucashe4rt@He4rt-PC:~$ kill -9 13421
lucashe4rt@He4rt-PC:~$
```

Assim **forçamos** a parada do programa de id *13421*

A diferença para do kill com e sem o modificador -9 é simples: sem o modificador, o comando solicita o fechamento do programa, dando uma chance para o programa se encerrar sozinho, com o modificador essa chance não existe, o processo é encerrado imediatamente. (Geralmente é usado quando um programa realmente trava de vez e não quer fechar)

---

## Referências

[Devmedia - comando importantes linux](https://www.devmedia.com.br/comandos-importantes-linux/23893)

[Bóson Treinamentos - comando ls](https://www.youtube.com/watch?v=BIksX9l1Hvo) - Vídeo

[Vivaolinux - usando o comando df](https://www.vivaolinux.com.br/dica/Usando-o-comando-df)

[Hostinger - comando cat linux](https://www.hostinger.com.br/tutoriais/comando-cat-linux/)

[Guia Linux - ps](http://guialinux.uniriotec.br/ps/)

[Hostinger - comando kill linux](https://www.hostinger.com.br/tutoriais/comando-kill-linux/)

## Autores

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)


* **Marco Antonio (Specko)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lolgamarco2)
