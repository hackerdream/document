#vue-chat

##功能描述：
	实现一个简单的网页聊天功能，能登录、加好友、和好友即时聊天
	
##编程环境:

运用语言：

* express
* sqlite3
* vue

运用编辑器：webstorm

##功能设计：

###API

>路由

	1. 登录

		参数：登录用户名和密码
		返回：登录用户名和密码
		
	2.	获取好友

		参数：用户id
		返回：用户id的好友信息；
	
	3. 加好友
	
		参数：好友id
		返回：好友id对应的用户信息
		
	4. 渲染消息

		参数：好友id
		返回：好友id与用户id对应的消息
		
>页面：
	
	1. 登录
		
		登录聊天页面
		
	2. 聊天

		渲染聊天页面
		
###数据库:

用户列表：

```
create table users(
	id INTEGER PRIMARY KEY,
	username VARCHAR(255) NOT NULL,
	password VARCHAR(255) NOT NULL,
	portrait VARCHAR(255) NOT NULL
)
```
用户好友列表：

```
 CREATE TABLE user_friend(
	id INTEGER PRIMARY KEY,
	from_userid INTEGER,
	to_userid INTEGER
)
```

聊天信息列表:

```
　CREATE TABLE user_message(
    id INTEGER PRIMARY KEY,
    from_userid INTEGER,
    to_userid INTEGER,
    message VARCHAR(255) NOT NULL,
    time DATETIME NOT NULL
)
```

###前端界面

	1. 登录界面

	2. 聊天界面

	
注：聊天界面由四部分组成：用户信息、好友列表、聊天记录、消息输入框