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

	*	POST：

		登录

		参数：username 、password

		```
		{
			"username":"xxxx",
			"password":"xxxxxx"
		}
		```
	
		返回：
		
		状态：200，表示登录成功
		
		返回内容：
		
		```
		{
			"message":"Ok"
		}
		```
		
		状态：401，表示登录信息错误，没有权限登录。
		
		返回内容：
		
		```
		{
			"message":"please input right username or password"
		}
		```
	
2. `/friend`
	
	*	GET：

		获取好友列表:
	
		返回：用户好友信息

		```
		[
		 {
		 	"id":1,
			"name":"xxxx",
			"portrait":"xxxx"
		 }
		]
		```
	
	*	POST：

		添加好友：
	
		参数：好友id
		
		```
		{
			"from_userid":1,
			"to_userid":2
		}
		```
	
		返回：添加好友信息,json格式
		
		```
		{
			"id":1,
			"name":"xxxxx",
			"portrait":"xxxx"
		}
		```
	
3. `/message/:id`
	
	* GET：

		获取消息列表:
	
		参数：id
		
		>好友id
	
		返回：聊天信息,json格式
		
		```
		[
		  {
		  	"id":1,
			"from_userid":2,
			"to_userid":1,
			"message":"xxxxx",
			"time":"1996-4-4"
		  }
		]
		  
		```
	
	*	POST：

		发送消息:
	
		参数：id
		
	   >好友id
		
		返回：用户发送的信息。
			
		```
		{
			"from_userid":2,
			"to_userid":1,
			"message":"xxxxx",
			"time":"1996-4-4"
		}
		```
		
4. `/getUser`

  *  GET:

  		获得用户信息:
  	
  		返回：
	
	
		```
		{
			"id":1,
			"name":"xxxxxx",
			"portrait":"xxxxxx"
		}
		```

5. `/searchUser`
	
  *	 GET:

  		搜索用户信息:

  		参数：
  		
  		Query:
  		> name 要搜索的名字

  		返回：
  		
  		```
  		[
  		  {
  			"id":1,
  			"name":"xxxxxx",
  			"portrait":"xxxxxx"
  		  }
  		]
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
 CREATE TABLE user_friends(
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