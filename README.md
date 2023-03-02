[![ 由Wechaty提供 ](https://img.shields.io/badge/Powered%20By-Wechaty-blue.svg)](https://github.com/wechaty/wechaty)
[![node version](https://img.shields.io/badge/node-%3E%3D16-blue.svg)](http://nodejs.cn/download/)
![](https://img.shields.io/badge/Window-green.svg)

# 智能微秘书-engine版本

## 依赖

node 版本 >16

## 关于puppet-engine 协议

puppet-engine是为了适配市面支持http调用的IM接口而产生的一款puppet，名称来源Wechaty作者@Huan，此puppet作为一个引擎模版，可以引入一个ts文件，来
达到适配多种http IM协议，目前内置的为开源的hook协议 [大恩hook](https://gitee.com/qxvxhook/pc-vx-hook-http-api)

## 优势

* 底层协议开源免费
* 支持发送接收小程序和H5链接
* 不掉线稳定，只要你windows电脑一直开着就可以
* Wechaty所有基础方法均支持，堪比目前的ipadLocal协议

## 项目说明

本项目是基于`puppet-engie`协议的版本，只能部署在windows环境下

## 准备

### 文件下载

环境：只支持windows环境，建议win10 及以上

node: node>= v16

指定微信版本：[WeChatSetup3.6.0.18.exe](https://github.com/leochen-g/puppet-engine/releases/download/lastest/WeChatSetup3.6.0.18.exe)

hook包下载：[Dll文件和注入器](https://github.com/leochen-g/puppet-engine/releases/download/lastest/DaenWxHook.zip)

以上环境都是必须，请勿在交流群或者私聊询问是否可以其他版本或其他系统

### 注册智能微秘书管理账号

1. 注册：[智能微秘书](https://wechat.aibotk.com/#/signup)

2. 初始化配置文件`小助手配置->基础配置`，修改后保存

3. 个人中心获取`APIKEY`和`APISECRET`，后续配置用到

### 注册天行数据账号

由于本项目大部分定时资讯和一些天气接口来自于天行数据，所以需要提前准备好天行数据的账号，同时申请好相关接口的权限

1、注册: [天行数据](https://www.tianapi.com/source/865c0f3bfa)

2、申请接口权限

必选接口

* [天行机器人](https://www.tianapi.com/apiview/47)
* [天气](https://www.tianapi.com/apiview/72)
* [新闻](https://www.tianapi.com/apiview/51)
* [垃圾分类](https://www.tianapi.com/apiview/97)

可选接口（如果想使用相应的功能还是必须申请的），但是如果默认使用了天行机器人，以下功能接口无需申请也可以，机器人会直接返回对应信息

* [土味情话](https://www.tianapi.com/apiview/80)
* [名人名言](https://www.tianapi.com/apiview/92)
* [星座运势](https://www.tianapi.com/apiview/78)
* [姓氏起源](https://www.tianapi.com/apiview/94)
* [顺口溜](https://www.tianapi.com/apiview/54)
* [老黄历](https://www.tianapi.com/apiview/45)
* [神回复](https://www.tianapi.com/apiview/39)
* [歇后语](https://www.tianapi.com/apiview/38)
* [绕口令](https://www.tianapi.com/apiview/37)
* [疫情](https://www.tianapi.com/apiview/169)
* [网络取名](https://www.tianapi.com/apiview/36)

## 开始

## 启动注入器

注意：以下目录请根据自己实际安装位置填写

1、安装上述指定版本微信到电脑中，记住目录，例如 `D:\soft\WeChat`

![](http://image.xkboke.com/picgo/202301131802392.png)

2、把hook包中`HPSocket4C.dll`文件放到`D:\soft\WeChat\[3.6.0.18]`下

![](http://image.xkboke.com/picgo/202301131801446.png)

![](http://image.xkboke.com/picgo/202301131804955.png)

3、启动注入器，填写dll文件路径，一定根据实际路径填写，不要直接复制我的路径

进程参数固定：`callBackUrl=http://localhost:8089/wechat/&port=8055&decryptImg=1`

![](http://image.xkboke.com/picgo/202301131809424.png)

4、点击注入并启动

![](http://image.xkboke.com/picgo/202301131812659.png)

5、启动微信后，直接登录即可

## 微秘书服务运行

#### Step 1: 安装

克隆本项目，并进入项目根目录执行 `npm install`安装项目依赖

#### Step 2: 配置

`src/index.js`代码中配置`APIKEY`和`APISECRET`，端口号可以不改，使用默认就行

#### Step 3: 运行

执行命令`npm run start`即可

#### Step 4: 配置相应功能

在[智能微秘书](https://wechat.aibotk.com)中配置你需要的功能后，给启动的微信发送`更新`关键词即可拉取最新配置（或者你自己设置的更新关键词，初始关键词是`更新`，**
每次修改配置后，请记得一定发送关键词更新配置**

## 体验与交流

扫描下方二维码，添加智能微秘书，体验以上所有功能，发送加群关键词即可进入交流群

![](http://image.xkboke.com/picgo/202301141927005.png)


## 常见问题处理

参见[http://wechat.aibotk.com/docs/question](http://wechat.aibotk.com/docs/question)

## 面板预览

![](./doc/img/index.png)
![](./doc/img/roomasync.png)
![](./doc/img/everyday.png)
![](./doc/img/event.png)
![](./doc/img/material.png)

## 功能预览

![](./doc/img/news.jpeg)

个人定时与群定时任务

![](./doc/img/func.jpeg)

群消息同步

<img src="./doc/img/async.png" width="300">

群合影

<img src="./doc/img/group.jpeg" width="300">



## 免责声明

本软件依据github上开源项目 Wechaty

通过简单的设置UI和交互，运行微信机器人。

请遵守国家法律政策，请勿用于非法犯罪行为！

请合理使用，一切不良行为和后果均与作者无关！