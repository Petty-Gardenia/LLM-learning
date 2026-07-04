尚硅谷大模型技术之Python连接外部数据源

（作者：尚硅谷研究院）

版本：V1.0

# 1 **MySQL安装**

![](images/5e383d1d45b7de4b9fa9143e4e9ea41713e055a9d72ac00614059c40393f341c.jpg)

# 2 **Redis 安装**

![](images/5e383d1d45b7de4b9fa9143e4e9ea41713e055a9d72ac00614059c40393f341c.jpg)

# 3 **JDK安装**

![](images/5e383d1d45b7de4b9fa9143e4e9ea41713e055a9d72ac00614059c40393f341c.jpg)

# 4 **Hive安装**

![](images/5e383d1d45b7de4b9fa9143e4e9ea41713e055a9d72ac00614059c40393f341c.jpg)

# 5 **Python连接MySQL代码**

## 5.1 **安装依赖包**

conda install pymysql

## 5.2 **代码**

import pymysql

try:

\# 建立数据库连接

conn = pymysql.connect(

host='hadoop102',

user='root',

password='123456',

database='gmall0620',

charset='utf8mb4',

cursorclass=pymysql.cursors.DictCursor

)

print("连接成功！")

\# 创建游标对象

mycursor = conn.cursor()

\# 执行 SQL 查询

mycursor.execute("SELECT \* FROM base\_dic")

\# 获取查询结果

results = mycursor.fetchall()

\# 遍历结果并打印

for row in results:

print(row)

\# 关闭游标和数据库连接

mycursor.close()

conn.close()

except pymysql.Error as e:

print(f"连接失败: {e}")

# 6 **Python连接Redis代码**

## 6.1 **安装依赖包**

conda install redis

## 6.2 **代码**

import redis

\# 创建 Redis 连接对象

r = redis.Redis(

host='hadoop102',  # Redis 服务器主机名

port=6379,         # Redis 服务器端口号

db=0               # 使用的数据库编号，默认为 0

)

\# 设置一个字符串键值对

r.set('my\_key', 'Hello, Redis!')

\# 从 Redis 中获取字符串值

value = r.get('my\_key')

if value:

print(value.decode('utf-8'))  # 解码为字符串

else:

print('Key not found.')

print("\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~")

\# 设置一个哈希键值对

r.hset('user:1', 'name', 'John')

r.hset('user:1', 'age', 30)

\# 获取单个字段的值

name = r.hget('user:1', 'name')

if name:

print(name.decode('utf-8'))

\# 获取整个哈希的所有字段和值

user\_info = r.hgetall('user:1')

for field, value in user\_info.items():

print(f'{field.decode("utf-8")}: {value.decode("utf-8")}')

print("\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~")

\# 向列表中添加元素

r.rpush('my\_list', 'apple', 'banana', 'cherry')

\# 获取列表中的元素

elements = r.lrange('my\_list', 0, -1)  # 获取列表的所有元素

for element in elements:

print(element.decode('utf-8'))

print("\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~")

\# 向集合中添加元素

r.sadd('my\_set', 'red', 'green', 'blue')

\# 获取集合中的所有元素

members = r.smembers('my\_set')

for member in members:

print(member.decode('utf-8'))

print("\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~")

\# 向有序集合中添加元素

r.zadd('my\_sorted\_set', {'apple': 1, 'banana': 2, 'cherry': 3})

\# 获取有序集合中的元素

elements = r.zrange('my\_sorted\_set', 0, -1)

for element in elements:

print(element.decode('utf-8'))

# 7 **Python连接Hive代码**

## 7.1 **安装依赖包**

conda install pyhive thrift

## 7.2 **代码**

from impala.dbapi import connect

\# 建立与 Hive 的连接

conn = connect(

host='hadoop102',

port=10000,  # Impala 默认端口

database='default',

auth\_mechanism='PLAIN'  # 认证方式，根据实际情况修改

)

\# 创建游标对象

cursor = conn.cursor()

\# 执行 SQL 查询语句

query = "SELECT \* FROM stu LIMIT 10"

cursor.execute(query)

\# 获取查询结果

results = cursor.fetchall()

\# 打印查询结果

for row in results:

print(row)

\# 关闭游标和连接

cursor.close()

conn.close()