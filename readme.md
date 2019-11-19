# Docker Swarm Experiment

Um experimento simples utilizando Docker Swarm.

## Estrutura

``` bash
demo-api/ # -> API em .Net Core de demonstração
registry/ # -> Configuração de um repositório de imagens privado usando Docker Compose;
reverse-proxy/ # -> Configuração de um servidor Nginx responsável por ser um proxy entre os serviços do Swarm;
swarm/ # -> Configuração do Docker Swarm;
```

## Referências

* [Docker Swarm Load Balancing with NGINX and NGINX Plus](https://www.nginx.com/blog/docker-swarm-load-balancing-nginx-plus)
* [Docker Registry](https://docs.docker.com/registry)