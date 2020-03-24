# Criando pequenos Scripts no Linux

## Diretiva

A primeira característica de um script é a diretiva #!, que indica qual é o interpretador que será usado para ler e interpretar o script.
Para scripts de shell, é comum 
```console
#!/bin/bash ou #!/bin/sh
```

Outros interpretadores podem ser invocados pela linha "#!": #!/usr/bin/perl(no caso da linguagem perl), dentre outros.
No caso de um script de shell, a linha faz com que um novo processo de shell seja executado para interpretar o script.

## Herança

Como um novo shell é invocado para interpretar e executar o script, você vai ter herança de variáveis exportadas com o comando 
```console
export
```
do shell pai(chamou o script) e o shell filho(executa o script). A herança é um caminho único de pai para filho. Um script não passa variáveis para o shell pai.

## Variáveis especiais

Variáveis especiais que podem ser utilizadas:

$0: Retorna o nome do script que está sendo executado;

$1-$9: Retorna os parâmetros passados na linha de comando;

$#: Retorna o número de parâmetros passados;

$?: Recupera o valor de retorno do último comando;

$$: Retorna o número do PID do processo em execução.

## Test

O comando test é uma ferramenta para testar arquivos, permissões, números, etc. Ele pode testar diversas condições, fornecendo o resultado através da variável de retorno.

## If test

O comando if serve para executar algo SE determinada condição for satisfeita. Mas, diferente da maioria das linguagens como JavaScript, Java, Php, etc o if testa um comando e não uma condição. Para testar condições devemos utilizar o comando test junto com o if. Os colchetes podem usar usados no lugar do comando test. Abaixo algumas condições possíveis:

* -eq Igual
* != Diferente
* -gt Maior
* -lt Menor
* -d Se o arquivo for um diretório
* -e Se existir o arquivo
* -z Se o arquivo estiver vazio
* -f Se o arquivo contiver algum text
* -o Se o usuário for o dono do arquivo
* -r Se o arquivo pode ser lido
* -w Se o arquivo pode ser alterado
* -x Se o arquico pode ser executado

## for

O comando for permite que laços sejam executados, até que uma determinida variável percorra todos os valores de uma dada lista. 

## while 

O while testa uma expressão até que ela se torne falsa.

<hr />

Isso é o basico do ShellScript, uma ferramenta muito poderosa que podemos usar no nosso Pinguim. Se você se interessou e quer virar um Ninja do ShellScript eu recomendo o [Canal do professor Uirá Ribeiro](https://www.youtube.com/user/ueribeiro/videos), e em breve vamos trazer mais conteudos mostrando exemplos praticos de como usar o ShellScript no dia a dia.


# Refêrencias

https://www.youtube.com/user/ueribeiro/videos
https://www.youtube.com/user/bosontreinamentos


