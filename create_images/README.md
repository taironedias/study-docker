### Create Images

O código fonte e o arquivo Dockerfile utilizado no build abaixo encontra-se [nesse folder]() aqui do repositório.

```bash
# dando build no Dockerfile para criar a minha imagem
    # a flag -f serve para especificar o nome do Dockerfile
    # a flag -t serve para definir um nome para sua imagem apos contruida
# por fim, o ponto é o path que está o arquivo Dockerfile
docker build -f Dockerfile -t taironedias/simple-node-app .
```

Assim, tudo dando certo ao executar o comando `docker images` é possível visualizar a sua imagem. Logo, basta criar um container a partir dele. Nesse exemplo, ficaria:
```bas
docker run -d -p 8081:3000 taironedias/simple-node-app
```


### Image Push for Docker Hub

```bash
# fazer o login no docker
docker login

# fazer o envio da sua imagem para o docker hub; nesse caso:
docker push taironedias/simple-node-app

# em qualquer outro computador, basta baixar a imagem ou baixar e executar
docker pull taironedias/simple-node-app

# assim, como visto nas instruções acima, basta executar a imagem
docker run -d -p 8082:3000 taironedias/simple-node-app
```