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

- response: enquanto o response é o objeto que eu vou utilizar para devolver uma resposta para quem está chamando a minha API. 