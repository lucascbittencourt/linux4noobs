# 03 - Navegação

## Conteúdo do artigo

[cd](#cd)<br>
[Path Absoluto X Path Relativo](#path)<br>
[pwd](#pwd)<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

Os comandos de navegação via linha de comando são de extrema importância para usarmos o sistema pois é desta maneira que conseguimos transitar pela estrutura de diretórios do nosso sistema.

> ## cd

Este comando, como abordado no artigo passado, serve para fazermos a mudança entre diretórios, ou seja, podemos navegar para qualquer local do sistema.

*Obs: como o comando `cd` ja foi abordado no artigo passado seremos mais diretos e sem muitos exemplos neste artigo.*

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cd Desktop
lucashe4rt@He4rt-PC:~/Desktop$

lucashe4rt@He4rt-PC:~$ cd /var/cache/
lucashe4rt@He4rt-PC:/var/cache$
```

Neste exemplo nós informamos um caminho relativo e um caminho absoluto, explicaremos mais para frente neste mesmo artigo a diferença de um para o outro.

Para entendermos melhor a navegação vamos ver mais alguns exemplos.

* `cd ..` - O `..` significa um diretório acima do atual logo esse comando nos permite subir um diretório.
* `cd ~` ou `cd` - O caractere `~` faz referência a pasta home do nosso usuário atual então podemos entender que com esse comando nós navegaremos até a home de nosso usuário, porém obtemos o mesmo resultado não passando nenhum parametro ao comando.
* `cd -` - Nos retorna para o último diretório acessado
* `cd /diretorio` - Partindo da raiz até o último diretório passado como referência
* `cd diretorio` - Parte do local corrente até o diretório passado como referência

> <h2 id="path">Path Absoluto x Path Relativo</h2>

 O path absoluto, ou caminho absoluto, é o path cujo início é a raiz do sistema, ou seja, o diretório `/`.

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cd /var/log/
lucashe4rt@He4rt-PC:/var/log$
```

O path relativo, ou caminho relativo, é aquele que o início é o diretório corrente, ou seja, não precisamos informar o caminho a partir do `/`.

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ cd Documents/linuxNoobs/5-Segurança/
lucashe4rt@He4rt-PC:~/Documents/linuxNoobs/5-Segurança
```

> ## pwd

Na maioria dos casos, o terminal, não nos apresenta o local onde está localizada a pasta ou o arquivos podendo nos deixar perdidos dentro do nosso sistema.

Para evitarmos tendo que ficar subindo diretórios para nos situarmos dentro dos diretórios, nós utilizamos o comando `pwd`, o nome é um acrônimo para *print working directory*, que nos informa o diretório corrente, apresentando o caminho desde o diretório raiz até o atual.

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ pwd
/home/lucashe4rt
lucashe4rt@He4rt-PC:~$
```

---

## Referências

[Wikibooks - Linux Essencial/Lição Navegação básica via linha de comando](https://pt.wikibooks.org/wiki/Linux_Essencial/Li%C3%A7%C3%A3o_Navega%C3%A7%C3%A3o_b%C3%A1sica_via_linha_de_comando)

## Autor

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)