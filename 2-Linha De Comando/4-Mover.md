# 04 - Manipulação de arquivos e diretórios

## Conteúdo do artigo

[Criar - Arquivos e diretórios](#Criar)<br>
[Copiar - Arquivos e diretórios](#Copiar)<br>
[Mover - Arquivos e diretórios](#Mover)<br>
[Remover - Arquivos e diretórios](#Remover)<br>
[Referências](#Referências)<br>
[Autores](#Autores)

---

Como sabemos é possivel fazer muitas coisas utilizando a linha de comando, uma das funcionalidades também é a manipulação de arquivos que será abordado neste artigo.

> ## Criar

### **Diretórios**

Para criarmos diretórios utilizamos o comando `mkdir`, que é um acrônimo para *make directory*, ele cria novos diretórios em um sistema de arquivos.

Sintaxe:

```console
mkdir [opção] diretório
```

Exemplo:

```console
lucashe4rt@He4rt-PC:~$ mkdir Exemplo
lucashe4rt@He4rt-PC:~$ ls
Desktop  Downloads  Games  Images  Documents  Exemplo
```

Este comando também nos permite criar varios diretórios ao mesmo tempo somente passando o nome dos diretórios seguidos um do outro.

```console
lucashe4rt@He4rt-PC:~$ mkdir Exemplo2 Exemplo3 Exemplo4
lucashe4rt@He4rt-PC:~$ ls
Desktop  Downloads  Games  Images  Documents  Exemplo Exemplo2 Exemplo3 Exemplo4
```

Ele também permite criar uma estrutura de arquivos usando esse mesmo comando passando a opção `-p`.

```console
lucashe4rt@He4rt-PC:~$ mkdir -p Exemplo4/Exemplo5/Exemplo6
lucashe4rt@He4rt-PC:~$ ls Exemplo4
Exemplo5
lucashe4rt@He4rt-PC:~$ ls Exemplo4/Exemplo5/
Exemplo6
```

No caso acima nós criamos um diretório "pai" (Exemplo5) juntamente com um diretório "filho" (Exemplo6) dentro de outro diretório já existente (Exemplo4).

### **Arquivos**

O comando `touch` é muito utilizado para criarmos arquivos vazios porém ele também é capaz de alterar o registro de data e hora de arquivos e pastas mas não nos aprofundaremos nessa funcionalidade dele nesta seção.

Sintaxe:

```console
touch [opções] [nome_arquivo]
```

Vamos criar um arquivo vazio usando o comando `touch`:

```console
lucashe4rt@He4rt-PC:~$ touch exemplo1.txt
lucashe4rt@He4rt-PC:~$ ls
Desktop  Downloads  Games  Images  Documents  Exemplo Exemplo2 Exemplo3 Exemplo4
exemplo1.txt
```

Este comando também nos permite criar múltiplos arquivos somente passando o nome dos arquivos em seguida um do outro.

```console
lucashe4rt@He4rt-PC:~$ touch exemplo2.txt  exemplo3.txt
lucashe4rt@He4rt-PC:~$ ls
Desktop  Downloads  Games  Images  Documents  Exemplo Exemplo2 Exemplo3 Exemplo4
exemplo1.txt exemplo2.txt  exemplo3.txt
```

*Obs: podemos gerar nomes automaticos usando as chaves (`{}`) enquanto criamos varios arquivos desta maneira `touch exemplo{4..6}.txt`, este comando irá criar 3 arquivos chamados exemplo4.txt, exemplo5.txt e exemplo6.txt*.

#### Algumas outras funcionalidades do comando touch

Opção| Função
---  | ---
-a  *arquivo.txt* | Altera a hora de acesso do arquivo
-m  *arquivo.txt*| Altera a hora de modificação do arquivo
-am *arquivo.txt*| Altera a hora de acesso e modificação do arquivo
-c  *arquivo.txt*| Altera a hora de acesso sem criar um novo arquivo

> ## Copiar

Para copiarmos um arquivo ou um diretório nós usamos o mesmo comando, o `cp`, que nos permite copiar arquivos ou diretórios para outro local.

Sintaxe:

```console
cp [opções] arquivo_origem local_destino
```

Para copiarmos um arquivo:

```console
lucashe4rt@He4rt-PC:~$ cp exemplo1.txt exemplo2.txt
lucashe4rt@He4rt-PC:~$ ls
Desktop  Images  exemplo2.txt Exemplo  Documents  Downloads  exemplo1.txt
```

Para copiarmos um diretório nós adicionamos a opção `-r`:

```console
lucashe4rt@He4rt-PC:~$ cp -r Exemplo/ Exemplo2/
lucashe4rt@He4rt-PC:~$ ls
Desktop  Images  exemplo2.txt Exemplo  Exemplo2 Documents  Downloads  exemplo1.txt
```

Algumas opções comuns do comando `cp`:

Opção  | Função
---    | ---
-i     | Pergunta se desejamos sobrescrever um arquivo destino já existente
-n     | Não sobrescreve um arquivo já existente
-r, -R | Copia diretórios de forma recursiva
-p     | Preserva as permissões originais do arquivo (proprietário, grupo, etc.)

> ## Mover

Para movermos ou renomearmos um aquivo ou um diretório nós usamos o comando `mv`.

Sintaxe:

```console
mv [opções] arquivos_origem local_destino
```

Mover um arquivo ou diretório para outro local:

```console
# Movendo um diretório para dentro de outro
lucashe4rt@He4rt-PC:~$ mv Exemplo2 Exemplo
lucashe4rt@He4rt-PC:~$ ls Exemplo/
Exemplo2

# Movendo um arquivo para dentro de um diretório
lucashe4rt@He4rt-PC:~$ mv exemplo1.txt Exemplo/Exemplo2/
lucashe4rt@He4rt-PC:~$ ls Exemplo/Exemplo2/
exemplo1.txt
```

Renomear um arquivo ou diretório:

```console
# Renomeando um diretório
lucashe4rt@He4rt-PC:~$ mv Exemplo/Exemplo2/ Exemplo/Linux
lucashe4rt@He4rt-PC:~$ ls Exemplo/
Linux

# Renomeando um arquivo
lucashe4rt@He4rt-PC:~$ mv exemplo2.txt He4rtDevs.txt 
lucashe4rt@He4rt-PC:~$ ls
Desktop  Images He4rtDevs.txt Exemplo Documents  Downloads
```

Algumas opções do comando `mv`:

Opção|Função
---  | ---
-b | Cria um backup de cada arquivo destino existente
-f | Apaga destinos existente sem perguntar ao usuário
-i | Pergunta se desejamos sobrescrever o arquivo destino já existente
-n | Não sobrescrever um arquivo destino já existente

> ## Remover

Para removermos arquivos e diretórios nós utilizamos o comando `rm` que nos possibilita excluir diretórios vazios, não vazios e arquivos.

Sintaxe:

`rm [opções] conteudo_excluir`

Excluindo arquivos:

```console
lucashe4rt@He4rt-PC:~$ rm He4rtDevs.txt
lucashe4rt@He4rt-PC:~$ ls
Desktop  Images Exemplo Documents  Downloads
```

Para excluirmos diretórios nós passamos a opção `-r`:

```console
lucashe4rt@He4rt-PC:~$ rm -r Exemplo/
lucashe4rt@He4rt-PC:~$ ls
Desktop  Images Documents  Downloads
```

Algumas opções do comando `rm`:

Opção|Função
---  | ---
-f | Ignora arquivos existentes e não pergunta antes de remover
-r, -R| Remove diretórios e seus conteúdo recursivamente
-d, --dir| Remove somente diretórios vazios
-i | Pergunta se queremos remover o arquivo/diretório antes de excluir

---

## Referências

[LinuxForce - Comando mkdir](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-mkdir/)

[Hostinger - Comando touch](https://www.hostinger.com.br/tutoriais/comando-touch-linux)

[Bóson Treinamentos - Comando cp e mv](http://www.bosontreinamentos.com.br/linux/comandos-cp-e-mv-como-copiar-e-mover-arquivos-no-linux/)

[LinuxForce - Comando rm](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-rm/)

## Autor

* **Lucas Silva (LucasHe4rt)** - *Back-end Developer & Member of He4rt Developers* - [Twitter](https://twitter.com/lucashe4rt)