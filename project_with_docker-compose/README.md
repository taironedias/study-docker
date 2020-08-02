## Docker Compose

Principais instruções do docker-compose:

**Obs.:** É importante que os comandos sejam executados dentro do diretório que está o arquivo `docker-compose.yml`.

```bash
# faz o build dos dockerfiles criados
docker-compose build

# sobe os serviços e cria os containers, caso alguma imagem não exista ainda no computador o mesmo é baixado nesse momento.
    # utilizando a flag -d o terminal é liberado após subir os containers
docker-compose up -d

# listando todos os serviços/containers que foram subidos
docker-compose ps

# parar os serviços e removê-los
docker-compose down
```

Para exemplificar a criação do docker-compose, foi utilizado o projeto do curso de Docker da Alura do cap06, modificando para as respectivas sintaxe e utilização atual.
