Esse projeto foi criado para implementar um teste de processo seletivo

## Passo a passo
- É preciso instalar o docker caso não possua na máquina de teste;

1 Criar as imagens do docker (depois de clonar o projeto através do github e já dentro da raiz da pasta cianettest)

1.1 Criar a imagem para o backend: 

$ docker build -t back-image -f cianettest-back/Dockerfile .

1.2 Criar a imagem para o frontend: 

$ docker build -t front-image -f cianettest-front/Dockerfile .

2 Rodar os containers com as imagens recém criadas tanto para o frontend quanto backend

2.1 Container do backend

$ docker run -p 8080:8080 -rm back-image

2.2 Container do frontend

$ docker run -v ${PWD}:/app -v /app/node_modules -p 3001:3000 --rm front-image

Pronto, as máquinas devem estar rodando devidamente cada uma dentro do seu container. Para rodar localmente, o frontend
chama a API rest com o IP local (http://localhost:8080).

Acesse a tela através do endereço: http:localhost:3001 e deve aparecer a lista dos personagens. Ao clicar no personagem, 
o container se expande mostrando os quadrinhos. Para facilitar a montagem da tela, foi utilizada a biblioteca de componentes
Material-ui do Google.
