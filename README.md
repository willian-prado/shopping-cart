## Projeto Shopping Cart

> Oitavo projeto do módulo de Fundamentos do curso de desenvolvimento web da Trybe.

**Contexto**

Este projeto, o mais desafiador do primeiro módulo, visa colocar em prática os conteúdos aprendidos sobre Web Storage
e assincronicidade em JavaScript.

**Objetivo do projeto**

Desenvolver um carrinho de compras dinâmico similar aos que existem em e-commerces.
Para listarmos os produtos à venda usamos a API do Mercado Livre.
O [manual da API do Mercado Livre](https://developers.mercadolivre.com.br/pt_br/itens-e-buscas) contém muitas informações sobre ela.

**Principais habilidades desenvolvidas nesse trabalho:**

- Fazer requisições a uma API *(Application Programming Interface)* do Mercado Livre;
- Utilizar conhecimentos sobre JavaScript, CSS e HTML;
- Trabalhar com funções assíncronas;

**Tecnologias utilizadas**
- <a href="https://www.w3.org/html/"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" title="HTML5" title="HTML" align="center" height="35" /> - HTML </a>
- <a href="https://www.w3schools.com/css/"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" title="CCS3" title="CSS" align="center" height="35"/> - CSS </a>
- <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" title="JavaScript" align="center" height="30"/>  - JavaScript</a>

---

### Lista de requisitos propostos pela Trybe:

#### Obrigatórios

**1 - Crie uma listagem de produtos**

Você deve criar uma listagem de produtos que devem ser consultados através da API do Mercado Livre.

Você deve utilizar o _endpoint_:
```javascript
"https://api.mercadolibre.com/sites/MLB/search?q=$QUERY"
```
onde `$QUERY` deve ser o valor da sua busca. Para este trabalho, a busca deve ser **obrigatóriamente** o termo `computador`.

O retorno desse _endpoint_ será algo no formato `json`. A lista de produtos que devem ser exibidos está no _array_ `results`.

Você **deve** utilizar a função `createProductItemElement(product)` para criar os componentes _HTML_ referentes a um produto.

Adicione o elemento retornado da função `createProductItemElement(product)` como filho do elemento `<section class="items">`.

**Obs:** as variáveis `sku`, no código fornecido, se referem aos campos `id` retornados pela API.

**2 - Adicione o produto ao carrinho de compras**

Cada produto na página _HTML_ possui um botão com o nome `Adicionar ao carrinho!`.

Ao clicar nesse botão você deve realizar uma requisição para o _endpoint_:
```javascript
"https://api.mercadolibre.com/items/$ItemID"
```
onde `$ItemID` deve ser o valor `id` do item selecionado.
Preste atenção que o JSON deve conter apenas **um** item.

Você **deve** utilizar a função `createCartItemElement()` para criar os componentes _HTML_ referentes a um item do carrinho.

Adicione o elemento retornado da função `createCartItemElement(product)` como filho do elemento `<ol class="cart__items">`.

**3 - Remova o item do carrinho de compras ao clicar nele**

Ao clicar no **produto no carrinho de compra**, ele deve ser removido da lista.
Para isso, uma função (já existente) chamada `cartItemClickListener(event)` deve ser implementada com a lógica necessária para realizar a remoção.

**4 - Carregue o carrinho de compras através do `LocalStorage` ao iniciar a página**

Ao carregar a página, o estado atual do carrinho de compras deve ser carregado do **LocalStorage**.
Para que isso funcione, o carrinho de compras deve ser salvo no **LocalStorage**, ou seja, todas as **adições** e **remoções** devem ser abordadas para que a lista atual seja salva.

**5 - Some o valor total dos itens do carrinho de compras**

Cada vez que se adicionar um item ao carrinho de compras, será necessário somar seus valores e apresentá-los na página principal do projeto. O elemento que tem como filho o preço total dos itens do carrinho deve ter, **obrigatóriamente**, a classe `total-price`.

Obs: Devemos tomar cuidado, no entanto, pois estamos buscando os dados do produto em uma API. Portanto, é necessário garantir que a API já retornou as informações para somente depois realizar o cálculo da soma.

**6 - Crie um botão para limpar carrinho de compras**

Crie um botão para remover todos os itens do carrinho de compras. Ele deve, **obrigatóriamente**, ter a classe `empty-cart`.

**7 - Adicione um texto de "loading" durante uma requisição à API**

Uma requisição à API gasta um tempo e durante ele, ficamos sem saber se está tudo certo ou se algo deu errado.
Normalmente é utilizada alguma forma para mostrar que a requisição está em andamento.
Mostre a palavra "loading..." em algum lugar da página **apenas durante** a requisição à API. O elemento mostrado durante o carregamento da página deve, **obrigatóriamente**, ter a classe `loading`.
