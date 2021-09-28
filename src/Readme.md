# Comandos

docker image build -t poferrari/conversao-temperatura:v1 .

docker image ls

docker container run -d -p 8080:8080 poferrari/conversao-temperatura:v1

docker container ls

docker container rm -f [CONTAINER_ID]

# Boas práticas

## Nomeando sua Imagem Docker
poferrari/api-conversao:v1
* poferrari: namespace (a quem pertence a imagem), proprietário - ID do dockerhub
* api-conversao: repositorio da imagem
* tag: versao da imagem, cada imagem terá uma versão, pode utilizar mesma versão da aplicação, utilizar o valor do número de Build, usar a latest (imagem mais atualizada)

## Preferência a imagens oficiais
* cuidado tem pessoas que criam imagens que ficam monitorando, não seguras, não utilize imagens desconhecidas

## Sempre especificar a tag nas imagens
* idempotência: garantir que sempre que construiu a imagem, ela terá o mesmo comportamento

## Um processo por container
* colocar o processo único, apenas uma parte da sua solução, terá vários containers se comunicando e formando sua solução, granularidade da sua aplicação, solução mais simples, mais clara
* um processo, um container - não colocar tudo em apenas um container

## Aproveitamento das camadas de imagem
* para ganhar desempenho na criação da imagem

## Utilize o .dockerignore
* se forma semelhante ao gitignore, ignorar a pasta, ignorar arquivo que não pode ser copiado

## COPY vs ADD
* utilizar sempre o COPY

## ENTRYPOINT vs CMD
* utilizado para inicializar o container
* ENTRYPOINT é imutável, não consegue sobreescrever, já o CMD você consegue sobreescrever na execução do container
* pode usar os dois combinados, CMD para passar parametros para o ENTRYPOINT, auxiliando na execução do container

## Uso do multistage