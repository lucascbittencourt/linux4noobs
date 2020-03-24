# Hardware

Agora nos vamos falar sobre Hardware. 

## CPUS

![amd](https://http2.mlstatic.com/processador-cpu-amd-athlon-64-x2-am2-21-g-ado4000iaa5dd-D_NQ_NP_610955-MLB31865302667_082019-F.jpg)

O primeiro que eu quero falar é a CPU, as CPUS são desenhadas com arquiteturas diferentes, ou seja, a forma que ela vai trabalhar todos os comandos que ela é capaz de fazer. Uma CPU sempre vai lidar com zeros e uns, transformando esse bits em dados diferente, fazendo transformações de dados com operações simples como; subtração, divisão, troca de bytes em espaço de memoria e coisas do tipo, e como ela faz isso vai definir a sua arquitetura, e a sua arquitetura define os comandos. Atualmente os computadores dektops trabalham com uma arquitetura chamada x86, que foi criada pela IBM nos anos 80, e hoje em dia nos temos a Intel e AMD que fazem esses chips. Os celulares utilizam outro tipo de arquitetura, que é chamado de A9 que utilizam outros tipos de Cpus, que são capazes de fazerem coisas diferentes, então o software precisa der compilado para cada tipo de CPU. Para você descobrir qual seu tipo de CPU no linux é facil, basta rodar o comando abaixo.

```shell
cat /proc/cpuinfo |less
```

## Memória RAM

![ram](https://40297.cdn.simplo7.net/static/40297/sku/2148_63dfd212-3fb2-4cf2-a74f-429429dfa15e_909x448.jpg)

A memória ram é um dispositivo que pode armazenar dados, e pode mover eles de uma maneira muito rapida, e a cpu só consegue tratar os dados quando eles estão na memória ram, todo hardware tem uma parte que é chamada DNA, então ali a CPU acessa a memória e trata os dados, o comando que usamos no Linux para ver as informações de memória é o Free.

```shell
free
```

Ele vai mostrar a memoria usada, a memoria disponivel, a memoria compartilhada e a memoria cache, é bom lembrar que a memória ram é volatil, então quando você desliga a maquina todos os dados que estão nela são apagados. 

## Placa Mãe

![mae](https://images0.kabum.com.br/produtos/fotos/98160/placa-mae-gigabyte-p-intel-lga-1151-atx-z390-gaming-sli-ddr4_1538513261_g.jpg)

A placa mãe é aonde você vai encaixar praticamente todos os componentes do seu computador. O comando para você ver todos os componentes conectados na sua Placa Mãe é o dmidecode.


```shell
dmidecode |less
```

Aqui você vai ter todas as informações da BIOS, que é um programa inicial que é gravado em um chip que fica na mãe e vai dar a carga inicial no computador e conferir todos os dispositivos conectados, e a BIOS depois passa o controle do computador para o gerenciador de boot, que vai carregar o sistema operacional, no nosso caso o KERNEL do Linux. Nos temos também a informação do DNI da placa, que é como ela trabalha com a questão de todos os perifericos, e as informações de todos os slots, voltagens, caches que se tem em cada entrada PCI da sua Placa Mãe. 

## Fonte

![Fonte](https://cdn.pichau.com.br/catalog/product/cache/a8a821144233824f257ff007174b65b4/p/g/pg-5001-br2.jpg)

A fonte de alimentação precisa ser suficiente para abastecer todos seus perifericos, cpus e coisas do tipo. Em servidores é normal você ter varias fontes para caso alguma pare de funcionar, as fontes possuem varios conectores, não só para Placa Mãe, por causa de alguns perifericos que precisam de um conector propio(placas de video por exemplo). 

## HD

![HD](https://static3.tcdn.com.br/img/img_prod/374123/17871_1_20161227105914.jpg)

Os HDs são a parte do computador onde os dados são armazenados. Diferente de memória ram eles são uma memória não-volátil, ou seja, as informaçãos armazenadas nele não são perdidas quando o computaodr é desligado, atualmente é o principal meio de armazenamento em massa. Nos computadores mais moderno, ele também é usado para expandir a memória RAM, através da gestão de memória virtual. O comando para acessar as informações do seu HD no Linux é o DF.

```shell
df
```

