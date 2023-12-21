<p align="center">
  <a href="https://github.com/moon-studio/vite-vue-bpmn-process">
   <img alt="logo" src="./public/icon-process.png" />
  </a>
</p>

<h1 align="center">
    Vite Vue Bpmn Process Editor
</h1>

<p align="center">
    <a href="https://github.com/moon-studio/vite-vue-bpmn-process/blob/main/README.en.md">English</a> | 中文
</p>

<p align="center">
<img alt="GitHub stars" src="https://img.shields.io/github/stars/moon-studio/vite-vue-bpmn-process?style=flat&logo=github" />
<img alt="GitHub stars" src="https://img.shields.io/github/forks/moon-studio/vite-vue-bpmn-process?style=flat&logo=github" />
</p>

<p align="center">
<img src="https://img.shields.io/badge/Vue-3.X-brightgreen" alt="" />
<img src="https://img.shields.io/badge/Pinia-2.X-brightgreen" alt="" />
<img src="https://img.shields.io/badge/TypeScript-4.5.4-brightgreen" alt="" />
<img src="https://img.shields.io/badge/Vite-2.9-brightgreen" alt="" />
<img src="https://img.shields.io/badge/NaiveUI-2.28-orange" alt="" />
<img src="https://img.shields.io/badge/Bpmn.js-9.2.2-orange" alt="" />
</p>

> 掘金2023年度人气创作者打榜中，快来帮我打榜吧～ https://activity.juejin.cn/rank/2023/writer/747323639208391?utm_campaign=annual_2023&utm_medium=self_web_share&utm_source=MiyueFE

## 项目简介

