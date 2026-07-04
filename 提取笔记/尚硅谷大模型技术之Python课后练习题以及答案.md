尚硅谷大模型技术之Python课后练习题以及答案

（作者：尚硅谷研究院）

版本：V1.0

# 1 **概述**

1. **介绍计算机的组成**
2. **说说计算机语言的发展简史**
3. **Python是一门什么样的语言，为什么学习Python**
4. **常见的Python的解释器有哪些**
5. **熟悉Python以及PyCharm的安装以及配置**
6. **用不同的方式打印输出“hello atguigu”**

# 2 **快速入门**

- 交互式命令行
- 脚本
- IDE

# 3 **基础知识**

7. **说说注释的作用以及分类和用法**
8. **标识符的命名规则都有哪些**
9. **在程序中定义name、age变量，将你的名字和年龄赋值，并输出到控制台**

name = "你的名字"

age = 你的年龄

print("我的名字是" + name + "，我今年" + str(age) + "岁。")

10. **将十进制数 42 转换为二进制表示**

decimal\_number = 42

binary\_number = bin(decimal\_number)

print(binary\_number)

如果你想要去除 0b 前缀，可以使用切片操作

decimal\_number = 42

binary\_number = bin(decimal\_number)[2:]

print(binary\_number)

以下是将十进制数 42 转换为二进制表示的手动计算方法：

用 42 除以 2，得到商 21 和余数 0。

用 21 除以 2，得到商 10 和余数 1。

用 10 除以 2，得到商 5 和余数 0。

用 5 除以 2，得到商 2 和余数 1。

用 2 除以 2，得到商 1 和余数 0。

用 1 除以 2，得到商 0 和余数 1。

将所有的余数从下往上排列，得到二进制表示 101010。

11. **将二进制数 110110 转换为十进制表示**

binary\_number = "110110"

decimal\_number = int(binary\_number, 2)

print(decimal\_number)

\# 从右到左，每一位上的数字分别是：0，1，1，0，1，1。

\# 对应的位置（从右开始算，从0开始数）分别是：2的0次方，2的1次方，2的2次方，2的3次方，2的4次方，2的5次方。

\# 接下来，将每一位上的数字与其对应的位置相乘，然后将得到的结果相加。

12. **将二进制数 1101 转换为十六进制表示**

binary\_number = "1101"

decimal\_number = int(binary\_number, 2)

hexadecimal\_number = hex(decimal\_number)

print(hexadecimal\_number)

\# 将二进制数从右到左每 4 位一组，不足 4 位的在左边补 0，然后将每组二进制数转换为对应的十六进制数。

\# 二进制 1101 对应的十进制数是 1\*2的0次方 + 0\*2的1次方 + 1\* 2的2次方 + 1\* 2的3次方 = 13。

\# 十进制数13对应的十六进制数是D。

13. **将十六进制数 1A3 转换为二进制表示**

hexadecimal\_number = "1A3"

decimal\_number = int(hexadecimal\_number, 16)

binary\_number = bin(decimal\_number)

print(binary\_number)

\# 将十六进制数的每一位转换为对应的 4 位二进制数。

\# 十六进制数 1 对应的二进制数是 0001。

\# 十六进制数 A（十进制为 10）对应的二进制数是 1010。

\# 十六进制数 3 对应的二进制数是 0011。

\# 所以十六进制数 1A3 对应的二进制数是 000110100011

14. **有十进制数-8，请用八位二进制小数表示的它的原码、反码、补码**

\# 首先，将8转换为二进制表示，得到 00001000。

\# 对于-8的原码，符号位为1，其余位为8的二进制表示，所以-8的原码是10001000

\# 负数的反码，符号位不变，其余位取反。

\# 对于-8的反码是 11110111。

\# 负数的补码，等于反码加1。

\# 对于-8的补码  11111000

15. **简单的加法计算器实现**

**要求：分别让用户输入两个加数，在程序中接收用户的输入并计算结果**

\# 获取用户输入的第一个数

num1 = int(input("请输入第一个数："))

\# 获取用户输入的第二个数

num2 = int(input("请输入第二个数："))

\# 计算两个数的和

result = num1 + num2

\# 输出结果

print(num1, "+", num2, "=", result)

