# reaproveitando uma imagem base para construir essa aplicacao; nesse caso, estou utilizando sempre a ultima versao e deixando explicito (poderia deixar somente o nome node)
FROM node:latest
# especificando quem esta mantendo essa imagem
LABEL maintainer="Tairone Dias"
# criando variaveis de ambiente, nesse caso a porta que esta sendo utilizada no projeto
ENV PORT=3000
# copiando para dentro da imagem todo o codigo fonte dessa aplicacao, sendo: o ponto o path que esta o codigo e o "/application" o local onde sera copiado o codigo
COPY . /application
# especificando o diretorio onde esta os arquivos para ser instalado as dependencias e executar o servidor
WORKDIR /application
# instalando as dependencia do projeto assim que a imagem estiver sendo construída
RUN npm install
# declarando o comando que será executado assim que a imagem estiver concluída
ENTRYPOINT npm start
# definindo a porta que o container utiliza
EXPOSE $PORT