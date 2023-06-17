# Swagger
Esse repositório é para guardar e compartilhar meus códigos da tecnologia swagger

* Conceitos básicos swagger:
1. URL: `https://Swagger.io`
2. o que é o Swagger?
    * É um conjunto de ferramenta para trabalhar com APIs de maneira dinamica e simplificada gerendo documentação, design e gerando código
3. o que o Swagger faz?
    * ele simplifica o desenvolvimento de APIs
4. Códigos Básicos:
    * Informações iniciais da sua documentação:
* Ex1:
```
openapi: 3.0.1
info:
  title: API de consutório
  description: API para controlar médicos e suas especialidades dentro do consultório.
  version: 0.0.1
  termsOfService: https://mockapi.io
  contact:
    name: Suporte a Devs
    email: contato@exemple.com
    url: https://mockapi.
  license:
    name: Licença GPLv3
    url: https://www.gnu.org/licenses/gpl-3.0.html
externalDocs:
  description: Documentação burocrática
  url: https://mockapi.io
```
* Ex2:

```
openapi: 3.0.1
info:
  title: API da Biblioteca
  description: API para controlar o fluxo de livros dentro de uma biblioteca publica
  version: 0.0.1
  termsOfService: https://github.com/escoladedevs/postman-em-1-hora
  contact:
    name: Suporte a Escola de Devs
    email: contato@exemple.com
    url: https://github.com/escoladedevs/postman-em-1-hora
  license:
    name: Lincença GPLv3
    url: https://www.gnu.org/licenses/gpl-3.0.html
externalDocs:
  description: Documentação Burogratica
  url: https://github.com/escoladedevs/postman-em-1-hora
```
* Servidor
```
servers: 
  - url: https://simple-books-api.glitch.me
```
* EndPoint - Status (Verifica todos os status)
```
paths:
  /status:
    get:
      summary: busca todos os livros
      responses:
        200:
          description: Sucesso
          content:
            application\json:
              example: 200
              schema:
                type: array
                items:
                  type: object
                    properties:
                      id:
                        type: integer
                    descrição:
                        type: string
```
