# NodeJS
## O que é?
- É uma plataforma que permite a utilização do Javascript dentro do âmbito do backend. Aplicações que rodam no servidor (interagem com banco de dados, apis(pagamento, serviço de endereço)).
- Conseguimos utilizar a mesma tecnologia que usamos nos navegadores para manipular o DOM no backend e construir nossas aplicações. 

## Criação do server.js
```js
import { createServer } from 'node:http'

const server = createServer((request, response) => {
  response.write('Hello World'); 
  
  return response.end()
})

server.listen(3333); 
// localhost: 3333
```

- **request**: serve para obter dados da requisição feita que o usuário está fazendo para o servidor HTTP. Como exemplo, dentro do request estamos criando uma funcionalidade da criação de um novo usuário. Dentro do usuário nos vamos buscar informações daquele usuário (nome, idade, endereço). **O request traz informações da requisição sendo feita para a nossa API**.  

- **response**: enquanto o response é o objeto que eu vou utilizar para devolver uma resposta para quem está chamando a minha API. 

## Frameworks
- Vai facilitar em várias coisas: consiga dividir o nosso servidor em várias rotas, vários endpoints. 

*Exemplo*: ter um modo DELETE que quero deletar um vídeo, um método POST para postar um vídeo, etc. 

// POST localhost:3333/videos
// DELETE localhost:3333/videos/1

- Integração com bibliotecas de terceiro, para envios de e-mail, autenticação, pagamento.
- O framework também facilita a gente trabalhar com banco de dados, que é uma das coisas que a gente vai trabalhar daqui a pouco, utilizando o banco de dados PostgreSQL (é o único opensorce).

## Dependências
- Fastify: npm install fastify

```js
import { fastify } from 'fastify'

const server = fastify();

server.get('/', () => {
  return 'Hello World'
})

server.get('/hello', () => {
  return 'Hello Rocketseat'
})

server.get('/node', () => {
  return 'Hello Node.Js'
})

server.listen({
  port: 3333
})
```

## CRUD: Create, Read, Update e Delete
### Objetivo: Criar uma API que gerencia vídeos

Aprenderemos sobre tipos de parâmetros aqui e informações que a gente pode enviar para cada requisição. 

- Métodos: são formas da gente diferenciar semanticamente ou seja, de acordo com significado, as ações que a gente faz numa API. 

Quando utilizamos o **GET** aqui dentro, a gente está utilizando o método **HTTP GET**, que é utilizado quando eu quero fazer uma operação na minha aplicação onde eu busco alguma informação. Então geralmente a gente faz isso por listagem, para obter um vídeo, etc. 

Método **POST**: Quando eu quero criar um registro, quando a gente for criar o vídeo.

Método **PUT**: Quando é para fazer uma alteração. 

Método **DELETE**: quando é para deletar. 