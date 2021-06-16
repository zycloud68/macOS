### 1. 通过brew安装mysql
```
brew install mysql (默认安装mysql的最新版)
// 安装mysql5.7版本
brew install mysql@5.7 
```
### 2. 更改配置
```
运行 sudo mysql.server start 
运行 mysql_secure_installation
运行 brew service start mysql 可以后台启动mysql
运行 mysql.server start 前台启动mysql(关闭控制台，服务停止)
```
```
 // 出现一下错误，证明mysql没有启动
 > mysql_secure_installation
Securing the MySQL server deployment.
Enter password for user root:
Error: Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)
```
### 4. 修改密码
```
 > sudo mysql_secure_installation
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No: y

There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file
// 这里提示选一个密码强度等级
Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 1
Please set the password for root here.
// 然后按照所选的密码强度要求设定密码
New password:

Re-enter new password:

Estimated strength of the password: 50
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
 ... Failed! Error: Your password does not satisfy the current policy requirements

New password:

Re-enter new password:

Estimated strength of the password: 100
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.
// 这里删除默认无密码用户
Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.


Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.
// 禁止远程root登录，我选的是不禁止。因为我的mac上的数据库不会放到公网上，也不会存什么敏感数据
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : no

 ... skipping.
By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.

// 这里删除默认自带的test数据库
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
 - Dropping test database...
Success.

 - Removing privileges on test database...
Success.

Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.
All done!
```
### 5.连接数据库mysql
```
> mysql -u root -p
> 输入密码：
```
