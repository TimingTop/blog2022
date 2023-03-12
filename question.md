1. 简历提到的   
(1) css flex 布局 把一堆 div 放一行居中显示  
     .box {    
         display: flex;flex-direction:   
         row;justify-content: center;  
     }  

(2) http 跟 websocket 的异同

(3) websocket 从 http upgrade 成功后，返回什么状态码
    ans: 101 

(4) websocket 理论 payload 长度，
     ans: 8 byte    https://datatracker.ietf.org/doc/html/rfc6455#section-5.2
          
2. js
(1) javascript 深度 clone

(2) 做一个简单的功能，但是要引入一个 几M 的 js 包，要提高性能，你会怎么做
    ans: 把大型 js 包按需引入 module， 类似 jdk9 的module 功能

(3) 一个页面 先按 a是先于 b 运行，由于网络问题，b 的结果 先返回了， 怎么解决
    ans: 1. a 返回 promise ，然后链式 then b
         2. 队列实现订阅，把fun全压倒队列中，
         3. generator yield , 内部调用 next(),触发 下一个func ,类似  2
         4. 最简单：  async / await   

3. React
(1) 父子组件之间是怎样通信的
    ans:        props , callback
(2) 跨级组件之间是怎么通信的
    ans:        context + provider ,   callback
(3) 同级组件之间是怎样通信的
    ans:        外部存储空间， 子 -> 父 -> 兄
(4) webpack 的用途, 常见的 loader ， plugin
    ans:  style-loader, css-loader, sass-loader, babel-loader, ts-loader, html-loader, 
          file-loader, url-loader, eslint-loader,
          HotModuleReplacementPlugin, html-webpack-plugin, extract-text-webpack-plugin,
          mini-css-extract-plugin, uglifyJsPlugin, compression-webpack-plugin,
          copy-webpack-plugin

4. 前端性能
(1-1) 动态web页面最耗性能的操作是？
    ans:         重新渲染
(1-2) 页面有一个1万项的动态菜单栏，数据是后台获取的，正常使用过程中会定期更新，你会怎么做
    ans:        old new data 进行比较，找出变化项再更新
(1-3) 设计一个找变化项的算法 
    ans:     react的 diff 算法原理， 3层，1=tree，2=component， 3=element

(2) 前端如何优化
   ans: 1-  加载时优化
           * 减少http请求
           * 服务器渲染
           * CDN
           * css写在 header， js 写在 底部
           * 利用 html 的缓存功能， expire=XXXX
           * 按需加载代码， 页面切换时才下载需要的js （webpack）
           * 用 矢量图
           * 图片： 延迟加载，降低质量，css3 画，合并小图标

        2-  运行时优化 
           * 减少重绘重排 ： 动态变化时用预设好的 css的class，不直接写 style 代码； 
                         对 dom 操作时，在内存生产好，整体带回文档中
                          
           * 时间委托
           * flexbox 排版