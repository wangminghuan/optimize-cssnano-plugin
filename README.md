
# optimizer-cssnano-plugin
> 修改自[optimize-cssnano-plugin](https://www.npmjs.com/package/@intervolga/optimize-cssnano-plugin)
只修改了test匹配规则部分，支持`?`拼接过的文件名

## Installation:

Using npm:

```shell
npm install --save-dev @optimizer-cssnano-plugin
```

## Configuration:

```javascript
const OptimizeCssnanoPlugin = require('optimizer-cssnano-plugin');

module.exports = {
  module: {
    loaders: [
      {
        test: /\.css$/,
        loader: ExtractTextPlugin.extract("style-loader", "css-loader")
      }
    ]
  },
  plugins: [
    new ExtractTextPlugin("styles.css"),

    new OptimizeCssnanoPlugin({
      sourceMap: nextSourceMap,
      cssnanoOptions: {
        preset: ['default', {
          discardComments: {
            removeAll: true,
          },
        }],
      },
    }),
  ]
}
```
