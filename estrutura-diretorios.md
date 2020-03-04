# Capítulo 2 

> ## Aula 01 - Estrutura de diretórios
Para entendermos a estrutura de diretórios do linux, vamos navegar para pasta **raiz** (`/`).

```console
lucashe4rt@He4rt-PC:~$ cd /
```

Estando na raiz do sistema vamos exibir os arquivos existentes na pasta.

```console
lucashe4rt@He4rt-PC:/$ ls
```


Esta ação retornará algo semelhante a isto: 

```console
lucashe4rt@He4rt-PC:/$ ls
bin   dev  home  lib64       mnt  proc  run   srv  tmp  var
boot  etc  lib   lost+found  opt  root  sbin  sys  usr
```

*Obs: os arquivos podem variar de acordo com a distribuição, no meu caso estou usando arch linux.*

Para melhorar a visibilidade vamos utilizar o comando `ls -l` ou `ll`.

```console
lucashe4rt@He4rt-PC:/$ ls -l
```
* O parametro `-l` do comando `ls` serve para exibir os arquivos em formato de lista, mostrando, respectivamente as permissões, usuário que criou, qual grupo pertence, tamanho do arquivo e a ultima modificação do arquivo.
ou 
```console
lucashe4rt@He4rt-PC:/$ ll
```
* O comando `ll`, que é um **ALIAS** de `ls -l` com mais algumas opções, não é padrão, ou seja, não são todas as distribuições que tem esta opção ja definida.

Resultado:

```console
lucashe4rt@He4rt-PC:/$ ls -l
total 52
lrwxrwxrwx   1 root root     7 Nov 13 13:23 bin -> usr/bin
drwxr-xr-x   3 root root  4096 Feb 23 11:17 boot
drwxr-xr-x  19 root root  3340 Feb 28 10:53 dev
drwxr-xr-x  73 root root  4096 Feb 28 10:53 etc
drwxr-xr-x   3 root root  4096 Feb 23 11:13 home
lrwxrwxrwx   1 root root     7 Nov 13 13:23 lib -> usr/lib
lrwxrwxrwx   1 root root     7 Nov 13 13:23 lib64 -> usr/lib
drwx------   2 root root 16384 Feb 23 10:36 lost+found
drwxr-xr-x   2 root root  4096 Nov 13 13:23 mnt
drwxr-xr-x   7 root root  4096 Feb 27 15:07 opt
dr-xr-xr-x 299 root root     0 Feb 28 10:53 proc
drwxr-x---   5 root root  4096 Feb 23 23:15 root
drwxr-xr-x  22 root root   540 Feb 28 10:53 run
lrwxrwxrwx   1 root root     7 Nov 13 13:23 sbin -> usr/bin
drwxr-xr-x   4 root root  4096 Feb 23 10:52 srv
dr-xr-xr-x  13 root root     0 Feb 28 10:53 sys
drwxrwxrwt  22 root root   600 Feb 28 16:13 tmp
drwxr-xr-x   9 root root  4096 Feb 27 16:48 usr
drwxr-xr-x  13 root root  4096 Feb 28 10:53 var

```

Agora com os arquivos listados de maneira melhor visivel, vamos explica-los.

---
> ### **/** - Raiz

O diretório **raiz** é onde estão todos os principais diretórios do nosso sistema operacional linux.

*Obs: o único usuário capaz de criar, mover e apagar arquivos nesse diretório é o __root__, ou seja, o administrador.*

> ### **/bin** - Binários essênciais

O diretório **bin** é onde seram armazenados todos os arquivos executaveis padrões e essenciais para a nossa distribuição, variando de distribuição para distribuição. Neste diretório encontraremos os comandos `ls`, `rm`, `cp`, entre outros.

Vamos acessar o diretório e listar seu conteúdo para entendermos melhor:

```console
lucashe4rt@He4rt-PC:/$ cd /bin
lucashe4rt@He4rt-PC:/bin$ ls
```

Ao executar o comando `ls` será retornado varios arquivos, sendo cada um deles um executavel, essenciais para o sistema, dentro da nossa distribuição.


> ### **/boot** - Arquivos de inicialização

O diretório **boot** é onde estão armazenados os arquivos relacionados ao "core" do sistema, ou seja, arquivos relacionados ao kernel do sistema operacional.

Vamos acessar o diretório e listar seu conteúdo para entendermos melhor:

