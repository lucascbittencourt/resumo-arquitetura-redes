# Proxy

Um servidor proxy é um intermediario em uma comunicação entre dois dispositivos em uma rede. Em uma rede do tipo cliente/servidor se ouver um servidor proxy a requisição é feita para o proxy, logo em seguida o servidor proxy faz a requisição para o servidor, o servidor responde o proxy e o proxy retorna a resposta ao cliente.

<p align="center">
CLIENTE >>> PROXY >>> SERVIDOR<br>
SERVIDOR >>> PROXY >>> CLIENTE
</p>

Existem dois tipos de servidores proxy, **proxy direto** e **proxy reverso**.

## Proxy direto

Esse tipo de servidor é utilizado para auxiliar os cliente, economizando banda e processamento com cache e mascarando sua origem.

### Cache

Um sistema de cache funciona para acelerar o carregamento de alguma coisa, por exemplo uma pagina web. O cache é um armazenamento de dados ja acessados que se não alterados ja são retornados diretamente ao invés de ser feita uma requisição para o servidor, economizando largura de banda, processamento e também assim acelerando o acesso à aquele conteúdo pois ja esta processado e pronto para exibição.

### Mascarar a origem

Um servidor proxy também pode servir para mascarar seu IP assim podendo acessar servidores que bloqueiam acesso vindo de determinadas faixas de IP pois no ponto de vista do servidor final sua requisição esta vindo do IP do proxy e não do seu IP verdadeiro.

Existem alguns problemas de usar servidores proxy para este propósito como a lentidão pois ao acessar o servidor diretamente a requisição passa pelo proxy, que pode estar em outro continente, antes de chegar ao destino e também tem problemas de segurança pois todos os dados passam por um intermediario (proxy) que não temos controle onde o administrador do mesmo pode capturar estes dados.

## Proxy reverso

Esse tipo de proxy é utilizado pra auxiliar os servidores, como firewall, balanceamento de carga, CDN e cache.

### Firewall

Funciona como um intermediario entre o servidor e a rede externa, a internet por exemplo, para o cliente ele aparentemente esta acessando o servidor diretamente enquanto na verdade esta passando pelo firewall primeiro que esta filtrando os pacotes de dados que estão passando.

### Balanceamento de carga

Para o cliente ele estará acessando um servidor/endereço único e o balanceador serve para distribuir as requisições que chegam naquele servidor/endereço entre varios servidores.

Um exemplo desse balanceamento é quando acessamos algum site muito movimentado, este site possui diversos servidores, o balanceador de carga manda a requisição para o servidor que estiver atrás dele e este servidor processa e retorna a resposta.

### CDN (Content Delivery Network)

Funciona de forma parecida com o balanceamento de carga, o cliente acessará um endereço/servidor único porém o servidor que responderá a requisição é o servidor geograficamente mais perto dele, já que os servidores são espalhados pelo mundo. 

Por exemplo, um cliente em algum lugar do Brasil acessa um site através de um endereço que esta hospedado nos EUA porém o servidor CDN (proxy reverso) que está no Brasil que irá responder aquela requisição se tiver o conteúdo daquele endereço armazenados em cache, caso não tenha irá redireciona-lo para o servidor localizado nos EUA.

### Cache

Funciona parecido com o sistema de cache do proxy direto porém auxiliando o servidor onde se o contéudo processado pelo servidor não tiver mudado ele irá entregar diretamente para o cliente economizando processamento do servidor e aumentando seu desempenho.

Conteúdos estáticos (imagens, paginas já processadas, etc) que ja foram processados e estão em cache, o servidor proxy reverso pode entregar diretamente o conteúdo ao invés de a requisição ser processada novamente pelo servidor.

---

<p align="center">
    <a href="./06-cooperativa.md">Voltar </a>|
    <a href="./08-vpn.md">Próximo</a>
</p>