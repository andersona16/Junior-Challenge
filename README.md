## Documentação da API

## Variáveis de Ambiente

Para rodar esse projeto, você vai precisar adicionar as seguintes variáveis de ambiente no seu .env

- DB_TYPE= # O tipo do banco de dados (ex: postgres, mysql)
- DB_HOST= # O host do banco de dados (ex: localhost)
- DB_PORT= # A porta do banco de dados (ex: 5432)
- DB_USERNAME= # O nome de usuário do banco de dados
- DB_PASSWORD= # A senha do banco de dados
- DB_DATABASE= # O nome do banco de dados

Como rodar as migrações

Instalar as dependências:

Certifique-se de que todas as dependências estão instaladas executando:

```bash
yarn install
```

```bash
Criar uma nova migração:

Caso você precise criar uma nova migração, use o comando abaixo, substituindo NomeDaMigration pelo nome da sua migração:

yarn typeorm migration:create ./src/database/migrations/NomeDaMigration
```

```bash
Rodar as migrações:

Após criar ou baixar as migrações, você pode executá-las com o seguinte comando:

yarn typeorm -- -d ./src/database/connection migration:run
```

#### Criar um Anel

```http
POST /api/rings
```

| Parâmetro   | Tipo     | Descrição                              |
| :---------- | :------- | :------------------------------------- |
| `name`      | `string` | **Obrigatório**. Nome do anel          |
| `power`     | `string` | **Obrigatório**. Poder do anel         |
| `carrier`   | `string` | **Obrigatório**. Transportador do anel |
| `forgedBy`  | `string` | **Obrigatório**. Forjador do anel      |
| `image_url` | `file`   | **Obrigatório**. Imagem do anel        |

Respostas:

- 201 Created: Anel criado com sucesso.
- 400 Bad Request: Campos obrigatórios faltando ou forjador inválido.
- 500 Internal Server Error: Erro ao adicionar um novo anel.

```json
[
  {
    "id": "string",
    "name": "string",
    "power": "string",
    "carrier": "string",
    "forgedBy": "string",
    "image_url": "http://example.com/uploads/image.jpg"
  }
]
```

#### Retornar Todos os Anéis

```http
GET /api/rings
```

Respostas:

- 200 OK: Lista de todos os anéis.
- 500 Internal Server Error: Erro ao buscar anéis.

```json
[
  {
    "id": "string",
    "name": "string",
    "power": "string",
    "carrier": "string",
    "forgedBy": "string",
    "image_url": "http://example.com/uploads/image.jpg"
  }
]
```

#### Retornar um Anel

```http
GET /api/rings/${id}
```

| Parâmetro | Tipo     | Descrição                                   |
| :-------- | :------- | :------------------------------------------ |
| `id`      | `string` | **Obrigatório**. ID do anel que você deseja |

Respostas:

- 200 OK: Anel encontrado.
- 400 Bad Request: ID inválido.
- 404 Not Found: Anel não encontrado.
- 500 Internal Server Error: Erro ao buscar o anel.

#### Atualizar um Anel

```http
PUT /api/rings/${id}
```

| Parâmetro   | Tipo     | Descrição                              |
| :---------- | :------- | :------------------------------------- |
| `name`      | `string` | **Obrigatório**. Nome do anel          |
| `power`     | `string` | **Obrigatório**. Poder do anel         |
| `carrier`   | `string` | **Obrigatório**. Transportador do anel |
| `forgedBy`  | `string` | **Obrigatório**. Forjador do anel      |
| `image_url` | `file`   | **Obrigatório**. Imagem do anel        |

Respostas:

- 200 OK: Anel atualizado com sucesso.
- 400 Bad Request: ID inválido ou forjador inválido.
- 404 Not Found: Anel não encontrado.
- 500 Internal Server Error: Erro ao atualizar o anel.

```json
[
  {
    "id": "string",
    "name": "string",
    "power": "string",
    "carrier": "string",
    "forgedBy": "string",
    "image_url": "http://example.com/uploads/image.jpg"
  }
]
```

#### Deletar um Anel

```http
DELETE /api/rings/${id}
```

| Parâmetro | Tipo     | Descrição                                   |
| :-------- | :------- | :------------------------------------------ |
| `id`      | `string` | **Obrigatório**. ID do anel que você deseja |

Respostas:

- 200 OK: Anel deletado com sucesso.
- 400 Bad Request: ID inválido.
- 404 Not Found: Anel não encontrado.
- 500 Internal Server Error: Erro ao deletar o anel.

## Junior Challenge - Frontend

Este repositório contém o frontend do projeto Junior Challenge, desenvolvido utilizando Vite, React, e TypeScript. Este documento descreve o processo de instalação, os principais scripts, a estrutura do projeto, e as dependências usadas.


## Instalação


Para instalar e configurar o projeto localmente, siga os seguintes passo


## 1. Clone o repositório:

```bash
git clone https://github.com/andersona16/Junior-Challenge.git
cd Junior-Challenge/frontend
```

## 2. Instale as dependências necessárias com o comando:

```bash
npm install

ou 

yarn install
```

## Scripts

Os seguintes scripts estão disponíveis no arquivo package.json para facilitar o desenvolvimento e o build do projeto:

```bash
npm run dev: Inicia o servidor de desenvolvimento com o Vite.

npm run build: Constrói o projeto para produção.

npm run preview

npm run lint
```

## Estrutura do Projeto


A estrutura do diretório frontend é organizada da seguinte forma:


```bash
frontend/
├── src/
│   ├── App.tsx            # Componente principal da aplicação React
│   ├── assets/            # Recursos como imagens, fontes, etc.
│   ├── components/        # Componentes reutilizáveis da aplicação
│   ├── context/           # Definição de Context API para gerenciamento de estado global
│   ├── interface/         # Definição de interfaces TypeScript usadas no projeto
│   ├── main.tsx           # Arquivo de entrada principal que inicializa a aplicação React
│   ├── pages/             # Páginas principais da aplicação
│   ├── routes/            # Definição de rotas do React Router
│   ├── services/          # Serviços para chamadas de API e outras funcionalidades
│   ├── styles/            # Arquivos de estilização global e componentes estilizados
│   ├── utils/             # Funções utilitárias e helpers do projeto
│   └── vite-env.d.ts      # Arquivo de definição de tipos para o Vite e TypeScript
```

## Principais Dependências

- React: Biblioteca para construção da interface do usuário.
- React Router Dom: Gerenciamento de rotas.
- Axios: Utilizado para chamadas HTTP.
- Styled Components: Estilização de componentes com CSS-in-JS.
- Yup: Validação de formulários.
- React Toastify: Exibição de notificações de forma fácil.
- React Slick: Criação de carrosséis de imagens.
- React Icons: Conjunto de ícones para uso em componentes.


## Ferramentas de Desenvolvimento

- TypeScript: Suporte a tipos estáticos.
- ESLint: Ferramenta de linting para garantir qualidade e consistência do código.
- Vite: Ferramenta de construção rápida e moderna.
- Definições de Tipos: Utilizadas para fornecer suporte de tipos ao trabalhar com bibliotecas - JavaScript em TypeScript.