```console
lucashe4rt@He4rt-PC:/$ cd /boot
lucashe4rt@He4rt-PC:/boot$ ls
grub  initramfs-linux-fallback.img  initramfs-linux.img  vmlinuz-linux
```
*Obs: os arquivos podem variar de acordo com a distribuição.*

Dentro desse diretório nos temos alguns arquivos, vamos explica-los:

1. **grub** é o gerenciador de boot.
2. **vmlinuz** é o nosso kernel em si.
3. **initramfs** é um sistema de arquivos temporários usados pelo kernel durante o inicio do sistema.

No seu caso podem aparecer alguns outros arquivos, como:

1. **initrd** que é uma parte do sistema que inicializa junto com o boot.
2. **memtest** é uma opção que pode ser acessada pela tela do grub para testes de memória.
3. **System.map** traz o mapeamento de tudo que esta dentro do kernel.

Básicamente é isto que nós podemos encontrar dentro do diretório **boot**.

> ### **/dev** - Arquivos de dipositivos
É um diretório muito importante para sistemas linux pois ele mapeia cada dispositivo físico que nós temos em arquivos.

Vamos entrar no diretório e olhar mais de perto:

```console
lucashe4rt@He4rt-PC:/$ cd dev/ 
lucashe4rt@He4rt-PC:/dev$ ls
autofs           hpet          rfkill    tty15  tty37  tty59    vcs6
block            hugepages     rtc       tty16  tty38  tty6     vcsa
bsg              hwrng         rtc0      tty17  tty39  tty60    vcsa1
btrfs-control    initctl       sda       tty18  tty4   tty61    vcsa2
bus              input         sda2      tty19  tty40  tty62    vcsa3
char             kfd           sdb       tty2   tty41  tty63    vcsa4
console          kmsg          sdb1      tty20  tty42  tty7     vcsa5
core             kvm           sdb2      tty21  tty43  tty8     vcsa6
cpu              lightnvm      sdc       tty22  tty44  tty9     vcsu
cpu_dma_latency  log           sdc1      tty23  tty45  ttyS0    vcsu1
cuse             loop-control  shm       tty24  tty46  ttyS1    vcsu2
disk             mapper        snapshot  tty25  tty47  ttyS2    vcsu3
dri              mem           snd       tty26  tty48  ttyS3    vcsu4
drm_dp_aux0      mqueue        stderr    tty27  tty49  udmabuf  vcsu5
fb0              net           stdin     tty28  tty5   uhid     vcsu6
fd               null          stdout    tty29  tty50  uinput   vfio
full             nvram         tty       tty3   tty51  urandom  vga_arbiter
fuse             parport0      tty0      tty30  tty52  userio   vhci
hidraw0          port          tty1      tty31  tty53  vcs      vhost-net
hidraw1          ppp           tty10     tty32  tty54  vcs1     vhost-vsock
hidraw2          psaux         tty11     tty33  tty55  vcs2     zero
hidraw3          ptmx          tty12     tty34  tty56  vcs3
hidraw4          pts           tty13     tty35  tty57  vcs4
hidraw5          random        tty14     tty36  tty58  vcs5

```
Em meio a estes varios arquivos mapeados nós temos arquivos de:
1. Dispositivos de blocos (block)
2. Dispositivos de caracteres (char)
3. Dispositivos de barramentos (bus)
4. Alguns tipos de dados da CPU (cpu)
5. Discos que estão sendo utilizados (disk)
6. Memória (mem)

*Obs: os arquivos deste diretório variam de máquina pra máquina, mas estes tópicos listados acima são padrões.*

Comumente esse diretório não é muito utilizado por nós e sim pelos drivers mas é importante sabermos de sua existencia e que todos dispositivos que temos no sistema estão mapeados aqui.

> ### **/etc** - Arquivos de configuração 
Este diretório é onde o sistema armazena arquivos de configuração, tanto de configuração de serviço como do próprio sistema.