Vite Vue Bpmn流程编辑器，基于[Bpmn.js](https://github.com/bpmn-io/bpmn-js)， [Vite](https://vitejs.dev)， [Vue.js 3.x](https://vuejs.org/)。

实现了 Bpmn.js 和 Diagram.js 的 typescript 类型声明，typescript 可以用来在编辑器中编写代码。

React 项目也可以参考自定义插件和属性更新方式。

> 码云：https://gitee.com/MiyueSC/vite-vue-bpmn-process

> 🚀Tips: diagram-js 与 bpmn-js 目前均已支持 Typescript。
> 


-----

> 2023年10月1日 更新
>
> 由于该项目目前依然存在一些未实现的功能和 Bug，但是修复起来比较麻烦，所以暂时停止维护。
>
> 目前已经新增了一个 **闭源** 的 Vue 3 + typescript 的项目，基本解决了所有已知 bug，并且增加了一些比较实用的功能。
>
> 已有功能：
>
> 1. 自适应网格背景（支持颜色、网格大小等设置）
> 2. 元素大小设置（初始化时可配置函数等）
> 3. 多元素组合创建
> 4. 自定义元素渲染（初始化时接收自定义元素渲染方法）
> 5. 自定义Palette
> 6. 工具栏
> 7. 兼容 camunda/activiti/flowable 部分属性配置的属性面板
> 8. 垂直泳道（有一点小问题）
> 9. 任务类节点外置label
> 10. 自动布局（无法识别泳道和子流程）
> 11. 美化 ContextPad
> 12. 扩展的自定义元素与属性
>
> 有需要的同学可以联系通过微信公众号联系我。
>
> 预览地址：[Vercel](https://vue-bpmn-process-designer.vercel.app/)、[GitHub Page](https://miyuesc.github.io/bpmn-designer/)

## 友情赞助

生活不易，猪猪叹气。如果对您有帮助，您可以请我喝杯咖啡。十分感谢 (毕竟这个项目还是写了几个月， typescript 部分实在是太难写了)~ ~ ~ ~

<div align="left">
<img alt="微信" src="public/wechat.jpg" width="240" style="display: inline-block"/>
<img alt="支付宝" src="public/alipay.png" width="240" style="display: inline-block"/>
</div>

> 付费咨询联系微信：
> 
> <img alt="wechat.png" src="public/wechat.png" width="200"/>
> 
> 也可关注公众号：MiyueFE 的前端圈
>
> <img alt="wechat.png" src="public/qrcode.jpg" width="200"/>

## 结构目录

```
|-- public
|-- src
|   |-- additional-functions                       扩展的事件函数方法，包括右键事件等
|   |-- additional-modules                         bpmn.js 自定义模块（扩展与重写）
|       |-- AutoPlace
|       |-- ContextPad
|       |-- Lint
|       |-- Palette
|       |-- PopupMenu
|       |-- Renderer
|       |-- Rules
|       |-- Translate
|   |-- bo-utils                                   businessObject 相关属性处理函数
|   |-- components                                 组件 与 bpmn.js 自定义模块
|       |-- common                                 公共组件
|       |-- Designer                               流程设计器
|       |-- Palette                                重写的 bpmn.js 的 Palette 组件
|       |-- Panel                                  重写的 bpmn.js 的 Panel 组件
|       |-- Setting                                项目配置表单组件
|       |-- Toolbar                                编辑器工具栏组件
|   |-- bpmn-icons                                 bpmn 对应的图标文件 svg
|   |-- config                                     项目配置文件
|   |-- moddle-extensions                          bpmn.js 扩展解析文件
|       |-- activiti.json                          
|       |-- bpmn.json                              bpmn 基础元素和属性配置
|       |-- camunda.json                           
|       |-- flowable.json                          
|       |-- miyue.json                             自定义扩展配置
|       |-- zeebe.json                             zeebe 表单配置
|   |-- store
|       |-- editor
|       |-- modeler
|   |-- styles
|       |-- camunda-penal.scss                     camunda 官方侧边栏样式
|       |-- context-pad.scss                       bpmn.js 上下文菜单样式（扩展部分）
|       |-- designer.scss                          流程设计器样式
|       |-- index.scss                             项目样式统一入口
|       |-- palette.scss                           bpmn.js 的 Palette 组件样式（扩展部分）
|       |-- panel.scss                             bpmn.js 的 Panel 组件样式（重写panel）
|       |-- setting.scss                           项目配置表单样式
|       |-- toolbar.scss                           编辑器工具栏样式
|   |-- utils
|       |-- EmptyXML.ts                            生成空的 XML 文件
|       |-- EventEmitter.ts                        事件发布订阅器
|       |-- files.ts                               文件相关操作
|       |-- index.ts                               常用工具函数
|       |-- Logger.ts                              控制台日志输出美化
|       |-- storage.ts                             本地存储操作
|       |-- tools.ts                               常用工具函数
|       |-- uuid.ts                                uuid 生成器
|   |-- App.vue
|   |-- main.ts
|   |-- env.d.ts
|-- types
|   |-- bpmn-moddle
|   |-- declares
|       |-- bpmn.d.ts                              bpmn.js 的类型声明文件
|       |-- bpmn-js-bpmnlint.d.ts                  bpmn.js lint 模块
|       |-- bpmn-js-token-simulation.d.ts          bpmn.js 流转模拟模块
|       |-- bpmn-moddle.d.ts                       bpmn.js 的 moddle 类型声明文件
|       |-- camunda-bpmn-moddle.d.ts               camunda 官方 moddle 类型声明文件
|       |-- diagram.d.ts                           diagram.js 的类型声明文件
|       |-- diagram-js-direct-editing.d.ts         diagram.js 的双击编辑类型声明文件
|       |-- didi.d.ts                              [Nikku - didi](https://github.com/nikku/didi/blob/master/lib/index.d.ts)
|       |-- moddle.d.ts                            moddle 的类型声明文件
|       |-- object-refs.d.ts                       
|   |-- editor
|-- LICENSE
|-- README.md
|-- tsconfig.json
|-- package.json
|-- vite.config.js
```

> Activiti moddle json: https://github.com/Activiti/activiti-modeling-app/blob/master/projects/process-editor/src/services/activiti.json

## 当前功能

### 1. 工具栏

- [x] 导入文件
- [x] 导出文件（xml, bpmn, svg）
- [x] 预览文件字符串（xml, json）
- [x] 元素对其（垂直上中下、水平左中右）
- [x] 缩放
- [x] 撤销恢复与重做
- [x] 扩展功能（流程模拟，小地图，快捷键提示，bpmn 事件查询）

### 2. 编辑器

- [x] 自定义流程id与名称
- [x] 可选流程引擎（camunda，activiti，flowable）
- [x] 动态背景设置
- [x] 自定义 PaletteProvider
- [x] 自定义 Renderer
- [x] 自定义 ContentPadProvider
- [x] 自定义 Rules
- [x] 自定义 ElementFactory
- [x] 扩展右键菜单
- [ ] 自定义 Overlays
- [ ] 扩展 Tooltip
- [ ] 部分元素高亮

### 3. 属性面板

- [x] 基础信息（id, name, version, executable ...）
- [x] 附件文档（documentation）
- [x] 执行作业
- [x] 异步配置
- [x] 流程启动项
- [x] 扩展属性
- [x] 执行监听器
- [x] 流转条件
- [ ] 任务监听器
- [ ] 任务多实例（会签、或签）

## 界面预览

![img.png](docs/img.png)

![img_1.png](docs/img_1.png)

![img_2.png](docs/img_2.png)

![img_3.png](docs/img_3.png)

![img_4.png](docs/img_4.png)

![img_5.png](docs/img_5.png)

![img_6.png](docs/img_6.png)


## 其他项目

1. [diagram-js-grid-bg](https://github.com/miyuesc/diagram-js-grid-bg)：基于 diagram-js-grid 的 SVG 网格背景，可用于diagram-js的相关项目，例如 bpmn-js、dmn-js 等
2. [bpmn-js-external-label-modeling](https://github.com/miyuesc/bpmn-js-external-label-modeling)：一个用来将 Label 标签渲染在节点外部的bpmn-js插件。

## Licence

This project is licensed under the Apache License 2.0 .
