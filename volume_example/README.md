### Working Volumes

A instrução abaixo auxilia a execução de um container para realizar alterações ou subir um servidor para seu projeto. Tendo como exemplo um projeto em Node.js que o código está na pasta `/home/lorem/projects/simple-app`, você deseja subir essa aplicação, então como fazer com docker? Dividirei em etapas das quais listarei e explicarei abaixo, ao final estará o comando completo.

1. `docker run -d`: comando já visto, mas serve para executar um container e não travar o terminal;

1. `-p 8088:3000`: a flag **-p** indica que você irá especificar a porta que será executada localmente e a porta que será executada no container. Nesse caso, a porta **8088** você acessará no browser e a porta **3000** é a configurada no projeto node;

1. `-v "/home/lorem/projects/simple-app:/application"`: a flag **-v** indica que deseja obter volumes nessa execução do container e nesse caso específico, você está passando o path do projeto para um folder qualquer do container (no caso do node, poderia ser qualquer nome);

1. `-w "/application"`: a flag **-w** (working direct) serve para dizer pro container em qual pasta será executado o comando em node. Assim, tem que ser com o mesmo nome da pasta que foi definido na criação do volume;

1. `node`: nome da imagem oficial do Node.js que contém o comando `npm`;

1. `npm start`: comando que será buscado dentro da imagem e, nesse caso, executado;

Assim, o comando completo ficará:

```bash
docker run -d -p 8088:3000 -v "/home/lorem/projects/simple-app:/application" -w "/application" node npm start
```


```bash
# se desejar, pode utilizar o comando pwd e utilizar interpolação, por exemplo:
$ pwd
/home/lorem/projects/simple-app
$ docker run -d -p 8088:3000 -v "$(pwd):/application" -w "/application" node npm start
```