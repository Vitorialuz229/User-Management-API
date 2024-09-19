# User Management API                   [![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)

![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB)
![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)

## Descrição

Este projeto é uma API para gerenciamento de usuários, desenvolvida com Node.js, Express e Prisma ORM, utilizando o **MongoDB** como banco de dados. A API permite criar, visualizar, atualizar e deletar usuários, fornecendo endpoints para operações CRUD básicas. O Prisma atua como ORM para facilitar a interação com o MongoDB.

## Front-End
O código do front-end para esta API pode ser encontrado no repositório [User Management View](https://github.com/Vitorialuz229/User-Management-View.git).

## Funcionalidades

- **Criação de Usuários**: Adicionar novos usuários com `nome`, `idade` e `email`.
- **Leitura de Usuários**: Recuperar a lista completa de usuários ou filtrar usuários por nome.
- **Atualização de Usuários**: Atualizar informações de um usuário existente.
- **Deleção de Usuários**: Remover usuários do banco de dados.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução JavaScript no servidor.
- **Express**: Framework minimalista para criação de APIs REST.
- **Prisma ORM**: Ferramenta para manipulação de banco de dados com foco em produtividade e segurança de tipos.
- **MongoDB**: Banco de dados NoSQL utilizado para armazenar dados dos usuários.

## Pré-requisitos

- **Node.js**: Instalar a versão mais recente de [Node.js](https://nodejs.org/en/).
- **MongoDB**: Configurar um banco de dados MongoDB local ou usar o MongoDB Atlas.
- **Prisma CLI**: Instalado globalmente ou localmente via npm.

## Instalação

1. Clone o repositório:

```bash
   git clone https://github.com/Vitorialuz229/User-Management-API.git

   cd User-Management-API
```

2. Instale as dependências:

```bash
npm install
```

3. Instale o Prisma como dependência de desenvolvimento:

```bash
npm install prisma --save-dev
```

4. Inicialize o Prisma com suporte para MongoDB:

```bash
npx prisma init
```

5. Configure o MongoDB no arquivo .env. Um exemplo de configuração para o MongoDB Atlas:

```env
DATABASE_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/mydatabase?retryWrites=true&w=majority"
```

6. Execute o comando para sincronizar o Prisma com o banco de dados MongoDB:

```bash
npx prisma db push
```

7. Instale o cliente Prisma:

```bash
npm install @prisma/client
```

8. Execute a aplicação:

```bash
npm start
```
## Endpoints

### Criar Usuário

- **Método**: `POST`
- **Rota**: `/users`
- **Corpo da Requisição**:

```json
  {
    "name": "Paulo",
    "age": "23",
    "email": "Paulo@gmail.com"
  }
```

### Listar Todos os Usuários

- **Método**: `GET`
- **Rota**: `/users`
- **Corpo da Requisição**:

```json
[
  {
    "id": "66eae3261116fc1d6d0d49ef",
    "email": "vitorialuz@gmail.com",
    "name": "Vitoria",
    "age": "21"
  },
  {
    "id": "66eaeceaac92f1d5585226f5",
    "email": "mariamae@gmail.com",
    "name": "Maria",
    "age": "72"
  }
   {
    "id": "66eaefsafac92f1d55852grg4",
    "name": "Paulo",
    "age": "23",
    "email": "Paulo@gmail.com"
  }
]
```

### Buscar Usuário por Nome

- **Método**: `GET`
- **Rota**: `/users?name=Vitoria`
- **Corpo da Requisição**:

```json
[
  {
    "id": "66eae3261116fc1d6d0d49ef",
    "email": "vitorialuz@gmail.com",
    "name": "Vitoria",
    "age": "21"
  }
]
```

### Atualizar Usuário

- **Método**: `PUT`
- **Rota**: `/users/:id`
- **Corpo da Requisição**:

```json
{
  "email": "maria@gmail.com",
  "name": "Maria",
  "age": "70"
}
```

### Deletar Usuário

- **Método**: `DELETE`
- **Rota**: `/users/:id`
- **Corpo da Requisição**:

```json
{
  "message": "Usuário deletado com sucesso!"
}
```

## Prisma Studio

Você pode usar o Prisma Studio para visualizar e manipular os dados diretamente no banco de dados MongoDB com o seguinte comando:

```bash
npx prisma studio
```

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir um PR ou relatar problemas.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

