
# 🦀 Webpack 源码目录结构

阅读任何框架源码的第一步，都应该首先简略翻一遍目录结构，识别入口与关键部件

<div grid="~ cols-2 gap-2" m="-t-2">

<div>

重点：

- `lib`：核心代码目录
  - [`webpack.js`](https://github.dev/webpack/webpack/blob/HEAD/lib/webpack.js): Webpack 入口代码；
  - `Compiler.js`: 全局编译管理对象，每次启动都会 **生成一个** `Compiler` 对象实例；
  - `Compilation.js`: 单次编译对象，每次编译都会 **生成新的** `Compilation` 对象实例；
- `package.json`: 这个就不用多说了吧；

</div>


```md
webpack
├─ lib
│  ├─ asset
│  ├─ async-modules
│  ├─ dependencies
│  ├─ esm
│  ├─ javascript
│  ├─ ....
│  ├─ Compiler.js
│  ├─ Compilation.js
│  └─ webpack.js
├─ examples
│  └─ ...
├─ benchmark
│  └─ ...
├─ declarations
│  └─ ...
├─ schemas
│  └─ ...
├─ ...
└─ package.json
```

</div>