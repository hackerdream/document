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

* API

>路由

	1. 登录

		登录账号，进入自己的聊天界面
		
	2. 获取好友

		获取好友列表以及对应的id
		
	3. 获取聊天记录

		获取各自对应的聊天记录，加以渲染到界面上；上传聊天记录到数据库
	
>页面

	1. 登录

		进入登录界面，执行登录操作
		
	2. 聊天

		聊天界面，能够和好友聊天
		
* 数据库

	I	ER图见word
	
* 前端页面

	1. 登录界面

	2. 聊天界面

	
注：聊天界面由四部分组成：用户信息、好友列表、聊天记录、消息输入框