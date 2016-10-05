#vue-chat

##功能描述：
	实现一个简单的网页聊天功能，能登录、加好友、和好友即时聊天
	
##编程环境:

运用框架：

* express
* sqlite3
* vue

运用编辑器：webstorm

##功能设计：

###API

1. `/login`
	
	登录

	*	POST：

		参数：username && password
	
		返回：
		
		```
	res.status(200).send('Ok');
	res.status(401).send('please input right username or password');
	
		```
	
2. `/friend`

	获取好友列表:
	
	*	GET：
	
		参数:用户id
	
		```
			req.session.id	
		
		```
	
	
		返回：用户好友信息

		```
		[
		 {
			"name":"xxxx",
			"portrait":"xxxx"
		 },
		 {
		 	"name":"xxxx",
			"portrait":"xxxx"
		 }
		]
		```
		
	添加好友：
	
	*	POST：
	
		参数：用户id、好友id
		
		```
		{
			"userid":1,
			"to_userid":2
		}
		```
	
		返回：添加好友信息,json格式
		
		```
		{
			"name":"xxxxx",
			"portrait":"xxxx"
		}
		```
	
3. `/message/:id`

	获取消息列表：
	
	* GET：
	
		参数：用户id、好友id
		
		```
			to_userid:req.params.id
		```
	
		返回：聊天信息,json格式
		
		```
		{
			"message":"xxxxx"
		}
		```
		
	发送消息:
	
	*	POST：
	
		参数：用户id、好友id
		
		```
			to_userid:req.params.id
		```
		
		返回：用户发送的信息。
			
		```
		{
			"message":"xxxxx"
		}
		```
4.`/getUser`

	获得用户信息

	GET:
	
	获取用户信息：
	
	```
		{
			"name":"xxxxxx",
			"portrait":"xxxxxx"
		}
	```

###页面路由

1.`/login`

	登录页面
	
2.`/chat`

	聊天界面

###数据库:

用户表：

```
create table users(
	id INTEGER PRIMARY KEY,
	username VARCHAR(255) NOT NULL,
	password VARCHAR(255) NOT NULL,
	name VARCHAR(10) NOT NULL,
	portrait VARCHAR(255) NOT NULL
)
```
用户好友表：

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