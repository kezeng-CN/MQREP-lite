#zIM-lite
轻量级即时通信（Instant Messenger）软件

#模块划分
- 注册服务器(Register Servers)
- 邮件服务器(Mail Servers)
- 消息路由服务器(Router Servers)
- 状态服务器(Presence Servers)
- 管理客户端(Management Client)
- 客户端(Client)

##注册服务器
1. 负责用户的注册，完成注册数据的生成
2. 提供用户注册信息修改

##邮件服务器
1. 调用MTA（Mail Transfer Agent）用户激活邮件发送

##消息路由服务器
1. 维护Presence Server的IP和Port
2. 记录Presence Server中的用户名，提供客户端和Presence Server查询某个用户位于哪个Presence Server中
3. 结合数据库服务器，持久化上述数据
4. 在Presence Server之间转发消息

##状态服务器
1. 记录用户信息
2. 执行主要业务逻辑
3. 存放主要数据
4. 内存中维护用户相关信息——用户注册信息、用户好友信息
5. 离线消息的存储、发送（文件系统中）
6. 客户端之间的消息转发——添加好友通知、发送文件请求

##管理客户端
1. 监控所有服务器状态（实时但非连续）

##客户端
1. 