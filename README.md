ThinkingAboutFED
===============

## 目的

 - 你需要了解的是思想，从项目搭建->开发->测试->项目发布
 - 各种工具的使用，太多了。。工具只是辅助，关键的是思想
 - 你可以不会使用工具，但是你要知道为什么工具要这样来做
 - 不同类型的页面、不同类型的终端，相乘后爆炸式的不同情况，但其实前端本质上的东西还是html，css和js
 - 接下来，就是如何更有效率的开发，和保证代码的质量

## 如何更有效率的开发

 - 写的快：代码目录划分、框架、重用dry、封装
 - 看的快：本地模拟环境调试，快速发布线上环境
 - 多人合作：github、模块化、耦合低

## 保证代码的质量

 - 单元测试！
 - 各种测试！

## 工具的熟练使用

yeoman等，搭建就有很多，fis、spm，搭建工作是第一步，可以搭建一个项目，搭建一个模块等等。
每个工具都有各自的特点，选择哪个？
思想，了解为什么要这样规划目录

开发，选择什么框架，框架多入牛毛，掌握框架背后的思想，你其实也能写出你的框架。

CSS，sass/scss/stylus，这样使用css的好处
写一个自己的CSS库又不一样，命名规范，如何层叠，粒度如何划分，bootstrap,alice

## FIS解决了什么问题

## 静态资源处理策略

 - ```<script src='path'></script>``` 引用的脚本默认会在打包后移动到body底部
 - ```<script data-position='head'></script>``` 引用或声明的脚本会移动到head底部
 - ```<script|link data-single='true'></script|link>``` 引用或声明的脚本和样式不会进行自动打包
 - ```<link rel='stylesheet' href='path'>``` 引用的样式表默认会在打包后移动到head底部
 - ```<link rel='stylesheet' href='path'>``` 引用的样式表默认会在打包后移动到head底部
 - ```<script>console.log('hello world')</script>``` 编写的内嵌脚本将会移动到body底部
 - ```<script|link data-fixed='true'>``` 声明的标签不会被处理
 - ```<style></style>``` 不会进行任何处理

## 用法

    $ npm install -g fis-postpackager-simple
    $ vi path/to/project/fis-conf.js

```javascript
//file : path/to/project/fis-conf.js
fis.config.set('modules.postpackager', 'simple');
//关闭autoCombine可以设置是否将零散资源进行打包
//fis.config.set('settings.postpackager.simple.autoCombine', false);
```

## 配置项

### autoCombine

设置是否自动将零散资源进行打包，默认为 `true`，关闭后仅会替换设置了pack的资源

### fullPackHit

设置是否资源需要全部命中pack设置才会将整个资源包引用

#### fullPackHit.js

默认为 `false`

#### fullPackHit.css

默认为 `false`

## 适应范围

用于简单的Web前端项目自动打包减少页面请求连接数，同时可以通过[pack](https://github.com/fex-team/fis/wiki/%E9%85%8D%E7%BD%AEAPI#pack)设置来对公共资源进行独立打包。

要求使用的页面是完整的HTML页面，即包含head与body标签，支持通过html inline的形式添加的公用head与底栏等。但是不支持母板页形式的页面继承。

## DEMO

https://github.com/hefangshi/fis-quickstart-demo

