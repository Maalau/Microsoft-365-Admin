# Microsoft-365-Admin
 
![https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square](https://img.shields.io/badge/license-MIT-blue.svg?longCache=true&style=flat-square)
![https://img.shields.io/badge/springboot-2.0.6-orange.svg?style=flat-square](https://img.shields.io/badge/springboot-2.1.3-yellow.svg?longCache=true&style=popout-square)

此项目是一个基于API的 Microsoft 365 管理平台, 支持订阅查询，用户管理（查询，新增，删除，分配许可证等），支持批量创建用户，批量删除用户. 支持多账户管理.

后端基于SpringBoot，使用 msal4j 和 microsoft-graph sdk 开发完成

前端？**嗯，能力不足，瞎写的，不要在意代码**


## 系统功能

- 总览：订阅数，许可证数，可用许可证数，用户数，允许登陆用户数，禁止登陆用户数等信息展示
- 许可查询：查询每个订阅的许可证信息
- 用户管理：查询，新增，删除，分配许可证等
- 多账户切换

**注意：出现执行新增/删除账户，启用禁用账户，授权账户等操作后，查询结果不变，请右上角点击刷新缓存，或列表中搜索该用户**

原因：调用微软API比较耗时，第一次查询时将需要的数据拉取到本地缓存（暂无自定义缓存失效功能，默认用户1天，域名1天，订阅30天）。

具体功能查看关于界面【操作教程】

## 运行

下载最新版本的额jar包，然后在同目录新建config目录，下载 [application-dev.yml](https://github.com/6mb/Microsoft-365-Admin/blob/master/src/main/resources/config/application-dev.yml)文件放到该目录。

按照格式修改配置文件

java -jar microsoft-0.0.1-SNAPSHOT.jar 启动，端口：8099

### 注意：如果前端文件单独部署（不建议部署到公网，没有登陆功能），请并修改config.js中的请求地址。


## 界面

![image](https://github.com/6mb/Microsoft-365-Admin/blob/master/.github/首页.png)

![image](https://github.com/6mb/Microsoft-365-Admin/blob/master/.github/订阅管理.png)

![image](https://github.com/6mb/Microsoft-365-Admin/blob/master/.github/用户管理.png)

![image](https://github.com/6mb/Microsoft-365-Admin/blob/master/.github/关于.png)

## API接口

[接口文档](https://github.com/6mb/Microsoft-365-Admin/blob/master/Microsoft%20365%20Admin.md)

- Microsoft 365 首页
    - 首页展示
    - 刷新缓存
- Microsoft 365 订阅管理
    - 许可统计
    - 许可证列表查询
- Microsoft 365 用户管理
    - 查询用户统计
    - 查询用户信息列表
    - 查询用户信息详情
    - 查询绑定域名
    - 添加账号
    - 删除账户
    - 添加订阅
    - 取消订阅
    - 启用账户
    - 禁用账户
    - 批量创建用户信息
## Postman 接口

 [点击下载](https://raw.githubusercontent.com/6mb/Microsoft-365-Admin/master/.github/Microsoft%20365%20Admin.postman_collection.json)

请自行设置 .evn  {host} 和 {port}

![image](https://github.com/6mb/Microsoft-365-Admin/blob/master/.github/接口.png)
