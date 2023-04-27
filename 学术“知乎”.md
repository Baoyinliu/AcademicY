_项目正在持续完善，code和详细描述持续补充中。_
<a name="kU3gE"></a>
## 项目简介
<a name="nKKpD"></a>
### 概述
项目概述：项目从＂学术知乎＂的角度出发，以论文关键词为主导设置问题-回答-专栏等模块，涵盖综合多种因素的热榜与点 赞、多级评论、关注等功能，并为用户提供存储学术资料至web3仓库的服务。

- 前后端分离，后端使用SpringBoot进行微服务架构开发，nacos作为服务注册中心，feign进行服务间调用，gateway统一 api地址，jwt生成token单点登录，并统一处理异常与返回值。 
- 前端采用vue+nodejs等常用技术栈开发，结合了富文本编辑器以及markdown等组件。 
- 使用redis作为缓存工具以及分布式锁、分布式session，并在业务逻辑上处理缓存穿透等问题。 
- 排序服务使用消息队列异步处理点赞、评论等相关热度数据，结合zSet计算热度并排序，联合关键词进行用户Feed。 
- 使用MonogoDB、Mysql数据库，以及第三方oss对象存储服务，用户个人资料借助web3Storage上传至Filecoin。  
<a name="OSJgv"></a>
### 项目架构
![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1682584787177-69a780eb-36fd-4699-ab69-0e992c9867a5.png#averageHue=%23fbfbfb&clientId=u3aa63522-edf0-4&from=paste&height=306&id=u7d9bf9aa&originHeight=883&originWidth=1600&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=122242&status=done&style=none&taskId=u57a8943d-191b-45f6-a546-fe5566d355f&title=&width=554.0606079101562)
<a name="sNEIg"></a>
### 项目截图
<a name="IerbD"></a>
#### 首页推荐
该模块按照用户喜爱的关键词推送“既热又新”的文章(文章=问题+回答)<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539784066-73804e36-1221-4379-8f73-1979880a2be5.png#averageHue=%23f5f4f3&clientId=u900c32ba-08df-4&from=paste&height=305&id=u3e1b9c5e&originHeight=1272&originWidth=1971&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=340385&status=done&style=none&taskId=u5c7f990a-b8bb-46ca-9bb3-9a1272c8e95&title=&width=473.06060791015625)
<a name="sqXJe"></a>
#### 热榜
该模块以用户喜爱的关键词为单位，对每个关键词下的热点文章进行推送<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539830727-a3332f3d-daa6-4ed3-98a5-5aae8fcd52e6.png#averageHue=%23efeeed&clientId=u900c32ba-08df-4&from=paste&height=220&id=u8edeaa17&originHeight=1286&originWidth=1964&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=563601&status=done&style=none&taskId=ud0ffe044-112b-467d-a12c-f751bcf08c3&title=&width=336.06060791015625)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539861552-8699fa7e-5c61-46dd-abb6-a60d839732a7.png#averageHue=%23f0eeed&clientId=u900c32ba-08df-4&from=paste&height=146&id=u12ce970c&originHeight=707&originWidth=1953&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=258474&status=done&style=none&taskId=u6016925b-697b-49ae-a28c-196472c7f7e&title=&width=403.06060791015625)
<a name="NYp8H"></a>
#### 问题详情页
该模块包括问题的标题，问题详情，以及问题的相关关键词，该问题下的回答，提问者信息等。<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540254809-db1431b6-99ce-4495-92c9-9820f98d50dc.png#averageHue=%23f1f0ef&clientId=u900c32ba-08df-4&from=paste&height=138&id=ueae95d84&originHeight=503&originWidth=1316&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=127306&status=done&style=none&taskId=u8b3ba58c-9daa-42b3-8651-1f84eed86c1&title=&width=361.06060791015625)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540069150-e9f4c287-ea6f-4790-b9d9-799fbc3b112e.png#averageHue=%23f7f6f6&clientId=u900c32ba-08df-4&from=paste&height=245&id=dFgqx&originHeight=1223&originWidth=1856&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=299012&status=done&style=none&taskId=u19211067-ec9b-48ae-b8cc-069894a081c&title=&width=372.06060791015625)
<a name="OBrnb"></a>
#### 关键词模块
首先关键词模块可按关键词热度展示热门关键词，并运行用户创建关键词，以及设置自己的关键词。<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539909700-d1b5b079-8a78-4073-9c4a-043ca639f8cf.png#averageHue=%23fbfafa&clientId=u900c32ba-08df-4&from=paste&height=244&id=u0309eea0&originHeight=1184&originWidth=2083&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=262131&status=done&style=none&taskId=u14958e9d-f192-40f1-83a6-0509cae2a90&title=&width=429.06060791015625)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539886705-8f73c902-c7a6-4a09-8d44-61c0cf99cf1b.png#averageHue=%23fdfdfd&clientId=u900c32ba-08df-4&from=paste&height=250&id=u9c94a6f9&originHeight=516&originWidth=549&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=23409&status=done&style=none&taskId=ud171a0dd-cc8f-4321-8eeb-ff95e200935&title=&width=266.1818181818182)
<a name="QlKEU"></a>
#### 关键词详情页
关键词详情页中会具体介绍该关键词的情况，并按关键词下内容的热度，展示相关的热门文章<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539945952-8f8cd8a7-562b-46d4-8132-df54aa2f6985.png#averageHue=%23f8f8f7&clientId=u900c32ba-08df-4&from=paste&height=459&id=imYrD&originHeight=2115&originWidth=1489&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=358110&status=done&style=none&taskId=ue34e165b-2868-4f60-8432-d10ecaf9fcf&title=&width=322.93939208984375)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679539992741-e79ec8c1-aa22-4398-9e11-4806636326b2.png#averageHue=%23f5f3f1&clientId=u900c32ba-08df-4&from=paste&height=467&id=ln6tb&originHeight=2220&originWidth=1254&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=270044&status=done&style=none&taskId=u720f8c19-50f8-43a4-8f8b-7f5dfae6d3a&title=&width=264)
<a name="RcCyv"></a>
#### 提问模块
![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540037576-8d569efe-1d55-428d-b606-bd6bba426a3d.png#averageHue=%23e3e3e3&clientId=u900c32ba-08df-4&from=paste&height=321&id=u46c6658c&originHeight=1301&originWidth=1944&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=108348&status=done&style=none&taskId=uca60a511-ee0e-44fb-938d-88410ac14f2&title=&width=480.06060791015625)
<a name="ryqTa"></a>
#### 回答模块
![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540125415-f75b1582-4e7b-4895-b537-5eb97e78e4bc.png#averageHue=%23faf9f9&clientId=u900c32ba-08df-4&from=paste&height=1716&id=uPprz&originHeight=5138&originWidth=1464&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=1130027&status=done&style=none&taskId=ueddbea59-d755-465f-a7d3-9eaa91e51f8&title=&width=488.81817626953125)
<a name="qq4Z8"></a>
#### 点赞评论关注
![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540193669-dd1de1da-f832-49f4-b6eb-ddf342e4a34c.png#averageHue=%23faebd4&clientId=u900c32ba-08df-4&from=paste&height=48&id=kErcl&originHeight=123&originWidth=134&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=3048&status=done&style=none&taskId=u3ee6fb38-7d5f-4a50-9e3d-559502dc83c&title=&width=51.96969795227051)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540225177-a978caa6-5ba7-490e-b181-d3a21235b071.png#averageHue=%23f4f9ff&clientId=u900c32ba-08df-4&from=paste&height=43&id=fqLjM&originHeight=88&originWidth=129&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=1773&status=done&style=none&taskId=u0fa24816-7b67-4c57-92ad-f9ca9dbc6fb&title=&width=62.54545454545455)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540235479-0c08382a-993d-4d79-8c05-6437c90c0999.png#averageHue=%23fcfce5&clientId=u900c32ba-08df-4&from=paste&height=53&id=pSnlC&originHeight=110&originWidth=213&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=4203&status=done&style=none&taskId=u1e6f3001-7f74-47bf-8d14-ac09f598045&title=&width=103.27272727272727)<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540180771-76aa82b3-a9ab-427e-b5a8-e1098997bcbc.png#averageHue=%23fefdfd&clientId=u900c32ba-08df-4&from=paste&height=302&id=u300a906e&originHeight=1210&originWidth=1184&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=93308&status=done&style=none&taskId=ud2485a14-48db-41f2-8edb-901c7b3ed63&title=&width=295.06060791015625)![image.png](https://cdn.nlark.com/yuque/0/2023/png/26756779/1679540087078-033750af-e3bb-4d2e-86cc-00b9c15b8223.png#averageHue=%23d5d5d5&clientId=u900c32ba-08df-4&from=paste&height=266&id=rWC5a&originHeight=1153&originWidth=1710&originalType=binary&ratio=2.0625&rotation=0&showTitle=false&size=174400&status=done&style=none&taskId=ubfdd2b50-3a22-44e0-a284-453f23c054a&title=&width=394.06060791015625)

