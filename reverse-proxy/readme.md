# Reverse proxy

1. Criando uma rede

``` bash
docker network create -d overlay swarm-network
```

2. Criando serviço com a API de demonstração

``` bash
docker service create \
    --name demo-api \
    --replicas 3 \
    --network swarm-network \
    demo-api
```

3. Buildando a imagem do proxy reverso

```
docker build -t reverse-proxy .
```

4. Gerando um certificado auto-assinado

``` bash
sudo openssl req \
    -x509 \
    -nodes \
    -days 365 \
    -newkey rsa:2048 \
    -keyout certs/domain.key \
    -out certs/domain.crt
```

5. Criando serviço de proxy reverso

``` bash
docker service create \
    --name reverse-proxy \
    --replicas 1 \
    -p 8090:80 \
    -p 9443:443 \
    --network swarm-network \
    reverse-proxy
```

6. Testando o redirecinamento

```
curl http://localhost:8090/WeatherForecast
```