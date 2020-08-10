# Linux Na Rede

## Protocolo TCP/IP

O TPC/IP é o protocolo padrão de comunicação padrão entre computadores, existem duas versões deste protocolo:

* IPv4: Utiliza uma estrutura de endereço formada por 4 octetos contendo números de 0 a -255. Exemplo: 192.168.0.1.

* IPv6: Utiliza uma estrutura de 128 bits, com notação em Hexadecimal.

Agora vamos falar um pouco sobre o modelo OSI contra o TCP/IP

![OSITCP](https://www.dltec.com.br/blog/wp-content/uploads/2019/02/osi-tcp-ip.png)

Do lado direito dessa imagem nos temos o modelo de arquitetura de redes que é o modelo OSI, esse modelo prevê camadas de redes. A ideia é que cada camada forneça serviços de redes para a camada superior, a trilha de protocolo TCP/IP implementou esse modelo de maneira mais simples, agora vamos falar um pouco mais sobre cada uma dessas camadas.

## Parte eletrica ou otica

É responsavel por manter um fluxo de bits de forma crua por algum meio, como um cabo de rede.

## Interface com a Rede

Geralmente aqui nos vamos ter um protocolo para a troca de dados(Ethernet). 

## Protocolo IP

Vai definir os endereços de rede dos dispositivos ligados a essa rede e a forma de como um pacote de dados vai de um remetente para um destinatario.

## Transporte

Aqui trabalham os protocolos de transporte das informações, que é responsavel por como os pacotes são enviados de um remetente para um destinatário. O TCP/IP tem dois protocolos de transporte, o TCP e o UDP. 

## Aplicação

É nessa camada que os protocolos das aplicações vão trabalhar, como HTTP e etc. Esses protocolos de aplicações dependendo do tipo de comunição que precisam, vão fazer um uso de um protocolo de transporte melhor para as suas necessidades, vamos falar disso agora.

# Camadas do TCP/IP

![TCP/IP](https://infotecnews.com.br/wp-content/uploads/2017/01/camada-tcpip-osi-1.jpg)

Aqui estão as camadas do TCP/IP e os seus protocolos, vamos falar um pouco mais de cada um.

## Rede

* ETHERNET: Ethernet é uma arquitetura de interconexão pare redes locais, baseada no envio de pacotes. Ela define cabeamento e sinais elétricos para a camada física em formato de pacotes e protocolos para a subcamada de controle de acesso ao meio(MAC). Desde os anos 90 ela vem sendo a tecnologia de LAN mais amplamente utilizada e tem tomado grande parte do espaço de outros padrões de rede que vamos citar a seguir.

* Token Ring: Token Ring é um protocolo de rede que opera na camada rede do protocolo TCP/IP. Usa um token, que consiste em uma trama de três bytes,que circula numa topologia em anel em que as estações devem aguardar a sua recepção para transmitir, a transmissão ocorre durante uma pequena janela de tempo, e apenas por quem detém o Token.

* Frame Relay: É uma tecnologia de comunicação de dados usada para transmitir da maneira rápida e barata(qb) a informação digital através de uma rede de dados, dividindo essas informações em frames a um ou muitos destinos de um end-point. 

* ATM: É projetado para unificar as telecomunicações e as redes de computadores. Ela foi projetada para uma rede que deve manipular tanto tráfego tradicional de dados de altas taxas de transferência, e conteúdo de baixa latência e de tempo real com voz e vídeo.

## Internet

* IP: É um protocolo de comunicação usado entre todas as máquinas em rede para encaminhamento de dados.

* ARP: É um padrão da telecomunicação, é usado para a resolução de enredereços(conversão) da camada de internet em endereços de camada enlace.

* ICMP: É um protocolo integrande do Protocolo IP, é utilizado para fornecer relatórios de erros à fonte original. Qualquer computador que utilize IP precisa aceitar as mensagens ICMP e alterar o seu comportamento de acordo com o erro relatado. Os gateways devem estar programados para enviar mensagens ICMP quando receberem datagramas que provoquem algum erro.

## Transporte 

TCP: É um dos protocolos de comunicação, da camada de transporte, que dão suporte a rede global Internet, verificando se os dados são enviados na sequência correta e sem erros via rede. É complementado pelo protocolo da Internet, normalmente chamado de, TCP/IP.

UDP: É um protocolo simples, ele é descrito na RFC 768 e permite que a aplicação envia um datagrama encapsulado num pacote IPv4 ou IPv6 a um destino, porém sem qualquer tipo de garantia que o pacote chegue corretamente(ou de qualquer modo). O protocolo UDP não é confiável, caso garantias sejam necessárias, é preciso implementar uma série de estrutura de controle, tais como timeouts, retransmissões, acknowledgments, controle de fluxo, etc.

## Aplicação

HTTP: É um protocolo de comunicação utilizado para sistemas de informação de hipermídia, distribuídos e colaboraticos. Ele é a base para a comunicação e dados na World Wide Web.

FTP: É um protocolo padrão independente de hardware sobre um modo de transferir arquivos/ficheiros e também é um programa de transfêrencia.

SMTP: É o protocolo padrão de envio de mensagens de emails através da Internet entre dois dispositivos computacionais, definido na RFC 821.

DNS: É um sistema hierárquico e distribuído de gestão de nomes para computadores, serviços ou qualquer máquina conectada à Internet ou a uma rede privada.

<hr />

Isso é o basico que você precisa pelo menos conhecer sobr redes, se quer aprender mais recomendo o canal [Certificação Linux](https://www.youtube.com/user/ueribeiro/videos111111111)

