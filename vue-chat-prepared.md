#vue-chat-prepared

##前端网页：
* 登录界面
	1. 用户名、密码输入框
	2. 登录按钮
* 聊天界面
	1. 头像、名字
	2. 好友列表
	3. 聊天框

* 组件
	1. 登录界面
	2. 头像
	3. 好友列表
	4. 聊天框

##后台：

* 网页设计

`/login`

登录页面

` /chat`

聊天界面

* API

`／login`

登录

`/message`

GET:

获取好友列表和聊天记录

POST：

聊天信息上传，加好友上传

`/addFriend`

加好友

##数据库

* user

```
create table users(
	id INTEGER PRIMARY KEY,
	username VARCHAR(255) NOT NULL,
	password VARCHAR(255) NOT NULL,
	portrait VARCHAR(255) NOT NULL
)

```

* user_friend

```
 CREATE TABLE user_friend(
	id INTEGER PRIMARY KEY,
	from_userid INTEGER,
	to_userid INTEGER
)
```

* user_message

```
　CREATE TABLE user_message(
	id INTEGER PRIMARY KEY,
	from_userid INTEGER,
	to_userid INTEGER,
	message VARCHAR(255) NOT NULL,
	time DATETIME NOT NULL
)
```