# Docker registry

1. Gerando um certificado auto-assinado

``` bash
sudo openssl req \
    -x509 \
    -nodes \
    -days 365 \
    -newkey rsa:2048 \
    -keyout certs/domain.key \
    -out certs/domain.crt
```

2. Gerando usuário e senha para o autenticação básica

``` bash
htpasswd -c auth admin
```

3. Executando o _registry_

```
docker-compose up -d
```