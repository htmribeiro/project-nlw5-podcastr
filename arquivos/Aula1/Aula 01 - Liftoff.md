-plantmanager

create-react-app.dev

## criando um novo projeto

utilizando o pacote do node chamado **npx**

```powershell
npx create-react-app podcastr
```

```powershell
yarn start
  start the development server.

yarn build
  Bundles the app into static files for production.

yarn test
  Stars the test runner.

yarn eject
  Removes this tools and copies build dependencies, configurations files
  and scripts into the app directory. If you do this, you can´t go back!

we suggest that you begin by typing:

  cd podcatr
  yarn start

Happy hacking!
```

## Conceitos do React

No React:  

* tudo é criado como componente
* nunca podemos colocar um elemento embaixo do outro sem ter algo em volta deles.
  > Podemos utilizar os colchetes angulares sem conteúdo (desenvolvido pelo React). Esse conceito é chamado de **Fragmento**. Com isso não se gera uma nova tag div para ser apresentada nos elementos do HTML e resolve esse problema que o React tem.  
Ex:

```js
<>
  <Button title="Button 1" />
  <Button title="Button 2" />
  <Button title="Button 3" />
  <Button title="Button 4" />
  <Button title="Button 5" />
</>
```


### Componentes

É uma função que retorna HTML (App.js)  

### Propriedade

É uma informação que repassa de componente para outro

```html
<img src="" />
```
O que chamamos nO HTML de atributos, no React é chamado de propriedades.  
Ex.: `src=""`

Toda vez que precisamos mostrar uma variável JS dentro do HTML precisamos colocá-la dentro de um par de chaves `{}`

Sempre que passamos uma informação dentro de um componente, eu posso acessar essa informação dentro de **children**  
Ex.: `props.children`

> Repassando a informação de um componente **pai** para o **filho**

### Estado

É uma forma de manipular informações de dentro de um componente.

É uma informação que podemos armazenar dentro de um componente. E toda vez que o usuário realizar uma ação dentro do nosso componente esse valor possa ser alterado.

>```js
> import { useState } from 'react';
>```

??? Conceito de desestruturar array

## Next.js

### SSR (Server-side rendering)

### SSG (Static site generation)

### Criando projeto com Next.js

