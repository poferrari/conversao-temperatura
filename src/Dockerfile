FROM node:14.17.5
# criar diretório de trabalho
WORKDIR /app
# copia dos arquivos que tem definição dos pacotes utilizados
COPY package*.json ./
# executar o comando, baixar pacotes de instalação
RUN npm install 
# uso das camadas, aproveitar o cache, ganhar desempenho, só roda se tiver alteração de pacote
# copiar os arquivos que faltam
COPY . .
# expor a porta
EXPOSE 8080
# comando de inicialização do container
CMD ["node", "server.js"]

