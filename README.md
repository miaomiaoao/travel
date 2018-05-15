# vue-travel

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

当一个文件以vue结尾时,叫做单文件组件

// 路由就是根据网址的不同,返回不同的内容给用户(router其实是router: router 在es6中, 当键和值相同时可以省略)

// @指src这个目录

在vue中 页面跳转使用标签<router-link to="/list"></router-link>

单页应用优点：页面切换快 缺点：首屏时间缓慢 seo差(单页应用在google和百度这种搜索引擎排名比较差)
页面跳转 --> js渲染(解约了很多http请求js)


新建页面的步骤
1.在meta的标签里面添加
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0, maximum-scale=1.0,
    user-scalable=no">
2.引入reset.css样式,因为在不同手机或者浏览器中,默认的样式都是不同的
3.引入border.css 移动端有1像素边框问题
4.移动端有一个300ms点击延迟,在移动端开发中在某些机型和某些浏览器上
当你使用click事件时click事件会延迟300ms执行,可以引入fast-click库
运行 npm install fastclick --save 
5.在我们移动端开发中会用到iconfont
6.移动端布局 一般会采用rem的
7.设计稿宽度750px 这是一个按照iphone6 做的2倍设计图
8.在样式里面引入其他css文件,import前面需要加@
9.引入样式写路径的时候@代表根目录为src,需要在@前面加~
10.将某个路径用符号代替,找到webpack.base.config.js里面resolve下面有一个alias属性(需要重启下服务器)