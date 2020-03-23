# 02 - Gerenciamento de usuários e grupos

## Contéudo do artigo

[Gerenciamento de usuários](#usuarios)<br>
[Gerenciamento de grupos](#grupos)<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

> <h3 id="usuarios"> Gerenciamento de usuários </h3>

#### Adicionar

Criar um usuário novo no Linux é bem simples, apenas é necessário o comando `useradd` e indicar o nome do novo usuário.

Sintaxe

```console
useradd [opções] <nomeusuario>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo useradd linux4noobs
```

*obs: o comando useradd apenas adiciona um novo usuário ao arquivo /etc/passwd, ele não aloca qualquer recurso.*

Algumas opções

opçao|função
---  |  ---
-d   | define o nome do diretório home do usuário (mas não o cria).
-s   | define o shell padrão do usuário.
-h   | exibe as opções do comando.

Exemplo usando as opções **-d** e **-s**.

```console
lucashe4rt@He4rt-PC:~$ sudo useradd -d /home/he4rtdevs -s /bin/bash he4rtdevs
```

#### Alterar

Para alterarmos uma conta de usuário basta apenas utilizarmos o comando `usermod`.

Sintaxe

```console
usermod [opções] <nomeusuário>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo usermod -l linux4he4rt linux4noobs
```

*no comando acima alteramos o nome do usuário linux4noobs para linux4he4rt.*

Algumas opções

opção | função
--- | ---
-d *diretório* [-m] | cria uma nova home para o usuário. A opção **-m** move os arquivos da home atual do usuário para a nova.
-e yyyy-mm-dd | altera a data de expiração da conta do usuário
-g *grupo* | altera o **GID** do grupo do usuário para o especificado.
-G *grupo[, grupo2, ...]* | define o **GID** dos outros grupos que o usuário pertence.
-l *nome* | altera o nome do usuário (ele não pode estar logado).
-s *shell* | altera o shell do usuário.
-u *uid* | altera o número de **UID** do usuário

#### Remover

Para removermos um usuário utilizamos o comando `userdel`.

Sintaxe

```console
userdel [opções] <nomeusuario>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo userdel linux4he4rt
```

Algumas opções

opção | função
--- |  ---
-h | exibe as opções do comando
-r | deleta a home e todos os seus arquivos

#### Senha

Para congfigurarmos ou alteramos a senha de um usuário utilizamos o comando `passwd`.

Sintaxe

```console
passwd [opções] <nomeusuario>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo passwd linux4he4rt
```

Algumas opções

opção | função
--- | ---
-l | Trava a senha do usuário, ficando impedido de se logar e não pode trocar a senha (não é desabilitado).
-u | Destrava a senha do usuário.
-d | Exclui a senha do usuário.
-e | Expira a senha do usuário, forçando-o a fornecer uma nova ao logar-se novamente.
-x *dias* | Expira a senha do usuário quando atingir o número de dias especificados.
-n *dias* | define a quantidade mínima de dias que o usuário deverá esperar para trocar a senha.
-w *dias* | define a quantidade mínima de dias que o usuário receberá o aviso que a senha precisa ser alterada.
-i | deixa o usuário inativo, caso a senha tenha expirado.
-S | Exibe o status da conta.
-a | Usada em conjunto com a opção -S mostra o status das contas de todos os usuários.

> <h3 id="grupos"> Gerenciamento de grupos </h3>

#### Adicionar 

Para criarmos um novo grupo utilizamos o comando `groupadd`.

Sintaxe

```console
groupadd [opções] <grupo>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo groupadd noobs
```

Algumas opções

opção | função
--- | ---
-g *GID* | especifica o **GID** do novo grupo (Utilize valores maiores que 500 e que não estejam sendo usados).
-o *GID* | atribui um **GID** já utilizado por outro grupo.

#### Mudar de grupo

Pode ocorrer que um usuário pertença a varios grupos, porém, todas as ações feitas por um usuário são associadas ao seu **UID** E **GID** primários e para mudarmos temporaria mente o grupo principal utiliza-se o comando `newgrp`.

Sintaxe

```console
newgrp [-] <grupo>
```

*obs: o hífen (**-**) serve para reinicializar as variáveis de ambiente do usuário.*

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo newgrp noobs
```

#### Remover

Para removermos um grupo utilizamos o comando `groupdel`

Sintaxe

```console
groupdel <grupo>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo groupdel noobs
```

*Obs: Não se deve remover o grupo primário de um grupo de usuários existentes. Deve-se antes remover os usuários, para então remover o grupo.*

---

## Referências

[Guia Linux - useradd](http://guialinux.uniriotec.br/useradd/)<br>
[Guia Linux - usermod](http://guialinux.uniriotec.br/usermod/)<br>
[Guia Linux - userdel](http://guialinux.uniriotec.br/userdel/)<br>
[Bóson treinamentos - comando   passwd](http://www.bosontreinamentos.com.br/linux/38-gerenciamento-de-usuarios-e-grupos-05-alterar-senhas-comando-passwd/)<br>
[Viva o Linux - Fundamentos do sistema Linux - usuários e grupos](https://www.vivaolinux.com.br/artigo/Fundamentos-do-sistema-Linux-usuarios-e-grupos/?pagina=4)

## Autores

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)