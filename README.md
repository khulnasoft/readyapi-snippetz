# Snippetz

[![CI](https://github.com/khulnasoft/readyapi-snippetz/actions/workflows/ci.yml/badge.svg)](https://github.com/khulnasoft/readyapi-snippetz/actions/workflows/ci.yml)
[![Release](https://github.com/khulnasoft/readyapi-snippetz/actions/workflows/release.yml/badge.svg)](https://github.com/khulnasoft/readyapi-snippetz/actions/workflows/release.yml)
[![Contributors](https://img.shields.io/github/contributors/khulnasoft/readyapi-snippetz)](https://github.com/khulnasoft/readyapi-snippetz/graphs/contributors)
[![GitHub License](https://img.shields.io/github/license/khulnasoft/readyapi-snippetz)](https://github.com/khulnasoft/readyapi-snippetz/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/%40khulnasoft/readyapi-snippetz)](https://www.npmjs.com/package/@readyapi/snippetz)
[![Discord](https://img.shields.io/discord/1135330207960678410?style=flat&color=5865F2)](https://discord.gg/8HeZcRGPFS)

> [!WARNING]
> This package is in early development. Don’t use it in production!

A modern way to generate code examples for different languages.

## Installation

```
npm install @readyapi/snippetz
```

## Usage

```js
import { snippetz } from '@readyapi/snippetz'

const snippet = snippetz().print('node', 'undici', {
  url: 'https://example.com'
})

/* Output */

// import { request } from 'undici'
//
// const { statusCode, body } = await request(
//   'https://example.com',
// )
```

## API

### Get all plugins

```js
import { snippetz } from '@readyapi/snippetz'

const snippet = snippetz().plugins()

/* Output */

// [
//   {
//     target: 'node',
//     client: 'undici',
//   }
// ]
```

### Check if a plugin is loaded

```js
import { snippetz } from '@readyapi/snippetz'

const snippet = snippetz().hasPlugin('node', 'undici')

/* Output */

// true
```

### Use just one plugin

```js
import { undici } from '@readyapi/snippetz-plugin-undici'

const source = undici({
  url: 'https://example.com'
})

console.log(source.code)

// import { request } from 'undici'

// const { statusCode, body } = await request(
//   'url': 'https://example.com',
// )
```

## Contributors

<!-- readme: collaborators,contributors -start -->
<table>
<tr>
    <td align="center">
        <a href="https://github.com/hanspagel">
            <img src="https://avatars.githubusercontent.com/u/1577992?v=4" width="100;" alt="hanspagel"/>
            <br />
            <sub><b>hanspagel</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/marclave">
            <img src="https://avatars.githubusercontent.com/u/6176314?v=4" width="100;" alt="marclave"/>
            <br />
            <sub><b>marclave</b></sub>
        </a>
    </td></tr>
</table>
<!-- readme: collaborators,contributors -end -->

Contributions are welcome! Read [`CONTRIBUTING`](https://github.com/khulnasoft/readyapi-snippetz/blob/main/CONTRIBUTING).

## License

The source code in this repository is licensed under [MIT](https://github.com/khulnasoft/readyapi-snippetz/blob/main/LICENSE).