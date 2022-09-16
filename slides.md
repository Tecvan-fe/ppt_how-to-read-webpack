---
theme: ./theme
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
css: unocss
title: 如何阅读 [Webpack](https://webpack.js.org/) 源码
---

# 🦀 如何阅读 [Webpack](https://webpack.js.org/) 源码

### 有一些关于 Webpack 源码分析、学习的技巧想分享给大家

<div class="pt-12">
  <span class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    范文杰@字节跳动
  </span>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: image-left
image: /掘金社区_推广海报.jpeg
---


# 关于我


- 👨‍💻 范文杰，来自广东汕尾
- 🧑‍💻 目前就职于 **字节跳动-飞书-前端团队**
- 📝 《[Webpack5 核心原理与应用实践](https://juejin.cn/book/7115598540721618944)》作者
- 🎨 公众号「**Tecvan**」作者
- 🦀 十级帝王蟹爱好者

<br>
<br>

<img src="/20220220-002839.jpg" class="w-55"/>

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->


---

# 🦀 为什么？


<div grid="~ cols-2 gap-4" >

因为 Webpack 依然是值得学习的技术方向之一！

**但是**

<div>

- 大多数公司的工程化基建都基于 Webpack 实现；
- Webpack 应用场景更广泛，包括小程序、桌面端应用等；
- Webpack 久经沙场，稳定性更强；
- ...
- Webpack 依然是兼容性、成长性、成熟度最高的构建工具；

</div>

<div>

- 这并不容易，很多同学其实用都用不明白，更谈不上开发 **Plugin**、**Loader** 等自定义组件。

</div>

</div>

**究其底层原因，主要还是在于对 Webpack 底层实现逻辑缺乏必要理解。**

---
layout: center
---

# 🦀 归根结底，还是对底层实现逻辑不够熟悉

---


# 🦀 Webpack 源码很复杂，很晦涩


```sh
git clone git@github.com:webpack/webpack.git
```

<br/>

### 代码量

| Language   | files | blank | comment |      code |
| :--------- | ----: | ----: | ------: | --------: |
| JavaScript |   537 |  8994 |   21062 | **85593** |

<br />

<div grid="~ cols-2 gap-4">
<div>

- **51** 种 `Module` 类型；
- **78** 种 `Dependency` 子类；
- **459** 种 Class；
- **257** 个 Hook；
- **171** 种内置插件；

</div>

<div class="text-2xl">

- 过度复杂的架构设计
- 老旧的 `Callback` 风格
- 不少 Duplicate 代码
- **更重要的是，资料很少**

</div>
</div>


<style>
  
</style>

---

# 🦀 So, 怎么办？

<div grid="~ cols-2 gap-4">
<div>

## 肝！

<br />

<img src="/1rkift4cg0l.jpeg">

不过，我这里有一些 **学习 Webpack 源码** 的技巧

</div>
<div>

<v-clicks>

## Table of Content

### 背景知识
- 源码结构详解
- 基本调试技巧

### 核心源码解析
- 理解常见代码流转逻辑
- 理解 Webpack 构建主流程
- 源码阅读技巧

</v-clicks>

</div>
</div>


---
src: ./slides/1_file-structure.md
---


---
src: ./slides/2_bootstrap.md
---


---
src: ./slides/3_progress.md
---

---
layout: center
class: text-center
---
# 🦀 如何剖析被 Hooks 封装的那部分代码

---
src: ./slides/4_arch.md
---

---
src: ./slides/5_arch-anlysis.md
---


---
src: ./slides/6_arch-tools.md
---


---
src: ./slides/7_main-thread.md
---

---
src: ./slides/8_make-phase.md
---

---
src: ./slides/9_seal-phase.md
---

---
layout: center
class: text-center
---
# 🦀 Blabla~~

总之，这事儿不容易，但沿着这个脉络，是可以 [做到](https://bytedance.feishu.cn/docs/doccnZeQsT5OpHqZCACSsbZbpuh) 的！

![](/blogs-capture.png)

---

# 🦀 画饼

真的学会之后，你可以：

<div grid="~ cols-2 gap-4" m="-t-2">

<v-clicks>

- 比较自在写一些 Plugin、Loader
- 遇到问题能迅速反应过来真没解决
- 有能力做一些偏基建的事情
- 有能力优化已有基于 Webpack 项目的构建性能
- 学习能力变强，下次再来一个复杂系统也不至于很慌
- ...

</v-clicks>

<div class="text-center">

<img src="/20220220-002839.jpg" class="w-60 dib" />

</div>

</div>

---
src: ./slides/10_skill.md
---

---

# 🦀 最佳实践

<v-clicks>

- **目标明确**：设定好具体、可衡量的目标，不要为了学习而学习，如果有切实的强诉求，那就别由于彷徨，马上去做
- **补充输入源**：磨刀不误砍柴工，不要上来就对着源码疯狂输出，一定要花点时间站在高层视角去看框架的背景和生态
- **抓大放小**：忽略哪些还不熟悉的概念、语句、工具、分支逻辑，你要认识到复杂事物的学习模型往往螺旋上升，逐步深入的，不可能过一遍就能掌握所有细节和精髓，如果一开始就过度关注细节，通常会让整个学习周期拉到无限长。要弄清楚啥时候，什么情况下应该忽略细节，什么时候应该抓住不放 —— 这与你的目标和切入点有很大的关系
- **随时记录**：一旦有任何新发现、新问题，做好笔记，记录下来，这些都会成为继续探索的重要线索
- **随时总结**：
  - 笔记记录当下的、零碎的发现，总结则将这些线索串联形成知识点。
  - 总结过程你会发现更多认知漏洞，提出更多问题，可以反过来继续挖掘
  - 好记性不如烂笔头，探索的结果落到纸面上才会真正成为你自己的东西，极端一点看，没有形成输出的学习过程往往会随着时间的流逝，变成徒劳


</v-clicks>

---
layout: center
class: text-center
---

# 谢谢观看

我叫范文杰，喜欢吃螃蟹

<div grid="~ cols-2 gap-4" m="-t-2" class="text-left">

<div class="text-right">
<img src="/20220220-002839.jpg" class="w-55 dib"/>
</div>

- [[万字总结] 一文吃透 Webpack 核心原理](https://mp.weixin.qq.com/s/SbJNbSVzSPSKBe2YStn2Zw)
- [[源码解读] Webpack 插件架构深度讲解](https://mp.weixin.qq.com/s/tXkGx6Ckt9ucT2o8tNM-8w)
- [有点难的知识点：Dependency Graph 深度解析](https://mp.weixin.qq.com/s/kr73Epnn6wAx9DH7KRVUaA)
- [有点难的知识点： Webpack Chunk 分包规则详解](https://mp.weixin.qq.com/s/dFrRY_ntUwmIOXzs8TYcFQ)
- [Webpack 原理系列六： 彻底理解 Webpack 运行时](https://mp.weixin.qq.com/s/nkBvbwpzeb0fzG02HXta8A)
- [Webpack 原理系列七：如何编写loader](https://mp.weixin.qq.com/s/TPWcB4MfVrTgFtVxsShNFA)
- [如何阅读源码 —— 以 Vetur 为例](https://mp.weixin.qq.com/s/wD4ERrDIPLweLvNalC8h4A)
- [Webpack5 核心原理与应用实践](https://juejin.cn/book/7115598540721618944)
- ...

</div>