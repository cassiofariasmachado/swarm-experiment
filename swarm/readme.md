# Docker Swarm

1. Criando um nó _manager_

``` bash
docker swarm init --advertise-addr <MANAGER-IP>
```

2. Gerando token para ingresso do segundo nó _manager_

``` bash
docker swarm join-token manager
```

3. Ingresso do segundo nó _manager_ ao Swarm

``` bash
docker swarm join --token <TOKEN> <MANAGER-IP>:2377
```