Vamos para dentro do diretório e dar uma olhada: 
```console
lucashe4rt@He4rt-PC:/$ cd etc/
lucashe4rt@He4rt-PC:/etc$ ls
ImageMagick-7           group-         man_db.conf      request-key.conf
NetworkManager          grub.d         mdadm.conf       request-key.d
UPower                  gshadow        mime.types       resolv.conf
X11                     gshadow-       mke2fs.conf      rpc
adjtime                 gtk-2.0        mkinitcpio.conf  samba
alsa                    gtk-3.0        mkinitcpio.d     sane.d
alternatives            healthd.conf   modprobe.d       securetty
arch-release            host.conf      modules-load.d   security
asound.conf             hostname       motd             sensors.d
audisp                  hosts          mtab             sensors3.conf
audit                   httpd          my.cnf           services
avahi                   initcpio       my.cnf.d         shadow
bash.bash_logout        inputrc        nanorc           shadow-
bash.bashrc             iproute2       ndctl            shells
bash_completion.d       iptables       netconfig        skel
bindresvport.blacklist  issue          nginx            slsh.rc
binfmt.d                java-openjdk   nscd.conf        ssh
ca-certificates         kernel         nsswitch.conf    ssl
cifs-utils              krb5.conf      openldap         sudoers
conf.d                  ld.so.cache    openmpi          sudoers.d
crypttab                ld.so.conf     os-release       sysctl.d
cups                    ld.so.conf.d   pacman.conf      systemd
dbeaver                 libaudit.conf  pacman.d         tmpfiles.d
dconf                   libblockdev    pam.d            trusted-key.key
default                 libnl          papersize        ts.conf
depmod.d                libpaper.d     passwd           udev
dpkg                    libreoffice    passwd-          udisks2
e2scrub.conf            libva.conf     php              vdpau_wrapper.cfg
environment             locale.gen     pkcs11           vimrc
ethertypes              localtime      polkit-1         wgetrc
fonts                   login.defs     profile          wpa_supplicant
fstab                   logrotate.d    profile.d        xattr.conf
fuse.conf               lvm            protocols        xdg
gai.conf                machine-id     pulse            xinetd.d
gemrc                   mailcap        rc_keymaps       xml
group                   makepkg.conf   rc_maps.cfg

```
*Obs: os arquivos deste diretório também podem variar de acordo com a distro e o que cada um tem instalado e configurado no seu sistema.*

Dentro deste diretório nos podemos encontrar arquivos de configuração de qualquer serviço, executaveis, inicialização, quais serviços irão subir primeiro, quais partições nós temos na nossa máquina, entre outros.

> ### **/home** - Pastas pessoais

Dentro desse diretório temos todos os diretórios de cada usuário que operam o sistema, ou seja, todos os usuários que logam e utilizam o sistema, porém isto não é regra. Este diretório é semelhante ao "documents and settings" do Windows.

Vamos acessar o diretório:

```console
lucashe4rt@He4rt-PC:/$ cd home/
 lucashe4rt@He4rt-PC:/home$ ls
lucashe4rt
```

Como podemos ver, tem uma pasta com o mesmo nome dos usuários disponiveis no sistema, no meu caso somente um. 

Vamos olhar dentro desta pasta também.

```console
lucashe4rt@He4rt-PC:/home$ cd lucashe4rt/
lucashe4rt@He4rt-PC:~$ 
```

Como podemos notar, nosso **path** mudou de **/home** para **~** quando acessamos a pasta com nosso nome de usuário ao invés de **/home/"usuario"**, ou seja, como dissemos no começo da aula, o diretório **~** é a **home** do nosso usuário logado.

Listando os arquivos da **home** do usuário:

```console
lucashe4rt@He4rt-PC:~$ ls
Desktop  Documents  Downloads Images
```
Temos os arquivos pessoais do usuário.

Antes de irmos para o próximo diretório vamos voltar para a **raiz** e limpar o terminal que esta cheio de comandos e coisas escritas na tela.

Para voltarmos para **raiz** podemos seguir praticamente os mesmos passo porém com uma diferença em um deles:

```console
lucashe4rt@He4rt-PC:~$ cd ../../
```

* De acordo com o que aprendemos anteriormente o parâmetro `..` sobe um diretório, então nos podemos utiliza-lo quantas vezes forem necessarias para subirmos até o diretório desejado, neste caso utilizamos duas vezes para subirmos dois diretórios.

ou podemos simplesmente digitar:

```console
lucashe4rt@He4rt-PC:~$ cd /
```

Resultado:

```console
lucashe4rt@He4rt-PC:/$
```

> ### **/lib** - Bibliotecas essenciais

Dentro deste diretório nos iremos encontrar bibliotecas
do próprio sistema.

Vamos entrar e olhar:
```console
lucashe4rt@He4rt-PC:/$ cd lib/
lucashe4rt@He4rt-PC:/lib$ ls
```

