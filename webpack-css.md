# webpack 如何处理 css

- 项目中配置
- 使用的 loader or plugin
- 原理

## 项目中的配置

```javascript
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const HTMLWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          // 根据运行环境判断使用那个 loader
          process.env.NODE_ENV === 'development'
            ? 'style-loader'
            : MiniCssExtractPlugin.loader,
          'css-loader',
        ],
      },
    ],
  },
  plugins: [new MiniCssExtractPlugin(), new HTMLWebpackPlugin()],
};
```

## 需要使用的插件

- style-loader
- css-loader
- mini-css-extract-plugin（将 css 单独提取到文件中，为每个 css 文件的 js 文件创建一个 css 文件，支持 css 按需加载，注意：这是 webpack5 特性）
- extract-text-webpack-plugin（5 之前的版本用这个）

## 原理

### css-loader

- css-loader 的作用是帮我们分析出各个 css 文件之间的关系，把各个 css 文件合并成一段 css
- 将 css 文件转化为 js 模块
