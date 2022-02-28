## Anotações

### Accessar SSH
docker run -it nome_imagem bash


### Limpar todos containeres

> docker rm $(docker ps -a -q) -f


### Qual a diferença entre ENTRYPOINT e CMD ?

Diferença entre ENTRYPOINT e CMD é que o ENTRYPOINT sempre roda, e o CMD pode ser substituido pelo argumento do docker run.

### Para que serve $@ ?

Serve para ler o comando passado após o docker run no entry point:

No docker file fica assim:
> exec "$@"

>  docker run --rm nginx echo xurupita

No exemplo acima, roda o container e faz um echo de xurupita.


### Como publicar imagem no dockerhub?

> docker login

> docker push gsoldateli/nome-da-imagem


### Quais tipos de network docker suporta?

- Bridge: Requer exposição de porta para acessar 
- Host: Os containeres ficam na mesma rede que o host, não requer exposição de porta.
- Overlay : Comum usar com docker swarm para fazer containeres se comunicarem
- macvlan: Seta mac address e parece que é uma rede plugada aqui na minha red.
- none: Não faz parte da rede.


### Como saber as minhas redes ?

> docker network ls

### Como limpar redes não utilizada ?

> docker network prune


### Como saber quais containeres estão na mesma rede?

> docker network inspect nome_da rede

```
  "Containers": {
            "27173da026c4f34553c1c3eecc6a4c7d7873d2e7f4abd79184ad2483baeb9933": {
                "Name": "ubuntu2",
                "EndpointID": "44ae5421d2513bca823c0c75cd8d515f1356dd7431bad50b7af3e9778a3703f6",
                "MacAddress": "02:42:ac:11:00:03",
                "IPv4Address": "172.17.0.3/16",
                "IPv6Address": ""
            },
            "390b16dff3575257cb4404fcf01c54497ffcd92730b234f182355009b524ad90": {
                "Name": "ubuntu1",
                "EndpointID": "ce794769a635b18dd23987c286779f04d9725f72783c6d86ab657e66ef261fcc",
                "MacAddress": "02:42:ac:11:00:02",
                "IPv4Address": "172.17.0.2/16",
                "IPv6Address": ""
            }
        },
```


### Como criar uma rede?

> docker network create --driver bridge minharede

Para adicionar containers na mesma rede:

--network minha rede

> docker run -dit --name ubuntu1 --network minharede bash
> docker run -dit --name ubuntu2 --network minharede bash

Agora de dentro de ubuntu1 posso pingar diretamente ubuntu2 ou o ip dele.

### Como conectar um container que está rodando a uma rede

> docker network connect minharede ubuntu3


### Host network

- No Linux funciona
- Não funciona no MacOS
- Funciona com Windows + WSL2

### Como acessar docker host de dentro do container?

TL;DR; 

http://host.docker.internal:8000

Exemplo:

No seu host rode um serviço php:

> php -S 0.0.0.0:8000

Agora para acessar a porta 8000 de dentro de um container?

Roda container
> docker run --rm -it --name ubuntu ubuntu bash

Instala curl

> curl http://host.docker.internal:8000


### Como fazer para rodar um docker file com nome diferente?

Se por exemplo, você tem 2 docker files:

- Dockerfile
- Dockerfile.prod

Para usar o Dockerfile.prod, roda o comando com um -f

docker build -t nome-imagem . -f Dockerfile.prod


### Multi-stage building

Processo de gerar imagem para produção otimizada sem ter que refazer todo Dockerfile.


Definir um FROM como builder:

> FROM php:7.4-cli as builder ou qualquer coisa

Após toda build completa, consumir ela em um novo from.

> FROM php:7.4-fpm-alpine
> COPY --from=builder /var/www/laravel .


### Como fazer docker-compose rebuildar imagens?

> docker-compose up -d --build

### Como declarar dependencias entre containeres? 

docker-compose tem depends_on na versão 2, que não garante muito...

A melhor opção é utilizar **dockerize**. https://github.com/jwilder/dockerize



