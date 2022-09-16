# 🦀 Webpack 插件架构


<div grid="~ cols-2 gap-4" m="-t-2">

<div>

```js
class Compiler {
  constructor() {
    this.hooks = {
      make: new AsyncParallelHook(["compilation"]),
    };
  }
  compile() {
    // ...
    // 1. 特定时机触发
    this.hooks.make.call([...]);
  }
}

class XxxPlugin {
  apply(compiler) {
    // 2. 插件中监听钩子
    compiler.hooks.make.tap("xxxPlugin", (compiler) => {
      // 3. 钩子回调中修改上下文对象的状态
      compiler.addEntry(xxx)
      // ...
    });
  }
}
```

</div>

<div  class="ml-8">

重点在于，Webpack 执行过程中：

1. 不同 **时机** 会触发不同钩子；
2. 不同钩子会传递不同 **上下文参数** ；
3. 不同上下文参数可以产生不同 **交互效果**；

<br/>

**结论：Webpack 主体只是实现了最最核心的构建流程，大部分功能都分发给不同插件实现**

<br/>

</div>

</div>