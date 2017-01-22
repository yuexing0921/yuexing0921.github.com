---
title: npm常用命令
date: 2017-01-22 14:47:14
tags:
---
# npm 常用命令 

#### npm init

#### npm install

##### npm install <packageName> 

##### npm install <packageName> -D or --save-dev 

会在package.json的devDependencies属性下添加msbuild
运行npm install --production或者注明NODE_ENV变量值为production时，不会自动安装msbuild到node_modules目录中

##### npm install <packageName> -S or --save 

会在package.json的dependencies属性下添加msbuild
运行npm install --production或者注明NODE_ENV变量值为production时，不会自动安装msbuild到node_modules目录中

##### [-S|--save|-D|--save-dev|-O|--save-optional] [-E|--save-exact] [--dry-run]

#### npm update

##### npm update <packageName>

##### npm update <packageName>@<version> 升级指定版本

#### 删除指定包

##### npm uninstall

##### npm remove, rm, r, un, unlink

#### npm config

##### npm config ls 获取基本配置信息

##### npm config ls -l 查看所有配置信息

##### npm config set <config> <config-value> 配置信息

###### npm config set registry http://registry.npm.taobao.org/

###### npm config set proxy http://proxy.com:8081/

##### npm config get <config>  获取配置信息

#### 查看包的信息

##### npm info <packageName>

##### npm show <packageName>

##### npm view <packageName>

##### https://registry.npmjs.org/<packageName>

#### 获得安装路径

##### npm root 查看当前包的安装路径

##### npm root -g  查看全局的包的安装路径

#### 模块发布过程

##### 用户登录 npm adduser 

##### 发布模块 npm publish 

#### 命令详解

##### npm help <packageName>

##### https://npmjs.org/doc/
