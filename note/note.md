#### 2021年06月20日总结记录

###### 1. 开发环境
电脑：mac os

开发软件: vscode/goland

开发辅助软件：docker安装mysql, navacat mysql

###### 2.项目参考
掘金小册：https://juejin.cn/book/6844733730678898702

项目代码：https://github.com/muxih4ck/Go-Web-Application-Template.git

文档讲述: https://github.com/confucianzuoyuan/go-tutorials/tree/master/%E5%9F%BA%E4%BA%8EGo%E8%AF%AD%E8%A8%80%E6%9E%84%E5%BB%BA%E4%BC%81%E4%B8%9A%E7%BA%A7%E7%9A%84RESTful-API%E6%9C%8D%E5%8A%A1

###### 3.项目调试
3.1 测试磁盘相关接口

 curl -XGET http://127.0.0.1:8080/sd/health

 curl -XGET http://127.0.0.1:8080/sd/disk

 curl -XGET http://127.0.0.1:8080/sd/cpu

 curl -XGET http://127.0.0.1:8080/sd/ram

3.2 测试增删改查接口

用户登录获取token
curl -XPOST -H "Content-Type: application/json" http://127.0.0.1:8080/login -d'{"username":"paopao","password":"paopaomodify"}'

创建用户
curl -XPOST -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE2MjQxNjExNzAsImlkIjoyLCJuYmYiOjE2MjQxNjExNzAsInVzZXJuYW1lIjoiYWRtaW4ifQ.am1GCSXmJNYqrlfZIYkmDuA2DDW56KWICTZpe9rbgfM" -H "Content-Type: application/json" http://127.0.0.1:8080/v1/user -d'{"username":"adminadmin","password":"adminadmin"}'

获取用户详细信息
curl -XGET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE2MjQxNjExNzAsImlkIjoyLCJuYmYiOjE2MjQxNjExNzAsInVzZXJuYW1lIjoiYWRtaW4ifQ.am1GCSXmJNYqrlfZIYkmDuA2DDW56KWICTZpe9rbgfM" -H "Content-Type: application/json" http://127.0.0.1:8080/v1/user/admin

更新用户信息
curl -XPUT -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE2MjQxNjExNzAsImlkIjoyLCJuYmYiOjE2MjQxNjExNzAsInVzZXJuYW1lIjoiYWRtaW4ifQ.am1GCSXmJNYqrlfZIYkmDuA2DDW56KWICTZpe9rbgfM"  -H "Content-Type: application/json" http://127.0.0.1:8080/v1/user/6 -d'{"username":"paopao","password":"paopaomodify"}'

删除用户
curl -XDELETE -H  "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE2MjQxNjExNzAsImlkIjoyLCJuYmYiOjE2MjQxNjExNzAsInVzZXJuYW1lIjoiYWRtaW4ifQ.am1GCSXmJNYqrlfZIYkmDuA2DDW56KWICTZpe9rbgfM"  -H "Content-Type: application/json" http://127.0.0.1:8080/v1/user/2

查询用户列表
curl -XGET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE2MjQxNjExNzAsImlkIjoyLCJuYmYiOjE2MjQxNjExNzAsInVzZXJuYW1lIjoiYWRtaW4ifQ.am1GCSXmJNYqrlfZIYkmDuA2DDW56KWICTZpe9rbgfM" -H "Content-Type: application/json" http://127.0.0.1:8080/v1/user -d'{"offset": 0, "limit": 20}'

3.3 测试中间件jwt,trace_id
3.4 makefile学习
3.5 golang代码规范学习[其实这个项目的结构仅作为参考]

3.6 学习收获
* 日志和配置文件系统所使用的第三方库
* gorm增删改查实现
* 自定义错误的规范使用
* gin框架的粗略使用，restful接口的实现流程
* 中间件的使用
* 在接口拉取时使用了go并发id_map实现，该思路较好

###### 4. 项目未学习
* swagger文档生成
* https加密
* 性能测试
