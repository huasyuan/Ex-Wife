# 《前妻》Ex-Wife Open Source Project


[![Security Status](https://www.murphysec.com/platform3/v3/badge/1617620594128891904.svg?t=1)](https://www.murphysec.com/accept?code=42e50df760bf2afba33cd650ea108949&type=1&from=2&t=2)
> ## 前言
>
> 开源平台：Github 
>
> 项目开源协议：MIT
>
> 项目主语言：PHP
>
> 项目运行环境：Apache or Nginx , MySQL and  PHP .
>
> 介绍语言：简体中文  English
>
> 难易程度：※
>
> 建议：先去学好了基础的PHP语法和HTML CSS相关知识再来。不然你会很恼火的。





# 零，预备环节（简体中文）	

#### Windows平台:

#### 安装[小皮面板](https://www.xp.cn/)自带mysql（用户名root 密码1234）有能力的同学可以徒手安装MySQL Nginx

#### [安装navicat](https://search.bilibili.com/all?keyword=Navicat%E5%AE%89%E8%A3%85&from_source=webtop_search&spm_id_from=333.851)(Windows端的Mysql图形化工具)

#### Linux平台：

##### [宝塔面板官方网站](https://bt.cn/new/download.html)

### 这里不会的，去B站搜教程。

# 创建数据库

```SQL
create database text;--创建一个吗，名为text的数据库
use text;--指定用text这个数据库
create table users(name char(10),passwd char(40))--创建名为users的表 char为数据类型
```

# 一，前端部分（注册）

> 代码这么多 不要慌
>
> 如果你的什么都不懂的，可以把style标签内的所有代码删掉
>
> style标签内的代码只是美化页面而已

```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>注册页面</title>
    <meta http-equiv="Content-Type" content="text/html; charset=gb2312" />
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        main{
            text-align: center;
            height: 320px;
            width: 450px;
            position: absolute;
            left: 34%;
            top:23%

        }
        .top-describe{

            font-size:35px;
            display: block;
            text-align: center;
        }
        input{
            display: block;
            width: 99.8%;
            height: 48px;
            font-size: 20px;
            border: 1px solid rgba(0,0,0,0.2);
        }
        button{
            width: 100%;
            height: 48px;
            margin-top: 20px;
            font-size: 30px;
            background-color: #f66f6a;
            border: none;
            color: white;
        }
    </style>
</head>
<body>
<main>
    <form action="index.php" method="post"'>
        <span class="top-describe">用户注册</span>
        <input type="text" name="name" placeholder="请输入用户名" style="margin-top: 20px;">
        <input type="password" name="passwd"placeholder="请输入密码" style="margin-top: 20px;">
        <button name="submit">注册</button>
    </form>
</main>
</body>
</html>
```



# 二，PHP部分（注册）

> 这个PHP代码，写的很不安全，但是初学者练习够了，请发挥你的头脑，让它安全些
>
> 这是低难度版本，高难度的会附在后面
>
> 高难度：※※※
>
> 低难度：※※

```PHP
<?php
    /*取输入框的值*/
    $name=$_POST['name'];
    $passwd=$_POST['passwd'];
	/*向页面输出 PHP获取的用户名 和 密码*/
    echo"用户名：$name<br>";
    echo"密码：$passwd";
    /*连接数据库*/
    $ip=mysqli_connect('192.168.1.10','admin123','admin','text');
    $cmd="insert into text(name ,passwd) values('$name','$passwd');";
    mysqli_query($ip,$cmd);

?>
```



# SQL语句看效果

> 你得先在前端页面注册后，这条语句才会有实质性的效果

```SQL
select * from users;	
```



# 三，前端部分（登录)

```HTML

```



# 四，PHP部分（登录比对）

```PHP

```



