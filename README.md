# Pipeline de ETL com Python - Bootcamp Santander 2025

## Enriquecendo descrições de produtos de um E-Commerce com IA Generativa
Este projeto demonstra a aplicação de um pipeline de ETL (Extract, Transform, Load) utilizando Python para aprimorar descrições de produtos em uma plataforma de e-commerce fictícia (Serverest API). O objetivo principal é enriquecer a qualidade das descrições dos produtos, tornando-as mais detalhadas e atrativas, através da integração de Inteligência Artificial Generativa.
## API Utilizada: https://serverest.dev/


## Pré-requisitos
> **Importante:** Essa etapa é feita devido a exclusão dos dados periodicamente na API.

### 1. Criar Usuário.
**Path:** https://serverest.dev/usuarios

**Método: POST**

**Body da requisição:**
```json
{
  "nome": "Fulano da Silva",
  "email": "fulano@email.com",
  "password": "teste",
  "administrador": "true"
}
```
### 2. Fazer Login e guardar o token de autenticação.
**Path:** https://serverest.dev/login

**Método: POST**

**Body da requisição:**
```json
{
  "email": "fulano@email.com",
  "password": "teste"
}
```
>O token é recebido após realizar o login.

**Path:** https://serverest.dev/login

**Body da requisição:**
```json
{
  "message": "Login realizado com sucesso",
  "authorization": "Seu token aqui"
}
```
### 3. Criar produtos teste.
**Path:** https://serverest.dev/produtos

**Método: POST**

**Body da requisição:**
```json
{
  "nome": "Nome do Produto",
  "preco": 10.00,
  "descricao": "Descrição",
  "quantidade": 10
}
```

------------


## Extract
#### Trazer as informações dos produtos por ID e os guardar em uma lista.

**Path:** https://serverest.dev/produtos/{_id}

**Método: GET**

------------


## Transform
#### Utilizar a biblioteca e a API do OpenAI para gerar uma descrição mais detalhada e chamativa para cada produto.

------------


## Load
#### Atualizar os produtos na API com as novas descrições via ID.

**Path:** https://serverest.dev/produtos/{_id}

**Método: PUT**

**Body da requisição:**
```json
{
  "nome": "Nome do Produto",
  "preco": 10.00,
  "descricao": "Descrição",
  "quantidade": 10
}
```
