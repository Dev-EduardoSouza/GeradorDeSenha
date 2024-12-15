
# Gerador Automático de Senhas

Este é um simples gerador automático de senhas construído com **Node.js** e **Express**. O projeto permite que o usuário gere senhas seguras de acordo com as especificações desejadas, como tamanho da senha, uso de letras maiúsculas, números e caracteres especiais.

## Funcionalidades

- **Gerar senhas** de tamanho personalizado.
- **Incluir caracteres maiúsculos**, minúsculos, números e caracteres especiais.
- **Resposta JSON** com a senha gerada.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução para JavaScript.
- **Express**: Framework minimalista para Node.js.
- **Body-parser**: Middleware para processar o corpo das requisições JSON.

## Instalação

1. **Clone o repositório**:

```bash
git clone https://github.com/seuusuario/gerador-senhas.git
cd gerador-senhas
```

2. **Instale as dependências**:

```bash
npm install
```

3. **Inicie o servidor**:

```bash
npm start
```

O servidor estará rodando na porta `3000`. Você pode acessar o gerador de senhas através de requisições HTTP.

## Como Usar

A API expõe um **endpoint** que gera senhas com base nas especificações fornecidas.

### Endpoint

**POST** `/generate-password`

### Corpo da requisição (JSON)

```json
{
  "length": 12,
  "useUppercase": true,
  "useNumbers": true,
  "useSpecialChars": true
}
```

- **length**: (obrigatório) O tamanho da senha desejada (um número maior que 0).
- **useUppercase**: (opcional) Se deve incluir caracteres maiúsculos (booleano).
- **useNumbers**: (opcional) Se deve incluir números (booleano).
- **useSpecialChars**: (opcional) Se deve incluir caracteres especiais (booleano).

### Exemplo de Requisição

```bash
curl -X POST http://localhost:3000/generate-password     -H "Content-Type: application/json"     -d '{"length": 16, "useUppercase": true, "useNumbers": true, "useSpecialChars": true}'
```

### Resposta

```json
{
  "password": "fJ#5gQ7&sL^aP1w!"
}
```

Caso algum parâmetro seja inválido ou ausente, o servidor retornará um erro com uma mensagem explicativa.

### Exemplo de Erro

```json
{
  "error": "O campo length (o tamanho da senha) deve ser um número maior que 0"
}
```

## Contribuição

Se você quiser contribuir para este projeto, fique à vontade para abrir **issues** ou **pull requests**.

