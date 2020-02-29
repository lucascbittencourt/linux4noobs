# Capítulo 2 - Manipulação de arquivo e pastas

> ## Aula 01 - Hierarquia dos diretórios e arquivos

Para entendermos a hierarquia do linux iremos aprender nosso primeiro comando que irá nos mover para pasta raiz do sistema operacional. Para isto, abra um terminal e digite:

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

Agora que entendemos como funciona para navegarmos entre os diretórios, vamos para o diretório **raiz** ( `/` ) novamente, seguindo o comando que aprendemos acima. 

Estando na raiz do sistema iremos aprender agora outro comando, o `ls`, para exibirmos os arquivos existentes na pasta.

```console
lucashe4rt@He4rt-PC:/$ ls
```

* O comando `ls`, nome derivado da palavra "list", exibe quais são os arquivos existentes na nossa pasta corrente, ou seja, da nossa pasta atual em formato de coluna.

Esta ação retornará algo semelhante a isto: 

```console
lucashe4rt@He4rt-PC:/$ ls
bin   dev  home  lib64       mnt  proc  run   srv  tmp  var
boot  etc  lib   lost+found  opt  root  sbin  sys  usr
```

*Obs: os arquivos podem variar de acordo com a distruição, no meu caso estou usando arch linux.*

Cada cor representa um tipo de arquivo (a cor pode ser configuravel):

* Azul escuro são os diretórios;
* Verde é um arquivo executavel e com todas persmissões de sistema (escrita, leitura e acesso);
* Azul claro são diretórios links.

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

Agora com os arquivos listado de maneira melhor visivel, vamos explica-los.

> ### **/bin**

O diretório **bin** é onde seram armazenados todos os arquivos executaveis padrões e essenciais para a nossa distribuição, variando de distribuição para distribuição. Neste diretório encontraremos os comandos `ls`, `rm`, `cp`, entre outros.

Vamos acessar o diretório e listar seu conteúdo para entendermos melhor:

```console
lucashe4rt@He4rt-PC:/$ cd /bin
lucashe4rt@He4rt-PC:/bin$ ls
```


Ao executar o comando `ls` será retornado varios arquivos, sendo cada um deles um executavel, essenciais para o sistema, dentro da nossa distribuição.

Para sairmos do diretório **bin** e voltarmos para **raiz** vamos utilizar:

```console
lucashe4rt@He4rt-PC:bin/$ cd ..
```
* O parametro `..` significa que estamos voltando um diretório para cima, neste caso o diretório acima é o **/**

ou

```console
lucashe4rt@He4rt-PC:bin/$ cd /
```

Resultado:

```console
lucashe4rt@He4rt-PC:/$
```

Agora vamos prosseguir para o próximo diretório

> ### **/boot**

O diretório **boot** é onde estão armazenados os arquivos relacionados ao "core" do sistema operacional, ou seja, arquivos relacionados ao kernel do sistema operacional.

Vamos acessar o diretório e listar seu conteúdo para entendermos melhor:

```console
lucashe4rt@He4rt-PC:/$ cd /boot
lucashe4rt@He4rt-PC:/boot$ ls
grub  initramfs-linux-fallback.img  initramfs-linux.img  vmlinuz-linux
```
*Obs: os arquivos podem variar de acordo com a distribuição.*

Dentro desse diretório nos temos alguns arquivos, vamos explica-los:

1. **grub** é o gerenciador de boot
2. **vmlinuz** é o nosso kernel em sí.
3. **initramfs** é um sistema de arquivos temporarios usados pelo kernel durante o inicio do sistema

No seu caso podem aparecer alguns outros arquivos, como:

1. **initrd** que é uma parte do sistema que inicializa junto com o boot.
2. **memtest** é uma opção que pode ser acessada pela tela do grub para testes de memória.
3. **System.map** traz o mapeamento de tudo que esta dentro do kernel.

Básicamente é isto que nós podemos encontrar dentro do diretório **boot**, então vamos dar sequencia para o próximo diretório.

> ### **/dev**
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

Comumente esse diretório não é muito utilizado por nós e sim pelos drivers mas é importante sabermos de sua existencia e que todos dispositivos que temos no sistema esta mapeado aqui.

Continuando com nossa jornada através dos diretórios.

> ### /etc 
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

Dentro deste diretório nos podemos encontrar arquivos de configuração de qualquer serviço, executaveis, inicialização, quais serviços iram subir primeiro, quais partições nós temos na nossa máquina, entre outros.

Vamos para o próximo diretório.

> ### **/home**

Dentro desse diretório temos todos os diretórios de cada usuário que operam o sistema, ou seja, todos os usuários que logam e utilizam o sistema, porém isto não é regra. Este diretório é semelhante ao "documents and settings" do Windows.

Vamos acessar o diretório

```console
lucashe4rt@He4rt-PC:/$ cd home/
 lucashe4rt@He4rt-PC:/home$ ls
lucashe4rt
```

Como podemos ver, tem uma pasta com o mesmo nome dos usuários disponiveis no sistema, no meu caso somente um. 

Vamos olhar dentro desta pasta também.

```console
[19:56:59] lucashe4rt@He4rt-PC:/home$ cd lucashe4rt/
[20:00:35] lucashe4rt@He4rt-PC:~$ 
```

Como podemos notar, nosso **path** mudou de **/home** para **~** quando acessamos a pasta com nosso nome de usuário ao invés de **/home/"usuario"**, ou seja, como dissemos no começo da aula, o diretório **~** é a **home** do nosso usuário logado.

Listando os arquivos da **home** do usuário:

```console
[20:00:35] lucashe4rt@He4rt-PC:~$ ls
Desktop  Documents  Downloads Images
```
Temos os arquivos pessoas do usuário.

Antes de irmos para o próximo diretório vamos limpar o terminal que esta cheio de comandos e coisas escritas na tela.

Para limpar a tela é bem simples, basta pressionar as teclas `CTRL + L` ou digitar no próprio terminal:

```console
lucashe4rt@He4rt-PC:~$ clear
```

E pronto, com o terminal limpo podemos prosseguir para o próximo diretório.

> ### **/lib**

