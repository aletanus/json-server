# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Projetos Front-end.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"




---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

                                                > USERS <

------------------------------------------------ POST localhost:3001/users CRIAR USUÁRIO

H- Content-Type application/json

    {
        "name":"Aline",
        "email":"aline@mail.com",
        "password": "12345",
        "city":"Florianópolis",
        "state":"Santa Catarina" ,
        "img":"https://cdn-icons-png.flaticon.com/512/4140/4140048.png",
        "zipCode":"78735000"
    }

Caso dê tudo certo, a resposta será assim:

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQwNTg5LCJleHAiOjE2NzI5NDQxODksInN1YiI6IjUifQ.NUeVu4Aw0XnwmP-I2b32hMe577YhUm5ijMgDrlbTW9s",
"user": {
"email": "fulano@mail.com",
"id": 5
}
}


----------------------------------------------- PATCH localhost:3001/users/{idDoUsuario} EDITAR USUÁRIO

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

{
"email": "fulano@mail.com",
"password": "654321"
}

Caso dê tudo certo, a resposta será assim:

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQwNTg5LCJleHAiOjE2NzI5NDQxODksInN1YiI6IjUifQ.NUeVu4Aw0XnwmP-I2b32hMe577YhUm5ijMgDrlbTW9s",
"user": {
"email": "fulano@mail.com",
"id": 5
}
}


------------------------------------------------ DELETE localhost:3001/users/{idDoUsuario} DELETAR USUÁRIO

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

body {}

resposta 200 ou 201 {}


-------------------------------------------------- GET localhost:3001/users/{idDoUsuario} BUSCAR USUÁRIO

H- Content-Type application/json

body {}

Caso dê tudo certo, a resposta será assim:

{
"email": "aline@mail.com",
"password": "$2a$10$TWKfnMCQ.0h0zCBDe8eXMOpKBMgeW7.Puzedt1iS/O3mutLongtWu",
"Name": "Aline",
"City": "Florianópolis",
"State": "Santa Catarina",
"Img": "https://cdn-icons-png.flaticon.com/512/4140/4140048.png",
"zipCode": "78735000",
"id": 5
}


-----------------------------------------------------------------------------------------------------------------------------------------

                                            > LOGIN <

--------------------------------------------------- POST localhost:3001/login - LOGIN DE USUARIO

H- Content-Type application/json

{
'email": 'aline@mail.com'
'password': 12345
}

Caso dê tudo certo, a resposta será assim:

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ.7QhQZVkxbZ8lqvo7gkrQFNpbWNNkf_HS0I74isCNIL4",
"user": {
"email": "aline@mail.com",
"Name": "Aline",
"City": "Florianópolis",
"State": "Santa Catarina",
"Img": "https://cdn-icons-png.flaticon.com/512/4140/4140048.png",
"zipCode": "78735000",
"id": 5
}
}


------------------------------------------------------------------------------------------------------------------------------------------------

                                            > UNITY <

--------------------------------------------------- POST localhost:3001/unity - CRIAR UNIDADE(EMPRESA)

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

{
"userId":5,
"nome_fantasia": "teste1",
"codigo_cep_estabelecimento": "1345135135",
"endereco_estabelecimento": "AV CAMPOS SALES",
"numero_estabelecimento": "6",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "(34)34343434",
"descricao_turno_atendimento": "aaaaaaaaa"
}

Caso dê tudo certo, a resposta será assim:

{
"userId": 5,
"nome_fantasia": "teste1",
"codigo_cep_estabelecimento": "1345135135",
"endereco_estabelecimento": "AV CAMPOS SALES",
"numero_estabelecimento": "6",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "(34)34343434",
"descricao_turno_atendimento": "aaaaaaaaa",
"id": 5
}


-------------------------------------------------- DELETE localhost:3001/unity/{idDaunity} - FORMATO DA REQUISIÇÃO

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

body {}

Caso dê tudo certo, a resposta será assim:

resposta 200/201 {}


---------------------------------------------------- PATCH localhost:3001/unity/{idDaunity} EDITAR UNIDADE(EMPRESA)

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

{
"userId":5,
"nome_fantasia": "teste1",
"codigo_cep_estabelecimento": "1345135135",
"endereco_estabelecimento": "AV CAMPOS SALES",
"numero_estabelecimento": "6",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "(34)34343434",
"descricao_turno_atendimento": "bbbbbb"
},

Caso dê tudo certo, a resposta será assim:

{
"userId": 5,
"nome_fantasia": "teste1",
"codigo_cep_estabelecimento": "1345135135",
"endereco_estabelecimento": "AV CAMPOS SALES",
"numero_estabelecimento": "6",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "(34)34343434",
"descricao_turno_atendimento": "bbbbbb",
"id": 5
}


------------------------------------------------ GET localhost:3001/unity/{idDaUnity} BUSCAR UNITY(EMPRESA)

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

body vazio {}

Caso dê tudo certo, a resposta será assim:

{
"userId": 4,
"nome_fantasia": "TESTE",
"codigo_cep_estabelecimento": "XXX",
"endereco_estabelecimento": "XXX",
"numero_estabelecimento": "1",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "XXX",
"descricao_turno_atendimento": "24 HORAS",
"id": 4
}


------------------------------------------------ GET localhost:3001/unity BUSCAR TODAS AS UNITY(EMPRESA)

H- Content-Type application/json
Bearer Token : "eyJlbWFpbCI6ImFsaW5lQG1haWwuY29tIiwiaWF0IjoxNjcyOTQ0MjEwLCJleHAiOjE2NzI5NDc4MTAsInN1YiI6IjUifQ"

body vazio {}

Caso dê tudo certo, a resposta será assim:
[
{
"userId": 4,
"nome_fantasia": "TESTE",
"codigo_cep_estabelecimento": "XXX",
"endereco_estabelecimento": "XXX",
"numero_estabelecimento": "1",
"bairro_estabelecimento": "CENTRO",
"numero_telefone_estabelecimento": "XXX",
"descricao_turno_atendimento": "24 HORAS",
"id": 4
},

{
"userId": 3,
"nome_fantasia": "TES123TE",
"codigo_cep_estabelecimento": "X231XX",
"endereco_estabelecimento": "XX23X",
"numero_estabelecimento": "1",
"bairro_estabelecimento": "CENT23RO",
"numero_telefone_estabelecimento": "X23XX",
"descricao_turno_atendimento": "24 HOR23AS",
"id": 4
}

]
