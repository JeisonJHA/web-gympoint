<h1 align="center">
  <img alt="Gympoint" title="Gympoint" src=".github/logo.png" width="200px" />
</h1>

<h4 align="center">
  A gym app that allow the students to make de register and questions.
</h4>

<p align="center">
  <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/jeisonjha/web-gympoint.svg">

  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/jeisonjha/web-gympoint.svg">

  <a href="https://www.codacy.com/manual/JeisonJHA/web-gympoint?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=JeisonJHA/web-gympoint&amp;utm_campaign=Badge_Grade">
    <img src="https://api.codacy.com/project/badge/Grade/aa3da21389b94437990040f2913eb5cd"/>
  </a>

  <img alt="Repository size" src="https://img.shields.io/github/repo-size/jeisonjha/web-gympoint.svg">
  <a href="https://github.com/jeisonjha/web-gympoint/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/jeisonjha/web-gympoint.svg">
  </a>

  <a href="https://github.com/jeisonjha/web-gympoint/issues">
    <img alt="Repository issues" src="https://img.shields.io/github/issues/jeisonjha/web-gympoint.svg">
  </a>

  <img alt="GitHub" src="https://img.shields.io/github/license/jeisonjha/web-gympoint.svg">
</p>
<p align="center">
  <a href="#rocket-sobre-o-desafio">Sobre o desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#layout">Layout</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-entrega">Entrega</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-licença">Licence</a>
</p>

## 🚀 Sobre o desafio

Durante esse desafio vamos construir o front-end da aplicação Gympoint que criamos o back-end durante os desafios dos módulos 02 e 03 de Node.js.

A versão web do projeto Gympoint representa a visão da academia, ou seja, todas funcionalidades presentes na versão web são para administradores. As funcionalidades para o aluno serão dispostas no aplicativo mobile.

### Novas funcionalidades

Antes de iniciar a parte web, **adicione as seguintes funcionalidades no back-end** da aplicação:

1. Adicione um campo boolean `true/false` na listagem de matrículas indicando se a matrícula está ativa ou não, ou seja, se a data de término é posterior à atual e a data de início inferior (utilize um campo `VIRTUAL`).

Por exemplo, no model de Matrícula, adicione um novo campo:

```js
active: {
  type: Sequelize.VIRTUAL(Sequelize.BOOLEAN, [
    'start_date',
    'end_date',
  ]),
  get() {
    return (
      isBefore(this.get('start_date'), new Date()) &&
      isAfter(this.get('end_date'), new Date())
    );
  },
},
```

E na query:

```js
const registrations = await Registration.findAll({
  attributes: ['id', 'start_date', 'end_date', 'price', 'active']
});
```

2. Permita que a listagem de alunos (`/users`) seja filtrada por nome recebendo um Query Parameter `?q=Diego` e buscando no banco usuários com esse filtro (utilize o operador `like`). Caso o parâmetro não seja passado, retorne todos usuários;

### Informações importantes

1. Antes de deletar qualquer registro do banco crie uma verificação adicinal usando a função `confirm` do JavaScript;
2. Para formatação de datas utilize sempre a biblioteca `date-fns`;
3. Não realize formatações de valores dentro do `return ()` nos componentes React, opte por formatar os dados assim que recebidos da API;
4. No cadastro/edição de planos e matrículas os inputs com fundo cinza são calculados automaticamente com base na seleção dos outros valores;
5. No cadastro/edição de matrícula deve ser possível buscar o aluno pelo nome, utilize o método `async` da biblioteca [React Select](https://react-select.com/home#async). Os planos devem ser buscados da API assim que a página carregar e não devem possuir filtro.

### Opcionais

1. Adicione paginação no front-end e back-end para todas listagens;
2. Utilize máscaras para inputs numéricos de valores, peso e altura;

## 🎨 Layout

O layout do desafio está em anexo como um arquivo `.sketch`.

Caso esteja usando OS X / Windows você pode abrir esse arquivo com um software chamado [Zeplin](https://zeplin.io).

Caso esteja no Linux ou não vá usar o Zeplin existe uma pasta chamada `Gympoint WEB` junto com esse repositório, baixe-a e acesse o arquivo `index.html` para visualizar as telas da aplicação.

## 📅 Entrega

Esse desafio **não precisa ser entregue** e não receberá correção. Além disso, o código fonte **não está disponível** por fazer parte do **desafio final**, que será corrigido para **certificação** do bootcamp. Após concluir o desafio, adicionar esse código ao seu Github é uma boa forma de demonstrar seus conhecimentos para oportunidades futuras.

## 📝 Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---

Made by Jeison Azevedo :wave: [Get in touch!](https://www.linkedin.com/in/jeison-azevedo/)
