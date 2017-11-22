# esi-webpack-plugin

> A Webpack plugin to resolve ESI includes.

Useful in conjunction with [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) to resolve ESI includes (using [nodesi](https://github.com/Schibsted-Tech-Polska/nodesi)) in all emitted HTML files.

## Install

```sh
npm install -D esi-webpack-plugin
```

## Usage

Options map more or less directly to the options provided by
[nodesi](https://github.com/Schibsted-Tech-Polska/nodesi).

```js
const EsiWebpackPlugin = require('esi-webpack-plugin');

module.exports = {
  // ...
  plugins: [
    new HtmlWebpackPlugin(),
    new EsiWebpackPlugin({
      baseUrl: 'http://example.com',
      onError(src, err) {
        console.error(`Error when resolving ${src}: ${err}`);
      },
      processOptions: {
        headers: {
          'Authorization': 'Basic Zm9vOmJhcgo='
        }
      }
    })
  ]
};
```

## License

MIT