Ao executar o comando `ls` será retornado uma série de arquivos, sendo cada um deles bibliotecas próprias da nossa distro.

*Obs: a quantidade de arquivos pode varias de acordo com a distribuição e o que cada um tem instalado na máquina.*


> ### **/mnt** - Montagem de sistemas temporários
Este diretório é um ponto de montagem temporário para que possamos montar manualmente, por exemplo, um pendrive, uma partição e etc.

Se entrarmos dentro dele e exibir seu conteúdo:

```console
lucashe4rt@He4rt-PC:/$ cd /mnt
lucashe4rt@He4rt-PC:/mnt$ ls
lucashe4rt@He4rt-PC:/mnt$ 
```
Não tem nada dentro deste diretório por conta dele ser usado como ponto de montagem então como não montamos nenhuma partição esta vazio.


> ### **/opt** - Pacotes opcionais

Normalmente quando instalamos um software grande, com várias bibliotecas, esse programa geralmente vem para o diretório **/opt**.

Vamos dar uma olhada.

```console
lucashe4rt@He4rt-PC:/$ cd opt/ 
lucashe4rt@He4rt-PC:/opt$ ls
discord  gitkraken  phpstorm  visual-studio-code
```
*Obs: os arquivos contidos neste diretório variam muito de acordo com o que cada máquina tem instalado, neste caso eu tenho estes softwares.*

> ### **/proc** - Kernel e arquivos de processos

Dentro desse diretório é onde fica os processos da nossa maquina armazenados também em diretórios, ou seja, cada processo em execução o sistema mapea em arquivos/pastas e armazena neste diretório.

Vamos entender melhor.

```console
lucashe4rt@He4rt-PC:/$ cd proc/ 
lucashe4rt@He4rt-PC:/proc$ ls
1     172   2477  3     446  503   63   766        diskstats      partitions
10    173   249   30    45   504   642  767        dma            pressure
11    1732  25    300   454  505   647  771        driver         sched_debug
1131  1734  251   302   46   506   65   777        execdomains    schedstat
12    176   252   304   460  51    66   786        fb             scsi
1232  177   253   306   47   52    660  787        filesystems    self
13    179   254   31    48   5249  666  796        fs             slabinfo
14    18    255   32    483  5273  668  8          interrupts     softirqs
1428  180   256   3226  484  53    67   801        iomem          stat
1433  181   258   325   485  54    674  820        ioports        swaps
1436  182   259   33    486  5404  675  830        irq            sys
1438  19    26    334   487  543   68   833        kallsyms       sysrq-trigger
1461  193   260   337   488  545   69   852        kcore          sysvipc
16    199   261   34    489  55    693  855        key-users      thread-self
1601  2     2624  35    49   56    697  857        keys           timer_list
1630  20    263   37    490  5629  699  882        kmsg           tty
1641  200   264   372   491  5754  71   9          kpagecgroup    uptime
1646  21    27    3728  492  58    72   994        kpagecount     version
165   2107  275   373   493  5823  720  acpi       kpageflags     vmallocinfo
1654  211   277   38    494  59    721  asound     latency_stats  vmstat
166   2110  2778  39    495  6     73   buddyinfo  loadavg        zoneinfo
167   2112  278   390   496  60    74   bus        locks
168   2134  2783  4     497  603   740  cgroups    meminfo
1680  2142  279   40    498  605   749  cmdline    misc
169   2198  28    404   499  606   75   config.gz  modules
1692  22    288   41    5    61    754  consoles   mounts
17    23    291   42    500  611   757  cpuinfo    mtrr
170   237   294   44    501  616   76   crypto     net
171   24    295   444   502  62    765  devices    pagetypeinfo

```

Os números dos arquivos não serão os mesmos no meu computador e no seu, por conta de cada maquina rodar processos diferentes.

Dentro desse diretório também contém arquivos de estatisticas e de logs.

*Obs: os números que nomeiam os diretórios são na verdade o __PID__ do processo dentro do sistema operacional.*

> ### **/root** - Home para o super usuário (root)
Este diretório semelhante a **home** do nosso usuário comum, porém esta pasta é a **home** do nosso usuário **root**, ou seja, aqui estão todos os arquivos pessoais do usuário **root**.

> ### **/run** - Arquivos temporários de aplicativos

Este diretório não é padrão em todas as distros, porém, dentro dele nós encontramos arquivos temporários de configuração, arquivos de processos em execução como logs e estatisticas.

Vamos listar esses arquivos:

