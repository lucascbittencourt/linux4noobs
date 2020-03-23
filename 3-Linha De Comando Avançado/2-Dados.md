# Condutores de Redirecionamentos

Existem  conceitos no Linux muito importantes, agora vamos falar um pouco sobre cada um.

## Entrada Padrão

A entrada padrão é todo o fluxo de dados que serve para dar entrada em um processo ou programa, coisas que vão de um mouse até um editor de texto.

## Saida Padrão

A saida padrão é tudo aquilo que o programa devolve, tudo que processa, coloca na tela ou terminal é a saida padrão, que também pode ser direcionada para um dispositivo, programa ou arquivo.

## Saida de Erro

A saida de erro é uma saida especial, o programa pode fazer uma separação entre a saida padrão e a saida de erro, para saber quando mostrar um erro e quando mostrar o conteudo.

<hr />

Se você executar o comando abaixo podera ver os 3 conceitos em forma de dispositivos.

```console
ls -l /dev/std*
```
Os dispositivos que tiverem a referencia 0 vão ser a entrada padrão, os que tiverem a referencia 1 vão ser a saida padrão e os que tiverem a referencia 2 vão ser a saida de erro.


```sql
mysql -uroot -psenha -d banco < sql.txt
```

Acima nos temos um exemplo de uma entrada padrão, para usar o MySql. Os comandos como ls e etc são uma saida padrão. 

<hr />

# Expressões Regulares

Uma expressão regular é um método formal de se especificar um padrão de texto a ser procurado em um ou mais arquivos.

É uma composição de caracteres com funções especiais, que agrupados entre si com caracteres literais e números, podem formar uma expressão queo shell pode entender e buscar.

Geralmente elas são usadas para buscar ou validar texto de coisas como:

* Email
* URL
* Data e Hora
* CNPJ, RG, CPF, ETC

Agora vou resumir um pouco a diferença entre os comandos Grep, Egrep e Fgrep.

## Grep

Pode ser utilizado para procurar expressões regulares simples . 

## Egrep

Pode ser utilizado para procurar expressões regulares simples e avançadas.

## Fgrep

Não pode ser usado para procurar expressões regulares, ele serve para fazer busca literais, ele é muito mais rapido se você estiver buscando alguma coisa que não usa expressões regulares.
