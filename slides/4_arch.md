# ð¦ Webpack æä»¶æ¶æ


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
    // 1. ç¹å®æ¶æºè§¦å
    this.hooks.make.call([...]);
  }
}

class XxxPlugin {
  apply(compiler) {
    // 2. æä»¶ä¸­çå¬é©å­
    compiler.hooks.make.tap("xxxPlugin", (compiler) => {
      // 3. é©å­åè°ä¸­ä¿®æ¹ä¸ä¸æå¯¹è±¡çç¶æ
      compiler.addEntry(xxx)
      // ...
    });
  }
}
```

</div>

<div  class="ml-8">

éç¹å¨äºï¼Webpack æ§è¡è¿ç¨ä¸­ï¼

1. ä¸å **æ¶æº** ä¼è§¦åä¸åé©å­ï¼
2. ä¸åé©å­ä¼ä¼ éä¸å **ä¸ä¸æåæ°** ï¼
3. ä¸åä¸ä¸æåæ°å¯ä»¥äº§çä¸å **äº¤äºææ**ï¼

<br/>

**ç»è®ºï¼Webpack ä¸»ä½åªæ¯å®ç°äºæææ ¸å¿çæå»ºæµç¨ï¼å¤§é¨ååè½é½ååç»ä¸åæä»¶å®ç°**

<br/>

</div>

</div>