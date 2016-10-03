# LeatCode修炼日志

## 第一天

### 问题：

Person表

| Column Name | Type |
|-------------|-----------|
| PersonId    | int     |
| FirstName   | varchar |
| LastName    | varchar |

其中PersonId是主键

Address表

| Column Name | Type    |
|-|-|
| AddressId   | int     |
| PersonId    | int     |
| City        | varchar |
| State       | varchar |

其中AddressId是主键

要求写出SQL语句，无论每个人是否含有地址信息，从两张表中选出每个人的下列信息：
```
FirstName, LastName, City, State
```
### 答案
```SQL
Select FirstName,LastName,City,State from Person Left Join Address On Person.PersonId = Address.PersonId
```
### 备注

这一个问题的讨论区里大部分的问题集中于为什么不能用where字句之类的。其实很简单，用where的话就是inner join。inner join表示的是自然连接，本来没有什么问题，但问题中明确要求了不论是否含有地址信息都能够提供相应信息，所以只能使用left join字句，这样才能满足要求。

### 知识点

- [Join的写法](url "http://blog.sina.com.cn/s/blog_73dac6b50101hdql.html")
- [几种Join的差别](url "http://blog.csdn.net/steryzone/article/details/4997060")
