## 功能

-   [1] Element UI
-   [2] 登录/注销
-   [3] 个人中心
-   [4] 修改用户信息
-   [5] 修改密码
-   [6] mysql
-   [7] 图形验证码

## 目录结构介绍

    |-- build                            // webpack配置文件
    |-- config                           // 项目打包路径
    ├--service                           // 服务端
    │   │-- app.js                       // express 入口文件
    │   |-- api                          // 接口
    │       │-- userApi.js               // 接口映射文件
    │   |-- db                           // 数据库
    │       |-- db.js                    // 连接数据库
    │       |-- sqlMap.js                // 数据库映射文件
    |-- src                              // 源码目录
    |   |-- components                   // 组件
    |       |-- common                   // 公共组件
    |           |-- Header.vue           // 公共头部
    |           |-- Home.vue           	 // 公共路由入口
    |           |-- Sidebar.vue          // 公共左边栏
    |		|-- page                   	 // 主要路由页面
    |           |-- Identify.vue         // 图形验证码
    |           |-- Login.vue            // 登录
    |           |-- ModifyPassword.vue   // 修改密码
    |           |-- ModifyUser.vue       // 修改用户
    |           |-- Readme.vue           // 简介
    |           |-- Register.vue         // 注册组件
    |           |-- UserCenter.vue       // 用户中心
    |           |-- Success.vue          // 修改成功
    |   |-- App.vue                      // 页面入口文件
    |   |-- main.js                      // 程序入口文件，加载各种公共组件
    |-- .babelrc                         // ES6语法编译配置
    |-- .editorconfig                    // 代码编写规格
    |-- .gitignore                       // 忽略的文件
    |-- index.html                       // 入口html文件
    |-- package.json                     // 项目及工具的依赖配置文件
    |-- README.md                        // 说明

## 执行步骤

1.开启本地 mysql 服务
创建 user 表 初始化表插入一条数据 脚本如下：
2.cd service
执行：node app 
3.开启后端服务器 另外开一个终端：运行
npm install // 安装项目依赖，等待安装完成之后 
4.浏览器访问 http://localhost:8083

## 服务器部署

// 执行构建命令，生成的 dist 文件夹放在服务器下即可访问
npm run build
