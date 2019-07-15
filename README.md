## Web

最近简单学习了servlet，试着做了一个Web系统，可以注册登录，发送邮件找回密码，上传文件，显示上传文件，聊天系统，有点可惜的是没有做成实时系统。

#### online.zip

其中，online.zip包是 HTML + CSS + JAVASCRIPT 的主体部分，包含了index.html, register.html, login.html, password_reset.html 等，位置不定，只需在浏览器中打开就行。

#### servlet.zip

Servlet.zip 中的 java 文件在 apache 的目录下（Mac中：/usr/local/apache-tomcat-8.5.42/webapps/ROOT/WEB-INF/classes），还需要在/usr/local/apache-tomcat-8.5.42/webapps/ROOT/WEB-INF/ 下的 web.xml 中添加路径，具体文件已经上传。

#### 其他

其他的解压后放到 apache 根目录下就行(/usr/local/apache-tomcat-8.5.42/webapps/ROOT)

#### 数据库 Mysql

``` sql
-- 使用的数据库 test
use test;

-- 创建表 qixqi_user
create table if not exists `qixqi_user`(
	`id` int(11) not null auto_increment,
  `username` varchar(100) not null unique default '',
  `email` varchar(100) not null unique default '',
  `password` varchar(100) not null default '',
  `register_time` datetime not null,
  `last_login_time` datetime not null,
  `iconID` int(11) not null default '',
  primary key(`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 default charset=utf8;

-- servlet 自动创建 fileupload 表

-- 创建 chat 表
create table if not exists `chat`(
    `cid` int(11) not null auto_increment,
    `uid` int(11) not null,
    `username` varchar(255) not null,
    `iconID` int(11) not null default '1',
    `typeID` int(11) not null default '1',      -- 用户发送信息的类型， 1为文字，2为文件
    `message` varchar(255) not null default '',
    `time` datetime not null,
    primary key(`cid`)
) ENGINE=InnoDB auto_increment=1 default charset=utf8;
```





