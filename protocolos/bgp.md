[README](/README.md)

# BGP  
 
- **Fundamentos do BGP**  
    **BGP**(Border Gateway Protocol) é o protocolo usado para ligar todas as redes da internet.  
    O poder queo BGP nos dá é a capacidade de manipular os caminhos do tráfego, ex, o trafego sair por um lado e voltar por outro, no caso de ter mais de um link.  
**Border gateway protocol version**
|RCF|Date|Version|
|:--:|:--:|:--:|
|1105|1989|1|
|1163|1990|2|
|1267|1991|3|
|1654 e 1771|1994 e 1995|4|  

O BGP é utilizamo muito mais do que como um protocolo de roteamento de internet, ele é amplamente utilizado  em diversos cenários  como DC, Cloud, Sec, IoT e outros.  


- **ASN**  
    Autonomous Systems - um ASN é um conjuntonde redes em um único domínio administrativo, dentro de um ASN estão os blocos de IPs públicos, dentro de um domínio administrativo, podemos usar os IGPs como o OSPF e IS-IS.  
    Assim como a rede re IPs públicos, um ASN tem que ser registrado, a IANA é quem fornece estes registros  
    Existem ASNs Publicos e os privados, caso seja necessário rodar um BGP em uma organização  
    Um erro comum, é uma empresa divulgar um prefixo de outra empresa, e acabar "sequestrando" o tráfego para ela, portando hoje existem ferramentas para proteger deste tipo de erro

 - **Path Vector**  
    Para o BGP, não importa quantos roteadores ele atravessa e sim quantos ASs, para escolher o melhor caminho, caso tenha mais de um caminho para chegar em uma rede, o BGP analisa um conjunto de atributos chamado PATH-ATRIBUTES ou PA.  
|BGP Path Atributes são classificados da seguinte maneira|
|:-:|
|**Well Known (Bem conhecidos)** - Devem ser obrigatóriamente conhecidos por todas as implementações BGP|
|**Optional** Como o próprio nome diz, são atributos opcionais e sua implementação não é obrigatória|  


- **Loop prevention**  
    Quando uma rede é divulgada para outro ASN, é divulgado também um atributo qu é o AS-Path, que é o caminho que este prefixo já percorreu, quando um AS recebe um anuncio de um prefixo que seja tenha seu própio AS, não é instalado na sua tabela de roteamento evitando o loop.  
    ![](/Imagens/BGP_img_01.png)  
    
iBGP x eBGP  
COnfiguração inicial  