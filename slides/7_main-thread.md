# 🦀 特别是：构建主流程

可以说，理解构建主流程就相当于理解了 70% 的核心原理


<div grid="~ cols-2 gap-4" m="-t-2">

![](/thread-overview.jpeg)

<div>

![](/thread-overview-simple.jpeg)

<v-clicks>

1. **初始化阶段**：修整配置参数，创建 Compiler、Compilation 等基础对象，并初始化插件及若干内置工厂、工具类；
2. **构建阶段**：从 entry 文件开始，**递归** 遍历所有依赖模块，找出依赖的依赖，直至遍历所有项目资源后，构建出完整的 模块依赖关系图；
3. **生成阶段**：将模块组装为一个个 Chunk 对象，之后调用一系列 Template 工厂类翻译 Chunk 代码并 **封装** 为 Asset。

</v-clicks>

</div>

</div>
