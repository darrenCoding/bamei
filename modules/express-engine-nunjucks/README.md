[![NPM version][npm-image]][npm-url]
[![David deps][david-image]][david-url]
[![node version][node-image]][node-url]
[![npm download][download-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/bamei-module-express-engine-nunjucks.svg?style=flat-square
[npm-url]: https://npmjs.org/package/bamei-module-express-engine-nunjucks
[david-image]: https://img.shields.io/david/leizongmin/bamei.svg?style=flat-square
[david-url]: https://david-dm.org/leizongmin/bamei
[node-image]: https://img.shields.io/badge/node.js-%3E=_4.0-green.svg?style=flat-square
[node-url]: http://nodejs.org/download/
[download-image]: https://img.shields.io/npm/dm/bamei-module-express-engine-nunjucks.svg?style=flat-square
[download-url]: https://npmjs.org/package/bamei-module-express-engine-nunjucks

# bamei-module-express-engine-nunjucks

express 框架使用 nunjucks 模板引擎

**本项目需要在 Node.js v6.0 或更高版本上运行**

## 安装

```bash
$ npm install bamei-module-express-engine-nunjucks --save
```

## 依赖模块

+ **bamei-module-express**@`*`


## 配置说明

```javascript
function fillDefaultConfig(config) {
  return Object.assign({
    // 自动转义输出的变量
    autoescape: true,
    // 监听文件变化，有更新时自动重载
    watch: true,
    // 当变量是undefined时抛出异常
    throwOnUndefined: false,
    // 删除标签空行
    trimBlocks: false,
    // 删除标签左边的空格
    lstripBlocks: false,
    // 不使用缓存
    noCache: true,
    // 模板引擎目录
    viewsDir: this.get('express.app').get('views'),
    // express实例
    express: this.get('express.app'),
    // 其他参考 nunjucks 模块
  }, config);
}
```

## 初始化

```javascript
module.exports = require('bamei').create(function (ctx) {
  // 先初始化依赖的模块
  ctx.module('express');
  
  // 使用 ctx.config.get('express-engine-nunjucks') 的配置初始化
  ctx.module('express-engine-nunjucks');
  // 或者
  // 自定义配置初始化
  const options = {};
  ctx.module('express-engine-nunjucks', options);
});
```



## License

```
MIT License

Copyright (c) 2016 Zongmin Lei <leizongmin@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
