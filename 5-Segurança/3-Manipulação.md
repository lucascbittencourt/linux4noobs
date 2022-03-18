# 03 - Manipulação de permissões

## Contéudo do artigo

[Donos, grupos e usuários](#donos)<br>
[Tipos de permissão]()<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

 As permissões dentro de um sistema Linux protegem os arquivos e diretórios do acesso indevido ou não autorizado de algum usuário. São as permissões que impedem que algum software malicioso cause estragos no nosso sistema. Vamos entender algumas coisas sobre permissões.

> ### <span id="donos"> Donos, Grupos e usuários </span>

O princípio da segurança do nosso sistema de arquivos Linux é definir o acesso aos arquivos por donos, grupos e usuários.

* **Dono**
  * É o usuário no qual criou o arquivo ou diretório.

* **Grupo**
  * Permite que os usuários do grupo tenham acesso ao arquivo/diretório.

* **Outro usuários**
  * Usuários que não são donos ou não pertecem ao grupo do arquivo/diretório.

> ### Tipos de permissão

Dentro do sistema linux nós temos 3 tipos de permissões básicas:

Permissão | Descrição
--- | ---
r | Permissão de leitura para arquivos e permissão pra listar conteúdo do diretórios.
w | Permissão para gravação de arquivos e permite criar arquivos e diretórios caso for um diretório.
x | Permite execução de um arquivo (se for um arquivo executavel) e caso for um diretório permite o acesso.

Nós conseguimos ver as permissões utilizando o comando **ls -l**

```console
drwxr-xr-x 16 lucashe4rt lucashe4rt      4096 Mar 15 14:11 Documents
```

Da esquerda pra direita nós temos as permissões do **dono**, **grupo** e outros usuários respectivamente. Logo em seguida temos o **dono** do diretório e o **grupo** respectivamente.

Nome | Permissão
--- | ---
Dono| rwx
Grupo| r-x
Outros| r-x

<br>

Função | Nome
---|---
Dono | lucashe4rt
Grupo | lucashe4rt

Desta maneira podemos entender que o **dono** tem acesso total ao diretório, o **grupo** tem acesso de *leitura* e *acesso* (acesso pois é um diretório), e **outros usuários** também tem permissão de *leitura* e *acesso*.

> ### Etapas para o acesso ao arquivo/diretório

Para o acesso a um arquivo ou diretório da seguinte forma:

1. Verifica-se primeiro se o usuário que está acessará o arquivo é o dono, caso seja as permissões destinadas ao dono são aplicadas.

2. Se não for dono do arquivo/diretório, verifica-se o grupo do arquivo e do usuário caso pertençam ao mesmo grupo as permissões referente ao grupo são aplicadas.

3. Se não pertencer ao grupo é verificado as permissões de acesso para os outros usuários e aplicadas.

> ### Alterar permissões

Alterar permissões de acesso a um arquivo ou diretório é bem simples, basta usar o comando `chmod`.

Sintaxe

```console
chmod [opções] [permissões] <arquivo/diretório>
```

O sistema entende com as indicações de usuários, grupo e outros usuários pelas letras *u*, *g* e *o* respectivamente e os simbolos *+* e *-* para adicinar ou remover as permissões.

Exemplo

```console
lucashe4rt@He4rt-PC:~$ chmod g+x arquivo.txt
lucashe4rt@He4rt-PC:~$ ls -l arquivo.txt
-rwxr-xr-- 1 lucashe4rt lucashe4rt 0 Mar 17 21:57 arquivo.txt
```

Como podemos perceber a permissão de execução daquele arquivo foi concedida ao grupo no qual o arquivo pertence.

#### Permissões octal

Nós também podemos alterar as permissões de acesso utilizando o modo octal, que é um conjunto de oito números onde cada número define um tipo de acesso diferente, ao invés de utilizar +x, -x, etc.

Tabela com as permissões em octal

Octal | Permissão
--- | ---
0 | Nenhuma (-rwx)
1| Execução (x)
2| Escrita (w)
3| Escrita + Execução (wx)
4| Leitura (r)
5| Leitura + Execução (rx)
6| Leitura + Escrita (rw)
7| Todas (+rwx)

Exemplo

```console
lucashe4rt@He4rt-PC:~$ chmod 701 arquivo.txt
lucashe4rt@He4rt-PC:~$ ls -l
-rwx-----x  1 lucashe4rt lucashe4rt         0 Mar 17 21:57 arquivo.txt
```

O primeiro número é destinado ao dono, o segundo ao grupo e o terceiro aos outros usuários, logo nesse exemplo nós demos todas as permissões ao dono, nenhuma ao grupo e execução para outros usuários.

> ### Alterar dono ou grupo

Para alterarmos o dono ou grupo do arquivo/diretório também é bem simples! Nós utilizamos o comando `chown` para esta ação.

Sintaxe

```console
chown [opções] <dono/grupo> <diretório/arquivo>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo chown root arquivo.txt
lucashe4rt@He4rt-PC:~$ ls -l
-rwx-----x  1 root       lucashe4rt         0 Mar 17 21:57 arquivo.txt
```

Como é possivel perceber trocamos o dono do arquivo para o usuário *root*.

Algumas opções do comando

Opção | Função
--- | ---
-R | inclui os sub-diretórios caso seja um diretório
-c | Exibe o resultado

Para alterarmos o grupo do arquivo ou diretório a sintaxe é a seguinte.

```console
chown [opções] dono:grupo <arquivo/diretório>
```

Exemplo

```console
lucashe4rt@He4rt-PC:~$ sudo chown root:root arquivo.txt
lucashe4rt@He4rt-PC:~$ ls -l
-rwx-----x  1 root       root               0 Mar 17 21:57 arquivo.txt
```

[Próximo](./4-Permissões.md)
---

## Referências

[IFRN - Linux 04](https://docente.ifrn.edu.br/filiperaulino/disciplinas/introducao-a-sistemas-abertos/aulas/)

## Autores

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)