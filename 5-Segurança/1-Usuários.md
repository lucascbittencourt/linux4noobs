# 01 - Usuários

## Contéudo do artigo

[passwd](#passwd)<br>
[Tipos de usuários](#tipos)<br>
[Grupos](#grupos)<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

O Linux é um sistema operacional multi-usuário, ou seja, ele pode ter mais de um usuário conectado ao mesmo tempo e cada um pode se conectar mais de uma vez num mesmo momento. Neste artigo vamos entender alguns conceitos sobre o arquivo *passwd*, *tipos de usuários* e *grupos*.

> ### passwd

O arquivo passwd é onde estão armazenadas as principais informações sobre todos os usuários em um sistema Linux. Cada linha desse arquivo é o registro de um usuário do sistema.

*Esse arquivo esta localizado em `/etc/passwd`.*

Exemplo do arquivo passwd.

```console
lucashe4rt@He4rt-PC:~$ cd /etc/
lucashe4rt@He4rt-PC:/etc$ cat passwd
root:x:0:0::/root:/bin/bash
bin:x:1:1::/:/usr/bin/nologin
daemon:x:2:2::/:/usr/bin/nologin
mail:x:8:12::/var/spool/mail:/usr/bin/nologin
ftp:x:14:11::/srv/ftp:/usr/bin/nologin
http:x:33:33::/srv/http:/usr/bin/nologin
nobody:x:65534:65534:Nobody:/:/usr/bin/nologin
dbus:x:81:81:System Message Bus:/:/usr/bin/nologin
systemd-journal-remote:x:982:982:systemd Journal Remote:/:/usr/bin/nologin
systemd-network:x:981:981:systemd Network Management:/:/usr/bin/nologin
systemd-resolve:x:980:980:systemd Resolver:/:/usr/bin/nologin
systemd-timesync:x:979:979:systemd Time Synchronization:/:/usr/bin/nologin
systemd-coredump:x:978:978:systemd Core Dumper:/:/usr/bin/nologin
uuidd:x:68:68::/:/usr/bin/nologin
polkitd:x:102:102:PolicyKit daemon:/:/usr/bin/nologin
git:x:977:977:git daemon user:/:/usr/bin/git-shell
lucashe4rt:x:1000:985::/home/lucashe4rt:/bin/bash
avahi:x:976:976:Avahi mDNS/DNS-SD daemon:/:/usr/bin/nologin
colord:x:975:975:Color management daemon:/var/lib/colord:/usr/bin/nologin
usbmux:x:140:140:usbmux user:/:/usr/bin/nologin
sddm:x:974:974:Simple Desktop Display Manager:/var/lib/sddm:/usr/bin/nologin
rtkit:x:133:133:RealtimeKit:/proc:/usr/bin/nologin
mysql:x:973:973:MariaDB:/var/lib/mysql:/usr/bin/nologin
cups:x:209:209:cups helper user:/:/usr/bin/nologin
```

Vamos analisar a linha contendo as informações do usuário *lucashe4rt*.

```console
lucashe4rt:x:1000:1000::/home/lucashe4rt:/bin/bash
```

Podemos observar que esta linha contém vários campos separados por dois pontos `:`. Vamos entender melhor cada campo respectivamente.

* **lucashe4rt** - nome do usuário na máquina;
* **x** - informação utilizada para validar a senha do usuário.
  * *Este campo geralmente é definido por "x" contendo a informação de senha real sendo armazenado em um arquivo de [senha sombra](http://www.bosontreinamentos.com.br/linux/o-arquivo-de-senhas-etc-shadow-no-linux/) separado.*
* **1000** - número de identificação do usuário. O sistema operacional usa esse número para manter os registros dos arquivos que o usuário possui ou pode acessar;
* **985** - número do grupo do usuário.
* **/home/lucashe4rt** - diretório base, *home*, do usuário.
* **/bin/bash** - shell padrão.

> <h3 id="tipos"> Tipos de usuários </h3>

#### Usuários comuns

São os usuários que podem se conectar no sistema. Geralmente, estes usuários possuem uma *home* e podem manipular arquivos quando tem as permissões para tal. Porém estes usuários geralmente não tem permissão para certos arquivos e diretórios na maquina e não podem executar muitas funções a nível de sistema.

#### Usuários de sistema

Diferente dos usuários comuns, estes usuários não se conectam no sistema. São contas usadas para tarefas específicas dentro do sistema que não são de propriedade de uma pessoa em particular.

#### Root

O usuário *root*, também chamado de superusuário, tem controle total sobre o sistema operacional. Ele pode acessar todos os arquivos e normalmente é o único que pode executar certos programas, como por exemplo o httpd.

Linha referente ao root no arquivo /etc/passwd.

```console
root:x:0:0::/root:/bin/bash
```

*obs: a linha de identificação do usuário root é igual a 0. Qualquer conta com a identificação de usuário  igual a 0 é um root, mesmo o nome não sendo root.*

> ### Grupos

Um grupo é um conjunto de um ou mais usuários. É interessante reunir vários usuários em um grupo para definir suas propriedades, como as permissões. Como o arquivo [passwd](#passwd) nós temos um arquivo somente para armazenar detalhes sobre os grupos.

*Esse arquivo esta localizado em `/etc/group`.*

Exemplo do arquivo group.

```console
lucashe4rt@He4rt-PC:~$ cd /etc/
lucashe4rt@He4rt-PC:/etc$ cat group
root:x:0:root
sys:x:3:bin
mem:x:8:
ftp:x:11:
mail:x:12:
log:x:19:
smmsp:x:25:
proc:x:26:polkitd
games:x:50:
lock:x:54:
network:x:90:
floppy:x:94:
scanner:x:96:
power:x:98:
adm:x:999:daemon
kmem:x:997:
tty:x:5:
utmp:x:996:
audio:x:995:
disk:x:994:
input:x:993:
kvm:x:992:
lp:x:991:cups
optical:x:990:
render:x:989:
storage:x:988:
uucp:x:987:
video:x:986:sddm
users:x:985:lucashe4rt
systemd-journal:x:984:
rfkill:x:983:
bin:x:1:daemon
daemon:x:2:bin
http:x:33:
nobody:x:65534:
dbus:x:81:
systemd-journal-remote:x:982:
systemd-network:x:981:
systemd-resolve:x:980:
systemd-timesync:x:979:
systemd-coredump:x:978:
uuidd:x:68:
polkitd:x:102:
git:x:977:
lucashe4rt:x:1000:
avahi:x:976:
colord:x:975:
usbmux:x:140:
sddm:x:974:
rtkit:x:133:
mysql:x:973:
cups:x:209:
```

Vamos analisar a linha contendo as informações do grupo *users*.

```console
users:x:985:lucashe4rt
```

Podemos observar que, assim como no arquivo passwd, esta linha contém vários campos separados por dois pontos `:`. Vamos entender melhor cada campo respectivamente.

* **lucashe4rt** - nome excluisivo do grupo;
* **x** - informação utilizada para validar a senha do grupo.
  * *Este campo como esta definido por "x" ele contém a informação de senha real armazenado no arquivo [/etc/gshadow](https://gnulinuxbr.wordpress.com/2009/07/14/arquivo-etcgshadow/) separado.*
* **985** - número exclusivo de identificação do grupo;
* **lucashe4rt** - lista dos nomes dos usuários que pertecem ao grupo.


[Próximo](./2-Grupos.md)
---

## Referências

[Viva o Linux - Os Usuários do Linux](https://www.vivaolinux.com.br/artigo/Os-usuarios-do-Linux)

## Autores

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)