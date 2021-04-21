# Aula 02 - Maximum Speed

## Next.js

### SSR (Server-side rendering)

### SSG (Static site generation)

### Criando projeto com Next.js

```powershell
npx create-next-app podcastrnext
```

```powershell
Inside that directory, you can run several commands:

  yarn dev
    Starts the development server.

  yarn build
    Builds the app for production.

  yarn start
    Runs the built app in production mode.

We suggest that you begin by typing:

  cd podcastrnext
  yarn dev
```

## TypeScript

> Instalação do TypeScript

```powershell
yarn add typescript @types/react @types/node -D
```

* Packages
  * **`@types/react`** - Integração do React com o TypeScript
  * **`@types/node`**  - Integração do Node com o TypeScript
  * **`-D`** - instalação na dependência de desenvolvimento, pois o typescript só roda em desenvolvimento, em produção o nosso código é convertido para JavaScript.

Após a instalação do TypeScript, iremos fazer a conversão dos arquivos `*.js` para `*.tsx` da pasta **pages**.

* **`tsx`** = typescript + jsx (xml e html no javascript)

## Criação dos estilos globais da aplicação

A pasta **pages** no *next*, só pode existir, ou na raiz do projeto ou dentro da pasta **src**, portanto criaremos a pasta **src**.

### Instalação do SASS

```
yarn add sass
```

Após a instalação do SASS, iremos fazer a conversão dos arquivos `*.css` para `*.scss` da pasta **styles**.

> Por via de regra para acessibilidade iremos trabalhar com as medidas:

* `rem` - nos valores
* `%` - nos medias queries

### Instalação da biblioteca de data do JS

```powershell
yarn add date-fns
```

### Instalação da biblioteca json-server

```powershell
yarn add json-server -D
```

> após instalação da biblioteca:

* Fazer a configuração do server do arquivo **package.json**, incluíndo dentro de `scripts`

```json
"server": "json-server server.json -w -d 750 -p 3333"
```

* **Parâmetros**
  * Aplica o `json-server`  no arquivo ***sever.json***.
  * `-w` (watch mode) - sempre que atualizar uma informação dentro desse servidor, ele irá reiniciar
  * `-d 750` (delay) - faz com que toda requisição para essa API demore 750 segundos para responder.
  * `-p 3333` (porta) - ao qual a API irá rodar.

> Comando para rodar o json-server

```powershell
yarn server
```

## SPA vs SSR vs SSG

```ts
// SPA

import { useEffect } from 'react'

export default function Home() {
  useEffect(() => {
    fetch('http://localhost:3333/episodes')
    .then(response => response.json())
    .then(data => console.log(data))
  }, [])

  return (
    <h1>Index</h1>
  )
}
```

```ts
// SSR

export default function Home(props) {
  return (
    <div>
      <h1>Index</h1>
      <p>{JSON.stringify(props.episodes)}</p>
    </div>
  )
}

export async function getSeverSideProps() {
  const response = await fetch('http://localhost:3333/episodes')
  const data = await response.json()

  return {
    props: {
      episodes: data,
    }
  }
}
```

```ts
// SSG

export default function Home(props) {
  return (
    <div>
      <h1>Index</h1>
      <p>{JSON.stringify(props.episodes)}</p>
    </div>
  )
}

export async function getStaticProps() {
  const response = await fetch('http://localhost:3333/episodes')
  const data = await response.json()

  return {
    props: {
      episodes: data,
    },
    revalidate: 60 * 60 * 8
  }
}
```
# código da aula
`#embuscadoproximonivel`