```console
lucashe4rt@He4rt-PC:/$ cd run/
lucashe4rt@He4rt-PC:/run$ ls
NetworkManager   httpd      lvm          nscd     tmpfiles.d
cryptsetup       initctl    lvmetad.pid  samba    udev
dbus             initramfs  media        sddm     udisks2
dmeventd-client  lock       mount        sudo     user
dmeventd-server  log        mysqld       systemd  utmp
```

*Obs: os arquivos neste diretório variam de máquina para máquina.*

> ### **/sbin** - Arquivos binários de administração

Este diretório é semelhante ao diretório **bin**, contém varios arquivos executaveis, porém com uma diferença, esse executaveis só podem ser acessados e executados pelo **super usuário**.

Vamos dar uma olhada.
```console
lucashe4rt@He4rt-PC:/$ cd sbin/
lucashe4rt@He4rt-PC:/sbin$ ls
```

Todos esses arquivos que foram retornados com nosso comando de exibição podem somente ser acessados pelo **super usuário**.

> ### **/srv** - Serviços de dados
 Este diretório não é padrão entre os linux então não entraremos em detalhes mas basicamente dados de servidores e serviços em execução na máquina são armazenados aqui.

 > ### **/sys** - Sistema
Aqui nos encontramos informações sobre nosso sistema operacional e sua execução

Vamos exibir seu conteúdo:

```console
lucashe4rt@He4rt-PC:/sys$ ls
block  class  devices   fs          kernel  power
bus    dev    firmware  hypervisor  module
```

> ### **/tmp** - Arquivos temporários
Ele é um diretório com todas as permissões, ou seja, qualquer usuário pode entrar, criar, apagar e mover arquivos dentro deste diretório.

```console
[17:03:51] lucashe4rt@He4rt-PC:/tmp$ ls
 Temp-51f11099-55d7-4570-9487-689450b1f2b4
 Temp-f859c4ee-4a2f-468d-a0db-c0906b74fa76
 appInsights-nodeAIF-444c3af9-8e69-4462-ab49-4191e6ad1916
 net-export
 sddm-:0-naLUIF
 sddm-auth16c347ea-a507-4a14-8e54-1d85eb7b5c9a
 ssh-vb9ZVI39dfES
 systemd-private-855130dd3c1244f985a509af3d43c5f8-httpd.service-RDFFYg
 systemd-private-855130dd3c1244f985a509af3d43c5f8-mariadb.service-KJWYwh
 systemd-private-855130dd3c1244f985a509af3d43c5f8-systemd-logind.service-EKe1pf
 systemd-private-855130dd3c1244f985a509af3d43c5f8-upower.service-lU2BCg
```
Este diretório armazena arquivos temporários, ou seja, após um período são apagados.

*Obs: quantidade de arquivos varia de máquina para máquina.*

> ### **/usr** - Dados de leitura

O diretório **usr** armazena aplicativos e arquivos utilizados pelos usuários, ao contrário de aplicativos e arquivos utilizados pelo sistema. Por exemplo, aplicativos não essenciais estão localizados dentro do diretório **/usr/bin** em vez do diretório **/bin**.

```console
lucashe4rt@He4rt-PC:/$ cd usr/
lucashe4rt@He4rt-PC:/usr$ ls
bin  include  lib  lib32  lib64  local  sbin  share  src
```
*Obs: em essencia esses arquivos tem somente permissão de leitura.*

> ### **/var** - Arquivo de dados váriaveis
O objetivo desse diretório e guardar parte status das execuções atuais do nosso sistema

```console
lucashe4rt@He4rt-PC:/$ cd var/
lucashe4rt@He4rt-PC:/var$ ls
cache  dpkg   games  local  log   opt  spool
db     empty  lib    lock   mail  run  tmp
```

*Obs: os arquivos de log e outros são armazenados neste diretório.*

---

## Referências:

[Tecmundo - Entendendo a estrutura de pastas do linux e android](https://www.tecmundo.com.br/android/25841-entendendo-a-estrutura-de-pastas-do-linux-e-android.htm)

[CanalTech - Entendendo a estrutura de diretórios do Linux](https://canaltech.com.br/linux/entendendo-a-estrutura-de-diretorios-do-linux/)

[Udemy - Terminal Linux, Shell Scripting e Gerenciamento de Redes](https://www.udemy.com/course/terminal-linux-do-zero-ao-gerenciamento-de-redes/)