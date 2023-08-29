*项目正在持续完善，code和详细描述持续补充中*

# 项目简介

## 概述

项目概述：项目从建立问答社区的角度出发，以关键词为主导设置问题-回答-知识库-智能回答-线下活动报名等模块，涵盖综合多种因素的热榜，集成活动报名、点赞、多级评论、关注、订阅消息推送等功能，利用LLM与知识库自动生成官方回答，并根据内容热度属性设置内容推荐规则。 

- 后端使用SpringBoot+Gateway+Nacos+Feign微服务架构开发，设置分布式session，token单点登录，统一处理异常与返回值。前端采用Vue+ElementUI等常用技术栈开发，结合了富文本编辑器以及markdown等组件。
- 使用Redis实现个性化排序，处理缓存，分布式锁处理线下活动报名并发相关问题。 
- 离线处理doc格式的知识文档，生成知识库与向量数据库，使用向量模型与LLM对提出的问题异步匹配知识库构造上下文prompt借助LLM生成智能回答。
-  使用消息队列异步处理点赞、评论等热度数据，计算文章热度，根据关键词与热度推荐用户浏览内容。 
- 使用MySql数据库、MonogoDB，以及第三方oss对象存储服务，用户个人资料借助web3Storage上传至Filecoin。

## 架构

- #### 总体架构

![](imgs\架构图.png)

- #### **大模型对话架构**

<img src="imgs\知识库生成.png" style="zoom: 67%;" />

<img src="imgs\推理.png" style="zoom: 80%;" />





## 功能展示

- #### **登录页**

  采用手机验证码方式登录，后端返回token保存在cookies中，登录session信息存储在redis中

  <img src="imgs\login.png" style="zoom:33%;" />

  <img src="imgs\login2.png" style="zoom:37%;" />

  

- #### **首页热榜**

  <img src="imgs\hot.png" style="zoom:38%;" />

- #### **问题提问**

  <img src="imgs\question1.png" style="zoom:33%;" />

  <img src="imgs\question2.png" style="zoom:44%;" />

- #### **问题回答**

  <img src="imgs\ans2.png" style="zoom:45%;" />

- #### **问题详情页**

  <img src="imgs\ques3.png" style="zoom: 40%;" />

- #### **回答详情（点赞、评论）**

<img src="imgs\ans3.png" style="zoom: 50%;" />

- #### **大模型智能回答**

  <img src="imgs\ans4.png" style="zoom:33%;" />

- #### **关键词页**

  <img src="imgs\key1.png" style="zoom:33%;" />

  <img src="C:\Users\Gary\Desktop\新建文件夹\imgs\key2.png" style="zoom:44%;" />

- #### **关键词详情浏览页**

  <img src="imgs\key3.png" style="zoom:33%;" />

- #### **活动报名**

  <img src="imgs\activity.png" style="zoom:38%;" />



## 开发者

刘宝印 东北大学

郭春晓 东北大学