---
title: 用 Weex 构建移动应用
type: guide
order: 4.5
version: 2.1
---

# 用 Weex 构建移动应用

## 今天的移动应用

这里谈一谈 Weex 对移动应用的理解。

### 移动应用需要支撑并行研发

如今移动应用的开发需要并行研发的能力，当一个移动应用发展到一定规模的时候，能否支撑大规模的并行研发就成为了一件非常关键而又重要的事情。否则很容易变成工程瓶颈。

### 移动应用需要动态性

如今移动应用不论从研发节奏、部署的灵活性和时效性、包大小、还是从研发到发布再到反馈的迭代周期上，都和移动互联网的发展速度极不相符。移动应用需要更简单轻量的研发模型，需要摆脱版本部署和分发的笨重过程。

### 移动应用需要开放互联

如今移动应用的内容和信息都是相互孤立的，应用之间的交流变得非常复杂和困难，也缺乏一定的标准和规范化的容器来承载。

## 整体结构设计

我们认为一个具有高并行研发能力、动态化和标准化规范化的移动应用应该由以下几个方面构成：

```
|------|------|------|------| |-----|
| page | page | page | page | | api |
|------|------|------|------| | api |
| page | page | page | page | | api |
|------|------|------|------| | api |
| page | page | page | page | | api |
|---------------------------| | api |
|           router          | | api |
|---------------------------| |-----|
```

* 页面：首先移动应用应该可以被拆解成若干个页面，每个页面相对解耦独立，同时每个页面都有一个 URL 进行唯一标识。
* 路由：这些页面将会通过路由机制有机的串联起来，页面之间的关系是通过路由来进行调度的。常见的移动应用路由包括导航栏、tab 切换等。
* 设备能力：以各种 API 或服务的方式提供出来，供页面自由使用。

这样的话，在构建一个完整的移动应用之前，先确定你的应用有多少页面，每个页面分别是什么 URL，页面之间的关联和跳转逻辑是怎样的，然后梳理整个移动应用需要的所有 API 和服务。

然后通过 Weex 创建不同的页面，并分别进行开发、调试和发布。

**相关链接**

* [页面结构](./page-architecture.html)

如果你已经有一个做好的移动应用，只想用 Weex 开发其中的一部分页面甚至仅仅其中的一两个页面，这对 Weex 来说完全不是问题。Weex 只是一个 SDK，对整体的移动应用架构不会产生任何侵入性。并且完全可以和纯 native 界面或 hybrid 页面共存。

如果需要 WeexSDK 额外的组件、模块或其它功能，可以通过 Weex 的扩展机制进行扩展。这部分工作需要 native 的研发知识，但是随着 Weex 组件和模块的丰富以及业务迭代的深入，这部分成本会承下降和收敛的趋势。

**相关链接**

* [如何扩展 iOS](../../references/advanced/extend-to-ios.html)
* [如何扩展 Android](../../references/advanced/extend-to-android.html)