16. **Python常用的运算符都有哪些类型**
17. **接收控制台输入的薪水值，如果高于15000，就投递简历**

# 4 **流程控制语句**

\# 获取老板提供的薪水

salary = int(input("请输入您提供的薪水"))

if salary >= 15000 :

print("薪水不错,考虑进一步沟通")

print("程序执行结束")

18. **从键盘上输入3位正整数，判断是否为水仙花数**

水仙花数:3位正整数等于各个位数字的立方和

\# 获取用户输入的三位正整数

input\_num = int(input("请输入一个三位正整数"))

\# 将输入的三位正整数各个位上的数字取出来 153

a = input\_num % 10 # 个位

b = input\_num // 10 % 10 # 十位

c = input\_num // 100 # 百位

\# 判断是否为水仙花数

if input\_num == a \*\* 3 + b \*\* 3 + c \*\*3 :

print("您输入的数字%d是水仙花数" %input\_num)

print("程序执行结束")

19. **从键盘上输入一个年份，判断是否为闰年**

\# 获取用户在键盘上输入的年份

year = int(input("请输入一个四位的年份"))

\# 判断是否为闰年

if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):

print("您输入的%d是闰年" %year)

print("程序执行结束")

20. **从键盘上获取输入的数字，判断奇偶性，分别输出**

\# 获取用户在键盘上的输入,并且转换为int

num = int(input("请输入一个正整数"))

\# 判断奇偶性

if num % 2 == 0 :

print("%d是偶数" %num)

else :

print("%d是奇数" %num)

print("程序执行结束")

21. **模拟用户登录验证，获取键盘上的输入，如果用户名admin,密码是123，提示登录成功，否则提示登录失败**

#获取用户输入的用户名和密码

print("\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~欢迎来到XXX系统\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\`")

username = input("请输入用户名\n")

password = input("请输入密码\n")

if "admin" == username and "123" == password :

print("恭喜您,登录成功!")

else :

print("登录失败,用户名或者密码错误")

22. **获取键盘上输入的数字，判断整数负数和0**

\# 获取用户在键盘上输入的数字

num = int(input("请输入一个数字"))

\# 判断正负零

if num > 0 :

print("正数")

elif num < 0 :

print("负数")

else :

print("零")

23. **从键盘上获取学生成绩，判断成绩等级**

>= 90 A

[80\~90) B

[70\~80) C

[60\~70) D

<60    E

\# 获取用户在键盘上输入的成绩

score = int(input("请输入您的成绩"))

\# 成绩合法性判断

if score < 0 or score > 100 :

print("输入的成绩不合法")

exit(1) # 退出程序

\# 定义一个变量,表示成绩的等级

grade = ''

if score >=90 :

grade = 'A'

elif score >= 80 :

grade = 'B'

elif score >= 70 :

grade = 'C'

elif score >= 60 :

grade = 'D'

else :

grade = 'E'

print("该成绩对应的等级为%s" %grade)

24. **从键盘上输入一个时间，输出它的下一秒时间**

\# 获取用户在键盘上输入的时间

hour = int(input("请输入小时(0\~23)"))

minute = int(input("请输入分钟(0\~59)"))

second = int(input("请输入秒(0\~59)"))

print("当前时间为:%d:%d:%d" %(hour,minute,second))

#计算下一秒

second += 1

\# 修正时间

if second == 60 :

\# 如果是60秒了,秒置为0,分钟+1

second = 0

minute += 1

\# 如果分钟加1后变为60,分钟置0,小时+1

if minute == 60 :

minute = 0

hour += 1

\# 如果小时加1后变为24了,小时置0

if hour == 24 :

hour = 0

print("当前时间的下一秒为:%d:%d:%d" %(hour,minute,second))

25. **遍历出1\~100之间所有的数,将能被3整除的数打印出来,每行打印5个**

num = 1 # 定义一个循环变量

count = 0  # 计数器变量

while num <= 100 :

\# 判断当前编译出来的数是否能被3整除

if num % 3 == 0 :

\# 如果能被3整除,将这个数打印出来

print(num,end ="\t")

count += 1

\# 判断是否需要换行

if count % 5 == 0 :

print()

num += 1 # 改变循环变量

26. **计算1+2+3+...+100的和**

