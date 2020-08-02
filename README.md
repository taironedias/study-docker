### Install Docker and Docker Compose

Recomendo utilizar o site oficial para obter uma correta instalação. Segue os links abaixo:

- [Install Docker](https://docs.docker.com/engine/install/) (escolha seu SO ou distro)
    - [Install Docker for macOS](https://docs.docker.com/docker-for-mac/install/)
    - [Install Docker for Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- [Post-installation steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/)
- [Install Docker Compose](https://docs.docker.com/compose/install/)

Após a instalação de ambos, tudo dando certo os comandos abaixo irão exibir suas respectivas versões (no momento de escrita desse helper, foi apresentada essas versões):

```bash
$ docker --version
Docker version 19.03.12, build 48a66213fe

$ docker-compose --version
docker-compose version 1.26.2, build eefe0d31
```

---
### Utils Commands in Docker

```bash

# lista todos os containers em execução/ativos
docker ps

# lista todos os containers que estão parados ou criados
docker ps -a

# utilizar o terminal do SO como terminal do container
docker run -it NOME_CONTAINER

# executar um container específico que está parado
docker start ID_CONTAINER

# parar um container específico
docker stop ID_CONTAINER
# passando a flag -t e um numero significa o tempo que levará para ser parado (no exemplo abaixo, o tempo é zero, logo será imediatamente parado, se não passar a flag o tempo é 10s)
docker stop -t 0 ID_CONTAINER

# utilizando o terminal do SO como terminal do container, porém o container está parado
docker start -a -i ID_CONTAINER

# removendo um container parado
docker rm ID_CONTAINER

# parando e removendo um container que acabou de ficar parado
# obs.: eh meio agressivo essa instrucao ~mais pode ser utilizada
docker rm -f ID_CONTAINER

# limpando todos os containers parados/inativos
docker container prune

# visulizando as imagens já baixadas
docker images

# removendo imagens que foram baixadas
docker rmi NOME_REPOSITORIO

# a flag -d é para executar algum container e não travar meu terminar. Por exemplo:
docker run -d NOME_IMAGEM

# a flag -P faz o docker atribuir portas aleatórias para container a ser executado
docker run -d -P NOME_IMAGEM

# a flag -p (minúsculo) segue a mesma explicação acima, porém eu defino uma porta a ser executada
docker run -d -p 12345:80 NOME_IMAGEM 

# listando as portas que estão sendo utilizadas por um container
docker port ID_CONTAINER

# executando um container e atribuindo um nome para ele (assim, posso encerrar o container passando o nome em vez do id)
docker run -d --name nome-qualquer NOME_IMAGEM

# retornando apenas os ids dos containers em execução
docker ps -q

# encerrando todos os containers em execução
docker stop -t 0 $(docker ps -q)

# criando volumes
docker run -d -v "/caminho/que/ficara/salvo/o/que/foi/escrito:/caminho/container/de/onde/pretende/escrerver" NOME_IMAGEM



```

---
### [Working Volumes](./volume_example/README.md)

---
### [Create Images](./create_images/README.md)

---
### Networking Containers

```bash
# criando um rede para comunicacao entre os containers
docker network create --drive bridge NOME_REDE

# lista as redes presentes no docker, sendo a bridge a default
docker network ls

# atribuindo a rede criada ao container
docker run -d --name NOME_CUSTOM_CONTAINER --network NOME_REDE NOME_IMAGE
```
**Ps.:** Só é possível acessar um outro container através do seu `container_name` se os containers estiverem em uma rede criada.


```bash

```