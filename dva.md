##### 一.环境搭建创建应用

  node.js安装，版本要求6.5+ 

 dva-cli(脚手架安装）

```
$ npm i dva-cli -g //dva-cli安装
$ dva -v //查看安装版本
0.7.0
```

​	创建应用

```
$ dva new user-dashboard //创建文件夹user-dashboard
$ cd user-dashboard //进入文件
```

##### 二.依赖安装

```
$ npm i antd --save //antd
$ npm i babel-plugin-import --save-dev //用于按需引入 antd 的 JavaScript 和 CSS，这样打包出来的文件不至于太大
```

对antd进行配置,修改.roadhogrc，在"extraBabelPlugins"里加上：

```
["import", { "libraryName": "antd", "style": "css" }]
```

##### 三.配置代理

修改.roadhogrc，加上"proxy"配置：

```
 "proxy": {
    "/erpQposRest": {
        "target": "http://v2.qpos.testin.qtoolsbaby.cn:81",
        "secure": false,
        "changeOrigin": true
      }
    },
```

此时启动应用npm start访问 [http://localhost:8000/api/users](https://www.gitbook.com/book/lcgyh/qpos/edit#) 可以访问到 [http://jsonplaceholder.typicode.com/users](https://www.gitbook.com/book/lcgyh/qpos/edit#)

##### 四.dva常用命令

```
npm start //项目启动
npm run build //项目打包
$ dva g route users //生成路由
$ dva g model users //生成数据模型
$ dva g component Users/Users //生成component
```

注意事项：

一开始用命令生成的都是js文件，不是jsx文件，我们不要擅自手动改变成jsx文件，因为会影响到命令的执行，会报错，所以我们还是要用js文件，到项目不用在生成路由的阶段，为了编辑器方便查看，我们可以手动去改动成jsx文件。