num = 1  # 循环变量

sum = 0  # 保存累加的和

while num <= 100 :

sum += num

num += 1

print("1\~100累加的和是%d" %sum)

27. **接收用户在键盘上输入的正整数,如果输入-1结束,找出其中输入最大的值**

num = 0  # 保存用户输入的正整数

max\_num = 0  # 用于存储最大值的变量

while num != -1 :

num = int(input("请输入一个正整数"))

if num > max\_num :

max\_num = num

if max\_num > 0 :

print("最大值为%d" %max\_num)

else :

print("您还没有输入正整数")

28. **求出2\~10这些数字中的质数**

质数:在一个大于1的自然数中,如果只能被1和自身整除的数

\# 遍历出2\~10之间的数字

for n in range(2,10):

\# 遍历寻找因子

for x in range(2,n):

if n % x == 0:

print('%d等于%d\*%d' %(n,x,n//x))

break  # 跳出循环

else :

print('%d是一个质数' %n)

29. **打印如下图形的\***

\*

\* \*

\* \* \*

\* \* \* \*

\* \* \* \* \*

\# 方式1 利用字符串和\*配合输出

row = 1

while row <= 5:

print("\*" \* row)

row += 1

print("-" \* 50)

\# 方式2 for循环的嵌套

for r in range(1,6):

for c in range(0,r) :

print("\*",end="")  # 打印不换行

print()

print("-" \* 50)

\# 方式3 while循环的嵌套

row2 = 1

while row2 <= 5:

col = 1

while col <= row2 :

print("\*",end="")

col += 1

print()

row2 += 1

# 5 **容器数据类型**

30. **给定一个列表 numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]，编写一个程序，将列表中所有的偶数元素删除**

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

\# 遍历列表的副本，避免在迭代时修改原列表导致的问题

for num in numbers[:]:

if num % 2 == 0:

numbers.remove(num)

print(numbers)

31. **创建一个空列表 fruits，然后添加 "apple", "banana", "cherry", "date" 四个元素。接着在列表的开始添加 "elderberry"，在 "cherry" 之前添加 "fig"，并将列表的最后一个元素替换为 "grape"。**

fruits = []

fruits.append("apple")

fruits.append("banana")

fruits.append("cherry")

fruits.append("date")

fruits.insert(0, "elderberry")

cherry\_index = fruits.index("cherry")

fruits.insert(cherry\_index, "fig")

fruits[-1] = "grape"

print(fruits)

32. **给定一个列表 prices = [10.5, 20.0, 15.75, 8.2, 12.0]，编写一个程序，将列表中的元素都乘以 1.1（表示增加 10%），并将结果存储在一个新列表 new\_prices 中。**

prices = [10.5, 20.0, 15.75, 8.2, 12.0]

new\_prices = []

for price in prices:

new\_price = round(price \* 1.1,2) #保留2为小数

new\_prices.append(new\_price)

print(new\_prices)

33. **有两个列表 list1 = [1, 2, 3, 4, 5] 和 list2 = [6, 7, 8, 9, 10]，将它们合并为一个新列表 combined\_list，并对 combined\_list 进行降序排序**

list1 = [1, 2, 3, 4, 5]

list2 = [6, 7, 8, 9, 10]

combined\_list = list1 + list2

combined\_list.sort(reverse=True)

print(combined\_list)

34. **给定一个列表 strings = ["hello", "world", "python", "is", "fun"]，编写一个程序，将列表中的元素拼接成一个字符串，元素之间用空格分隔。**

strings = ["hello", "world", "python", "is", "fun"]

sentence = " ".join(strings)

print(sentence)

35. **给定一个字符串 sentence = "Hello, World!"，编写一个程序，将字符串中的所有小写字母转换为大写字母，并输出结果。**

sentence = "Hello, World!"

upper\_sentence = sentence.upper()

print(upper\_sentence)

36. **给定一个字符串 text = "Python is fun and powerful."，统计字符串中字母 n 出现的次数。**

text = "Python is fun and powerful."

count\_n = text.count('n')

print(count\_n)

37. **给定一个字符串 str1 = "apple,banana,cherry,date"，将该字符串按照 , 分隔，存储在一个列表中，并将列表中的元素首字母大写，最后将修改后的列表元素用 - 连接成一个新的字符串。**

str1 = "apple,banana,cherry,date"

str\_list = str1.split(',')

capitalized\_list = []

for s in str\_list:

capitalized\_list.append(s.capitalize())

new\_str = '-'.join(capitalized\_list)

print(new\_str)

38. **给定一个元组 fruits = ("apple", "banana", "cherry", "date", "elderberry")，编写一个程序，找出元组中最长的元素。**

fruits = ("apple", "banana", "cherry", "date", "elderberry")

longest\_fruit = fruits[0]

for fruit in fruits:

if len(fruit) > len(longest\_fruit):

longest\_fruit = fruit

print(longest\_fruit)

39. **给定两个集合 set1 = {1, 2, 3, 4, 5} 和 set2 = {4, 5, 6, 7, 8}，编写一个程序，找出两个集合的交集、并集以及差集。**

set1 = {1, 2, 3, 4, 5}

set2 = {4, 5, 6, 7, 8}

intersection\_set = set1 & set2  # 或者使用 set1.intersection(set2)

union\_set = set1 | set2  # 或者使用 setA.union(setB)

difference\_set = set1 - set2  # 或者使用 setA.difference(setB)

print("交集:",intersection\_set)

print("并集:", union\_set)

print("差集:", difference\_set)

40. **给定一个集合 original\_set = {1, 2, 3, 4, 5}，编写一个程序，向集合中添加元素 6 和 7，并从集合中移除元素 3。**

original\_set = {1, 2, 3, 4, 5}

original\_set.add(6)

original\_set.add(7)

original\_set.remove(3)  # 或者使用 discard 方法，如果元素不存在，discard 不会引发错误

print(original\_set)

41. **给定一个字典 student\_scores = {"Alice": 85, "Bob": 92, "Charlie": 78, "David": 88}，编写一个程序，将每个学生的分数增加 5 分，并将结果存储在一个新的字典 updated\_scores 中。**

student\_scores = {"Alice": 85, "Bob": 92, "Charlie": 78, "David": 88}

updated\_scores = {}

for student, score in student\_scores.items():

updated\_scores[student] = score + 5

print(updated\_scores)

42. **给定一个字典 fruit\_prices = {"apple": 1.2, "banana": 0.5, "cherry": 2.5, "date": 3.0}，编写一个程序，找出价格最高的水果及其价格。**

fruit\_prices = {"apple": 1.2, "banana": 0.5, "cherry": 2.5, "date": 3.0}

max\_price = 0

max\_fruit = None

for fruit, price in fruit\_prices.items():

if price > max\_price:

max\_price = price

max\_fruit = fruit

print(f"The most expensive fruit is {max\_fruit} with a price of {max\_price}.")

# 6 **函数**

43. **说说函数定义都包含哪些要素**
44. **什么是形参和实参**
45. **编写一个函数 multiply\_list，它接收一个列表 numbers 作为参数，将列表中的元素相乘，并返回结果**

def multiply\_list(numbers):

result = 1

for num in numbers:

result \*= num

return result

\# 调用函数

print(multiply\_list([2, 3, 4]))

46. **编写一个函数 is\_prime，它接收一个正整数 n，并判断 n 是否为质数，如果是质数返回 True，否则返回 False。**

def is\_prime(n):

if n <= 1:

return False

if n <= 3:

return True

if n % 2 == 0 or n % 3 == 0:

return False

i = 5

while i \* i <= n:

if n % i == 0 or n % (i + 2) == 0:

return False

i += 6

return True

\# 调用函数

print(is\_prime(7))

print(is\_prime(10))

# 7 **文件操作**

47. **读写文件的流程**
48. **常见的文件操作模式有哪些**
49. **文件拷贝的案例**
50. **理解类和对象的关系**
51. **使用面向对象编程来表示汽车和发动机的关系，以及如何组装一台汽车。**

# 8 **面向对象之类和对象**

\# \_\_init\_\_(self, cylinders, horsepower)：构造函数，接收发动机的气缸数

\# cylinders 和马力 horsepower，并将其存储为实例属性。

\# start(self)：模拟发动机启动，返回启动信息。

\# stop(self)：模拟发动机停止，返回停止信息。

class Engine:

def \_\_init\_\_(self, cylinders, horsepower):

self.cylinders = cylinders

self.horsepower = horsepower

def start(self):

return "Engine is starting..."

def stop(self):

return "Engine is stopping..."

\# \_\_init\_\_(self, make, model, year, engine)：构造函数

\# 接收汽车的制造商 make、型号 model、生产年份 year 和一个 Engine 对象 engine，

\# 并将其存储为实例属性，同时初始化汽车的速度 speed 为 0。

\# start(self)：调用发动机的 start() 方法来启动汽车，实际上是调用关联的发动机对象的启动方法。

\# stop(self)：调用发动机的 stop() 方法来停止汽车。

\# accelerate(self, amount)：使汽车加速，将 amount 加到当前速度上，并返回当前速度信息。

\# brake(self, amount)：使汽车刹车，从当前速度中减去 amount，但速度不会低于 0，返回当前速度信息。

class Car:

def \_\_init\_\_(self, make, model, year, engine):

self.make = make

self.model = model

self.year = year

self.engine = engine

self.speed = 0

def start(self):

return self.engine.start()

def stop(self):

return self.engine.stop()

def accelerate(self, amount):

self.speed += amount

return f"Car is accelerating. Current speed: {self.speed} mph."

def brake(self, amount):

self.speed = max(0, self.speed - amount)

return f"Car is braking. Current speed: {self.speed} mph."

\# my\_engine = Engine(cylinders=6, horsepower=300)：创建一个具有 6 个气缸和 300 马力的发动机对象。

\# my\_car = Car(make="xiaomi", model="su7", year=2024, engine=my\_engine)：

\# 创建一个xiaomi su7汽车对象，将之前创建的发动机对象作为其发动机。

\# 调用汽车的各种方法：

\# print(my\_car.start())：启动汽车。

\# print(my\_car.accelerate(30))：加速 30 英里 / 小时。

\# print(my\_car.accelerate(20))：再次加速 20 英里 / 小时。

\# print(my\_car.brake(10))：刹车 10 英里 / 小时。

\# print(my\_car.stop())：停止汽车。

def main():

\# 创建一个发动机对象

my\_engine = Engine(cylinders=6, horsepower=300)

\# 创建一个汽车对象，将发动机对象作为参数传递给汽车对象

my\_car = Car(make="xiaomi", model="su7", year=2024, engine=my\_engine)

print(my\_car.start())

print(my\_car.accelerate(30))

print(my\_car.accelerate(20))

print(my\_car.brake(10))

print(my\_car.stop())

if \_\_name\_\_ == "\_\_main\_\_":

main()

# 9 **面向对象之三大特性**

52. **用面向对象的思想，假设你有汽车和摩托车不同的交通工具，出行的时候，你可以选择喜爱的方式出行**

class Vehicle:

def \_\_init\_\_(self, brand, model):

\# 封装：将属性设为私有，只能通过方法访问

self.\_\_brand = brand

self.\_\_model = model

def get\_brand(self):

return self.\_\_brand

def get\_model(self):

return self.\_\_model

def start(self):

raise NotImplementedError("Subclasses should implement this method")

class Car(Vehicle):

def \_\_init\_\_(self, brand, model, num\_doors):

\# 调用父类的构造函数

super().\_\_init\_\_(brand, model)

self.num\_doors = num\_doors

def start(self):

return f"The {self.get\_brand()} {self.get\_model()} car with {self.num\_doors} doors is starting."

class Motorcycle(Vehicle):

def \_\_init\_\_(self, brand, model, has\_sidecar):

super().\_\_init\_\_(brand, model)

self.has\_sidecar = has\_sidecar

def start(self):

if self.has\_sidecar:

return f"The {self.get\_brand()} {self.get\_model()} motorcycle with a sidecar is starting."

else:

return f"The {self.get\_brand()} {self.get\_model()} motorcycle is starting."

def start\_vehicle(vehicle):

\# 多态：不同的子类对象调用 start 方法有不同的行为

print(vehicle.start())

def main():

\# 创建对象

car = Car("xiaomi", "su7", 4)

motorcycle = Motorcycle("Harley Davidson", "Sportster", False)

motorcycle\_with\_sidecar = Motorcycle("BMW", "R1200", True)

\# 调用 start\_vehicle 函数

start\_vehicle(car)

start\_vehicle(motorcycle)

start\_vehicle(motorcycle\_with\_sidecar)

if \_\_name\_\_ == "\_\_main\_\_":

main()

# 10 **错误和异常**

53. **异常的处理方式**
54. **异常的传递**
55. **同学之间相互配合，各自开发一个功能，将开发的功能打包给对方使用**
56. **使用生成器函数作为迭代器对象并迭代**

# 11 **模块和包**

# 12 **Python高级语法**

def my\_range(start, end):

current = start

while current < end:

yield current

current += 1

def main():

\# 使用生成器函数作为迭代器

for i in my\_range(1, 5):

print(i)

if \_\_name\_\_ == "\_\_main\_\_":

main()

# 13 **进程与线程 + 网络编程**

57. **聊天程序基础版**

- 服务器端

import socket

def main():

\# 创建一个 TCP 套接字，AF\_INET 表示使用 IPv4 地址，SOCK\_STREAM 表示使用 TCP 协议。

server\_socket = socket.socket(socket.AF\_INET, socket.SOCK\_STREAM)

\# 将套接字绑定到本地 IP 地址 127.0.0.1 和端口号 12345

server\_socket.bind(('127.0.0.1', 12345))

\# 开始监听客户端连接，参数 1 表示最大连接数为 1。

server\_socket.listen(1)

print("服务器正在监听 127.0.0.1:12345...")

\# 接受客户端连接，返回客户端套接字和客户端地址

client\_socket, client\_address = server\_socket.accept()

print(f"客户端 {client\_address} 已连接。")

while True:

\# 接收客户端发送的数据，最大长度为 1024 字节。

data = client\_socket.recv(1024)

if not data:

break

print(f"客户端: {data.decode('utf-8')}")

\# 发送消息给客户端 将消息编码为 UTF-8 并发送给客户端。

message = input("服务器: ")

client\_socket.send(message.encode('utf-8'))

\# 关闭客户端套接字

client\_socket.close()

\# 关闭服务器套接字

server\_socket.close()

if \_\_name\_\_ == "\_\_main\_\_":

main()

- 客户端

import socket

def main():

\# 创建一个 TCP 套接字

client\_socket = socket.socket(socket.AF\_INET, socket.SOCK\_STREAM)

\# 连接到服务器的 IP 地址 127.0.0.1 和端口号 12345。

client\_socket.connect(('127.0.0.1', 12345))

while True:

\# 将用户输入的消息编码为 UTF-8 并发送给服务器

message = input("客户端: ")

client\_socket.send(message.encode('utf-8'))

\# 接收服务器消息

data = client\_socket.recv(1024)

if not data:

break

print(f"服务器: {data.decode('utf-8')}")

\# 关闭客户端套接字

client\_socket.close()

if \_\_name\_\_ == "\_\_main\_\_":

main()

58. **聊天程序改进版：服务器端+异常处理+多线程**

import socket

import threading

def handle\_client(client\_socket, client\_address):

print(f"客户端 {client\_address} 已连接。")

try:

while True:

\# 接收客户端消息

data = client\_socket.recv(1024)

if not data:

break

print(f"客户端 {client\_address}: {data.decode('utf-8')}")

\# 发送消息给客户端

message = input(f"服务器回复 {client\_address}: ")

client\_socket.send(message.encode('utf-8'))

except Exception as e:

print(f"与客户端 {client\_address} 通信时出错: {e}")

finally:

\# 关闭客户端套接字

client\_socket.close()

def main():

\# 创建一个 TCP 套接字

server\_socket = socket.socket(socket.AF\_INET, socket.SOCK\_STREAM)

\# 绑定 IP 地址和端口号

server\_socket.bind(('127.0.0.1', 12345))

\# 监听客户端连接

server\_socket.listen(5)

print("服务器正在监听 127.0.0.1:12345...")

while True:

\# 接受客户端连接

client\_socket, client\_address = server\_socket.accept()

\# 创建线程处理客户端

client\_thread = threading.Thread(target=handle\_client, args=(client\_socket, client\_address))

client\_thread.start()

if \_\_name\_\_ == "\_\_main\_\_":

main()