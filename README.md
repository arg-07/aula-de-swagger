# Swagger
Esse repositório é para guardar e compartilhar meus códigos da tecnologia swagger

* Repositório contendo documentação de uma API para Testes:

` https://github.com/escoladedevs/postman-em-1-hora `

* URL da API de Teste:

`https://6096015d116f3f00174b29ba.mockapi.io`

* Conceitos básicos swagger:
1. URL: `https://Swagger.io`
2. Swagger editor: `https://editor.swagger.io`
3. o que é o Swagger?
    * É um conjunto de ferramenta para trabalhar com APIs de maneira dinamica e simplificada gerendo documentação, design e gerando código
4. o que o Swagger faz?
    * ele simplifica o desenvolvimento de APIs
5. Códigos Básicos:
* Informações iniciais da sua documentação:

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/77fb29ee-397c-4d5c-b96c-25d94b244268)


```
openapi: 3.0.1
info:
  title: API de consultório
  description: API para controlar médicos e suas especialidades dentro do consultório.
  version: 0.0.1
  termsOfService: https://mockapi.io
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://mockapi.io
  license:
    name: "Lincença: GPLv3"
    url: https://www.gnu.org/licenses/gpl-3.0.html
externalDocs:
  description: Documentação burocrática
  url: https://mockapi.io
  
```
* Servidor

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/8251d29b-48bb-4298-b644-21fb4a3bcd6c)


```
servers:
- url: https://6096015d116f3f00174b29ba.mockapi.io/
  description: API de Test
```
* EndPoint - GET - especialidades (Realiza consulta generica)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/851714d5-74e7-4f35-8ef1-0fdaf5f6de68)

```
paths:
  /especialidades:
    get:
      summary: Realiza uma consulta generica
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
```

* EndPoint - POST - especialidades (Adiciona informações sem ID Fixo)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/8c0cbd58-b2a4-4b97-91cf-c5e28ac716be)


```
    post:
      summary: adiciona informações sem id fixo
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
```
* EndPoint - GET ID - especialidades (Realiza uma consulta generica de modo especifico pelo ID)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/7c1a5880-60ac-4716-b8f3-d3f4274df9e2)


```
/especialidades/{id}:
    parameters:
    - name: id
      in: path
      schema:
        type: integer
      required: true
    get:
      summary: Realiza uma consulta de modo especifico pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Especialidade não encontrada
          content:
            application/json:
              example: "Not Found"
```
* EndPoint - POST ID - especialidades (Adiciona informações com ID fixo)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/56d99c98-7a6d-407d-8367-a74bf07dde5d)


```
post:
      summary: adiciona informações com id fixo
      requestBody:
        content:
          application/json:
           schema:
             type: object
             properties:
               descricao:
                 type: string
      responses:
        201:
          description: sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
```
* EndPoint - DELETE - especialidades (Deleta informações)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/a6125f9e-7b92-48a1-a16e-820981512984)


```
    delete:
      summary: delete informações
      responses:
        200:
          description: apagado com sucesso
          content:
            application/json:
              example: 200 - apagado com sucesso
```
* EndPoint - PUT - especialidades (Atualiza informações informações)

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/23586d15-dae1-412e-a013-d70983bf5435)


```
put:
      summary: Atualiza informações
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        200:
          description: atualização realizada com sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Cadastro não encontrado na base de dados
```
* Código YML completo contendo todos os EndPoints

![image](https://github.com/arg-07/aula-de-swagger/assets/77308865/68095917-301a-4025-be92-2afbeb0b57c8)


```
openapi: 3.0.1
info:
  title: API de consultório
  description: API para controlar médicos e suas especialidades dentro do consultório.
  version: 0.0.1
  termsOfService: https://mockapi.io
  contact:
    name: Suporte a Devs
    email: contato@example.com
    url: https://mockapi.io
  license:
    name: "Lincença: GPLv3"
    url: https://www.gnu.org/licenses/gpl-3.0.html
externalDocs:
  description: Documentação burocrática
  url: https://mockapi.io
servers:
- url: https://6096015d116f3f00174b29ba.mockapi.io/
  description: API de Teste
paths:
  /especialidades:
    get:
      summary: Realiza uma consulta generica
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
    post:
      summary: adiciona informações sem id fixo
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        201:
          description: "Sucesso"
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
  /especialidades/{id}:
    parameters:
    - name: id
      in: path
      schema:
        type: integer
      required: true
    get:
      summary: Realiza uma consulta de modo especifico pelo ID
      responses:
        200:
          description: Sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Especialidade não encontrada
          content:
            application/json:
              example: "Not Found"
    post:
      summary: adiciona informações com id fixo
      requestBody:
        content:
          application/json:
           schema:
             type: object
             properties:
               descricao:
                 type: string
      responses:
        201:
          description: sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
    delete:
      summary: delete informações
      responses:
        200:
          description: apagado com sucesso
          content:
            application/json:
              example: 200 - apagado com sucesso
    put:
      summary: Atualiza informações
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                descricao:
                  type: string
      responses:
        200:
          description: atualização realizada com sucesso
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: integer
                  descricao:
                    type: string
        404:
          description: Cadastro não encontrado na base de dados
```
