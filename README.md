<h1 align="center">
  <center>Prisma: ORM Node.js
</center>
</h1>

<p align="center">Projeto para testar as funcionalidade do ORM Prisma, que está em alto no momento.</p>

## 👨🏼‍💻 Base

- [Prisma: o ORM Node.js que você precisa em 2022](https://www.youtube.com/watch?v=nuLTwqPNq-w)

## ✋🏻 Pré-requisitos

- [Node.js](https://nodejs.org/en/)
- [Yarn](classic.yarnpkg.com/en/docs/install)

## 🔥 Instalação e execução

1. Faça um clone desse repositório;
2. Entre na pasta `cd prisma_decode`;
3. Rode `yarn` ;
4. Rode `yarn prisma generate` para instalar os models do prisma no projeto
5. Rode `yarn dev` ou `npm run dev` para rodar a aplicação;
6. Acesse a URL `http://localhost:4003`;

## Como mostrar log da aplicação?

```ts
const prismaClient = new PrismaClient({
  log: ["error", "info", "query", "warn"],
});
```

## Como incluir informações em um select com relacionamento

```ts
const product = await prismaClient.product.findFirst({
  where: {
    id,
  },
  include: {
    ProductCategory: {
      // Seleciona o model
      include: {
        category: true, // Dentro do model seleciono o relacionamento que quero trazer completo.
      },
    },
  },
});
```

---
