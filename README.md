## Webpack

> Webpack : Estipula uma série de configurações que chamamos de loders que vai ensinar a nossa aplicação de como tratar vários tipos de arquivos como [hbs, js, sass, png, jpg] e etc ... ele basicamente pega esses arquivos e converte em arquivos no qual o browser compreenda como [js, png, jpg, css]

> Passo 1 : Instalar as bibliotecas do webpack

```bash
yarn add webpack webpack-cli babel-loader -D
```

- babel-loader : É a integração entre o babel e o webpack.

> Passo 2 : Criar um arquivo de configuração na raiz do projeto => 'webpack.config.js' e adicionar as configurações.

```js
// webpack.config.js

const path = require('path');

module.exports = {
    entry: path.resolve(__dirname, 'src', 'index.js'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx']
    },
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
}

/*
entry: Indica o arquivo principal da aplicação;
output: Indica o arquivo de saida do webpack;
resolve: Indica quais tipos de arquivos devem sem interpretados;
module: Onde fica as configurações de como a aplicação vai comportar quando estiver importando cada um dos tipos de arquivos ou seja quando importado arquivo javascript webpack vai lhe dar de uma forma quando estiver importando um arquivo png ou css vai lhe dar de outra forma.
*/
```

> Passo 3 : Executar o webpack

```bash
yarn webpack
```

