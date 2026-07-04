# 尚硅谷大模型技术之Python基础 — 学习笔记

> 版本：V1.1 (PyCharm版) | 作者：尚硅谷研究院 | 课程使用 Python 3.12.8
> 本笔记整合课程讲义、每日一考、课后练习与阶段考试，共17章 + 8个附录，涵盖Python从入门到网络编程。补充了虚拟环境、pip、JSON、datetime、collections、typing 等实用主题。

---

## 目录

1. [概述](#1-概述)
2. [快速入门](#2-快速入门)
3. [基础知识](#3-基础知识)
4. [流程控制语句](#4-流程控制语句)
5. [容器数据类型](#5-容器数据类型)
6. [函数](#6-函数)
7. [文件操作](#7-文件操作)
8. [面向对象：类和对象](#8-面向对象类和对象)
9. [面向对象：三大特性](#9-面向对象三大特性)
10. [综合案例：愤怒的小鸟](#10-综合案例愤怒的小鸟)
11. [错误和异常](#11-错误和异常)
12. [模块和包](#12-模块和包)
13. [Python高级语法](#13-python高级语法)
14. [进程与线程](#14-进程与线程)
15. [网络编程](#15-网络编程)
16. [正则表达式](#16-正则表达式)
17. [综合案例：客户信息管理系统](#17-综合案例客户信息管理系统)

**附录**

- A. [阶段考试选择题](#a-阶段考试题目选择题)
- B. [PyCharm 常用快捷键](#b-pycharm-常用快捷键)
- C. [Python 内置函数速查](#c-python-内置函数速查)
- D. [虚拟环境与pip依赖管理](#附录d-虚拟环境与pip依赖管理)
- E. [JSON 处理](#附录e-json-处理)
- F. [datetime 时间处理](#附录f-datetime-时间处理)
- G. [collections 常用数据结构](#附录g-collections-常用数据结构)
- H. [类型提示 typing](#附录h-类型提示-typing)

---

## 1 概述

### 1.1 计算机组成

- **硬件**：运算器、控制器(CPU)、存储器、输入设备、输出设备
- **软件**：系统软件(OS) + 应用软件
- **裸机** = 只有硬件，无软件

### 1.2 编程语言分类

| 类型 | 特点 | 代表语言 |
|------|------|----------|
| 编译型 | 生成可执行文件后运行 | C, C++, Go |
| 解释型 | 逐句翻译执行，不生成可执行文件 | Python, PHP, JavaScript |

### 1.3 计算机语言简史

- **第一代 机器语言**：二进制代码，如 `0000,0000,000000010000` 代表 LOAD A, 16
- **第二代 汇编语言**：助记符 LOAD/MOVE，面向机器，不易移植
- **第三代 高级语言**：接近人类语言，需要编译器或解释器

### 1.4 为什么学Python

**起源**：1989年 Guido van Rossum（荷兰）圣诞节开发，1991年发布第一版  
**设计哲学**：优雅、明确、简单 — "用一种方法，最好是只有一种方法来做一件事"

**应用场景**：Web开发(Django/Flask) · 网络爬虫 · 自动化运维 · 数据分析(Numpy/Pandas) · AI/ML(PyTorch/TensorFlow) · 办公自动化 · 量化交易 · 3D游戏

**优点**：易学、丰富标准库、大量第三方库、可移植、可扩展、免费开源  
**缺点**：运行速度慢(解释型)、代码不能加密(发布即源码)

### 1.5 Python版本与解释器

- Python 2 已于 2020.1.1 停止更新，**主流是 Python 3.x**
- **CPython**（最广泛）· IPython（交互增强）· PyPy（JIT加速）· Jython（Java平台）· IronPython（.Net平台）

---

## 2 快速入门

### 2.1 安装Python

1. 官网 https://www.python.org/ → Downloads → 选版本(3.12.8) → **Install**安装包
2. 安装时勾选 "Add Python to PATH"
3. 验证：`python --version`

> **Install vs Embeddable**：Install 包含完整标准库+pip，适合开发；Embeddable 是精简版，适合嵌入其他应用。

### 2.2 安装PyCharm

- 官网 https://www.jetbrains.com/pycharm/download
- 专业版试用30天，社区版免费
- 常用快捷键：`Ctrl+/` 注释 · `Ctrl+Alt+L` 格式化 · `Ctrl+D` 复制行 · `Tab/Shift+Tab` 缩进

### 2.3 第一个Python程序

三种运行方式：

```python
# 1. 交互式命令行
>>> print("hello")

# 2. 脚本模式
# hello.py → python hello.py

# 3. IDE模式（推荐日常使用）
print("hello world")
```

---

## 3 基础知识

### 3.1 注释

```python
# 单行注释（#后加一个空格）

"""
多行注释（三个引号）
实际上是多行字符串
"""
```

### 3.2 变量

- **创建**：`变量名 = 值`（无需声明类型）
- **多个变量**：`a = b = c = 10` 或 `x, y, z = 10, 20, 30`
- **交换**：`a, b = b, a`
- **常量**：约定全大写 `PI = 3.14159`

#### 标识符命名规则

- 只能含字母、数字、下划线，**不能以数字开头**
- **区分大小写**，不能与关键字重名
- 三种命名法：大驼峰 `UpperCamelCase` · 小驼峰 `lowerCamelCase` · 蛇形 `snake_case`

> Python关键字：`False, None, True, and, as, assert, async, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield`

### 3.3 进制与编码

#### 进制表示
- 二进制 `0b`/`0B` · 八进制 `0o` · 十六进制 `0x`

#### 进制转换函数
```python
bin(10)   # '0b1010'  十进制→二进制
oct(10)   # '0o12'    十进制→八进制
hex(10)   # '0xa'     十进制→十六进制
int('1010', 2)  # 10  二进制→十进制
```

#### 原码、反码、补码

| | 正数 | 负数 |
|---|---|---|
| **原码** | 二进制表示 | 绝对值二进制，最高位置1 |
| **反码** | =原码 | 原码符号位不变，其余取反 |
| **补码** | =原码 | 反码+1 |

> **计算机用补码存储**：统一处理加减法，避免 +0 和 -0 两个编码。

### 3.4 基本数据类型

#### Python 数据类型总览

| 类别 | 类型 | 可变性 |
|------|------|--------|
| 数值 | int, float, complex, bool | 不可变 |
| 字符串 | str | 不可变 |
| 容器 | list, tuple, set, dict | list/dict/set可变, tuple不可变 |
| 特殊 | None | — |

#### int 关键点
```python
# 大数可用_分隔
big = 1_000_000  # 1000000

# 小整数池 [-5, 256]：相同值指向同一对象
a = 100; b = 100  # a is b → True
a = 1000; b = 1000  # a is b → False

# type vs isinstance：isinstance考虑继承（bool是int子类）
isinstance(True, int)  # True
```

#### float 关键点
```python
0.1 + 0.2  # 0.30000000000000004（精度问题）
from decimal import Decimal
Decimal('0.1') + Decimal('0.2')  # Decimal('0.3')
```

#### bool 关键点
- `True == 1`, `False == 0`（bool 是 int 子类）
- **Falsy值**：None, 0, 0.0, False, '', [], {}, (), set()
- `is` 比较身份(id)，`==` 比较值

#### 字符串基础
```python
s = 'hello'  # 单引号
s = "hello"  # 双引号
s = """多行
字符串"""   # 三引号

# 转义字符：\n \t \\ \' \"
# 原始字符串：r"C:\new\test"
```

#### 类型转换
- 隐式：int→float 自动
- 显式：`int() float() str() bool() eval() chr() ord() tuple() list() set()`

#### 编码解码
```python
"你好".encode('utf-8')    # b'\xe4\xbd\xa0\xe5\xa5\xbd'
b'\xe4\xbd\xa0'.decode('utf-8')  # '你'
# UTF-8：英文1字节，中文3字节；GBK：英文1字节，中文2字节
```

### 3.5 输入输出

```python
# 输入
name = input("请输入姓名：")  # 返回str

# 输出
print("hello", end="")  # 自定义结尾
print("a", "b", sep="-")  # a-b

# % 占位符
print("我叫%s，今年%d岁" % (name, age))

# format 方法
print("我叫{}，今年{}岁".format(name, age))
print("{1} {0}".format("world", "hello"))  # hello world

# f-string（推荐）
print(f"我叫{name}，今年{age}岁")
print(f"{name=}")  # name='张三'（调试用）
```

### 3.6 运算符

#### 算术运算符
`+ - * / //(整除) % **(幂)`

#### 赋值运算符
`= += -= *= /= //= %= **=`  
`:=` 海象运算符（表达式内赋值）：`if (n := len(list)) > 5:`

#### 比较运算符
`== != > < >= <=` — 字符串按ASCII逐字符比较

#### 逻辑运算符
`and or not` — 短路求值，返回实际值而非bool：
```python
3 and 5  # 5
0 or 10  # 10
```

#### 位运算符
`& | ^ ~ << >>`

```python
# 取反：~x = -(x+1)
~5  # -6

# 用位运算判断奇偶
num & 1  # 1=奇数, 0=偶数
```

#### 成员/身份运算符
```python
'a' in 'abc'      # True
a is None         # 身份判断
```

#### 运算符优先级
`**` → `~ + -`(一元) → `* / // %` → `+ -` → `<< >>` → `&` → `^` → `|` → 比较 → 逻辑

### 3.7 PEP8 编码规范

- **缩进**：4个空格
- **行长度**：≤79字符（代码）/ ≤72字符（注释）
- **函数/类之间**：两个空行
- **UTF-8编码**，不用分号结尾

---

## 4 流程控制语句

### 4.1 分支语句

```python
# 单分支
if 条件:
    语句

# 双分支
if 条件:
    语句
else:
    语句

# 多分支
if 条件1:
    语句
elif 条件2:
    语句
else:
    语句

# match-case（Python 3.10+）
match value:
    case 1 | 2:          # | 表示或
        print("1或2")
    case _:               # _ 通配符
        print("其他")

# 三目运算符
x if 条件 else y
```

### 4.2 循环语句

```python
# while 循环
while 条件:
    循环体
else:                # 正常结束执行
    语句

# for 循环
for 变量 in 可迭代对象:
    循环体

# range(start, stop, step)
range(5)         # 0,1,2,3,4
range(1, 5)      # 1,2,3,4
range(1, 10, 2)  # 1,3,5,7,9

# 循环控制
break     # 跳出整个循环
continue  # 跳过本次迭代
pass      # 占位符，什么都不做
```

### 每日一考·流程控制

> **Q**：输出100~1000中所有水仙花数（3位正整数=各位立方和）  
> **A**：153, 370, 371, 407  
> ```python
> num = 100
> while num < 1000:
>     a, b, c = num // 100, num // 10 % 10, num % 10
>     if num == a**3 + b**3 + c**3:
>         print(num)
>     num += 1
> ```

---

## 5 容器数据类型

### 5.1 序列通用操作

```python
# 索引
s[0], s[-1]

# 切片 [start:stop:step]
s[1:5], s[::-1]  # 反转

# 通用操作
len(s), max(s), min(s), s.count(x)
x in s, x not in s
s1 + s2, s * 3
```

### 5.2 列表 (list) — 可变·有序·可重复

```python
# 创建
lst = [1, 2, 3]
lst = list(range(5))  # [0,1,2,3,4]

# 增删改查
lst.append(4)          # 末尾添加
lst.insert(0, 0)       # 指定位置插入
lst.extend([5, 6])     # 批量添加
lst.remove(3)          # 删除值（不存在报错）
lst.pop()              # 删除末尾
lst.pop(1)             # 删除索引1
del lst[0]             # 删除索引
lst.clear()            # 清空

# 排序
lst.sort()             # 升序，原地修改
lst.sort(reverse=True) # 降序
sorted(lst)            # 返回新列表

# 列表推导式 ★
[i for i in range(10) if i % 2 == 0]           # [0,2,4,6,8]
[(i, j) for i in [1,2] for j in [3,4]]         # 所有组合
```

### 5.3 字符串 (str) — 不可变·有序

```python
# 常用方法
s.replace('old', 'new')
s.split(',')              # 按分隔符分割
','.join(['a', 'b'])      # 拼接
s.strip()                 # 去两端空白
s.upper() / s.lower()
s.startswith('http') / s.endswith('.py')
s.find('sub')             # 找不到返回-1
s.index('sub')            # 找不到报错
s.count('a')

# 判断系列
s.isdigit() / s.isalpha() / s.isalnum() / s.isspace()
```

### 5.4 元组 (tuple) — 不可变·有序

```python
t = (1, 2, 3)
t = (1,)       # 单元素必须加逗号
t = tuple([1, 2, 3])

# 元组不可修改元素，但可变元素内容可变
t = ([1, 2], 3)
t[0].append(3)  # OK，改成([1,2,3], 3)
```

### 5.5 集合 (set) — 可变·无序·不重复

```python
s = {1, 2, 3}
s = set()       # 空集合（{}是空字典）
s = {x for x in range(5)}  # 集合推导式

s.add(4) / s.remove(3) / s.discard(5)  # discard不存在不报错

# 集合运算
s1 & s2        # 交集
s1 | s2        # 并集
s1 - s2        # 差集
s1 ^ s2        # 对称差集
```

### 5.6 字典 (dict) — 可变·键值对·键唯一

```python
d = {'name': 'Alice', 'age': 25}
d = dict(name='Alice', age=25)
d = {k: k**2 for k in range(5)}  # {0:0, 1:1, 2:4, 3:9, 4:16}

# 访问
d['name']              # 键不存在报错
d.get('name', '默认值')  # 键不存在返回默认值

# 增删改
d['new'] = 'value'
d.update({'a': 1, 'b': 2})
del d['key']
d.pop('key')
d.popitem()            # 删除最后一项

# 遍历
for k in d: ...
for k, v in d.items(): ...
for v in d.values(): ...
for k in d.keys(): ...
```

### 5.7 容器对比

| | list | tuple | set | dict |
|---|---|---|---|---|
| 可变 | ✅ | ❌ | ✅ | ✅ |
| 有序 | ✅ | ✅ | ❌ | ✅(3.7+) |
| 重复 | ✅ | ✅ | ❌(值) | ❌(键) |
| 符号 | `[]` | `()` | `{}` | `{k:v}` |

### 每日一考·容器

> **Q**：列表推导式 `[(i,j) for i in list1 for j in list2]` 生成什么？  
> **A**：list1每个元素与list2每个元素的所有组合（笛卡尔积）。

> **Q**：字典中如何安全获取不存在的键？  
> **A**：`d.get(key, default)` — 不存在返回default而非报错。

---

## 6 函数

### 6.1 函数定义

```python
def 函数名(参数列表):
    """文档字符串（docstring）"""
    函数体
    return 返回值

# 查看文档
help(函数名)
```

### 6.2 参数传递

> **核心**：Python 传的是**对象引用**。不可变对象像"传值"，可变对象像"传引用"。

```python
def f(num, lst):
    num = 10        # 不改变外部（不可变对象）
    lst.append(4)   # 改变外部（可变对象）

# *= 与 * 的区别
a = [1, 2]
a *= 2   # 原地修改（地址不变）
a = a * 2  # 创建新对象（地址改变）
```

### 6.3 参数形式

```python
# 位置参数
def f(a, b): ...

# 默认参数（默认值在定义时计算一次）
def f(a, b=10): ...

# 可变参数
def f(*args): ...    # args 是 tuple
def f(**kwargs): ... # kwargs 是 dict

# 强制位置/关键字（Python 3.8+）
def f(a, /, b, *, c): ...
# a: 必须位置, b: 任意, c: 必须关键字

# 解包传参
f(*[1, 2, 3])
f(**{'name': 'Alice'})
```

### 6.4 变量作用域 LEGB

| 层级 | 说明 | 示例 |
|------|------|------|
| **L**-ocal | 函数内部 | 函数内变量 |
| **E**-nclosing | 外层函数 | 闭包变量 |
| **G**-lobal | 模块级别 | 全局变量 |
| **B**-uilt-in | 内置 | print, len |

```python
# global：修改全局变量
x = 10
def f():
    global x
    x = 20

# nonlocal：修改外层函数变量
def outer():
    x = 10
    def inner():
        nonlocal x
        x = 20
```

> 注意：if/for/while **不创造**新作用域，只有 module/class/def/lambda 会。

### 6.5 递归

```python
# 阶乘
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)
```

### 6.6 Lambda 函数

```python
lambda 参数: 表达式

# 常用场景
sorted(students, key=lambda s: s['score'])
list(map(lambda x: x**2, [1, 2, 3]))
list(filter(lambda x: x > 0, [-1, 0, 2]))
from functools import reduce
reduce(lambda a, b: a+b, [1, 2, 3, 4])  # 10
```

### 6.7 类型注解

```python
def greet(name: str, age: int = 0) -> str:
    return f"Hello, {name}"

# 查看注解
greet.__annotations__  # {'name': str, 'age': int, 'return': str}
```

### 每日一考·函数

> **Q**：`*args` 和 `**kwargs` 的区别？  
> **A**：`*args` 接收多余的**位置**参数→元组；`**kwargs` 接收多余的**关键字**参数→字典。

> **Q**：函数内想修改全局变量怎么做？  
> **A**：用 `global` 关键字声明。但如果是可变对象且修改内容（非重新赋值），可不用 global。

---

## 7 文件操作

### 7.1 基本流程

```python
# 写文件
with open('file.txt', 'w', encoding='utf-8') as f:
    f.write('Hello\n')
    f.writelines(['line1\n', 'line2\n'])

# 读文件
with open('file.txt', 'r', encoding='utf-8') as f:
    content = f.read()        # 读全部
    line = f.readline()       # 读一行
    lines = f.readlines()     # 读全部行→列表
```

### 7.2 文件模式

| 模式 | 说明 |
|------|------|
| `r` | 只读，文件必须存在 |
| `w` | 只写，会覆盖 |
| `a` | 追加 |
| `x` | 新建，文件存在则报错 |
| `b` | 二进制模式 |
| `t` | 文本模式（默认） |
| `+` | 读写 |

### 7.3 文件拷贝案例

```python
# 优化版：分块读取，支持大文件
def copy_file(src, dst):
    with open(src, 'rb') as f_in:
        with open(dst, 'wb') as f_out:
            while True:
                chunk = f_in.read(1024 * 1024)  # 1MB
                if not chunk:
                    break
                f_out.write(chunk)
```

### 7.4 os/os.path 常用操作

```python
import os
os.rename('old', 'new')
os.remove('file.txt')
os.mkdir('dir')
os.makedirs('a/b/c')
os.getcwd()
os.listdir('.')
os.walk('dir')          # 递归遍历
os.path.exists('path')
os.path.join('dir', 'file')
os.path.split('path/to/file')   # ('path/to', 'file')
```

---

## 8 面向对象：类和对象

### 8.1 基本概念

```
类(Class)  →  对象的模板/蓝图
对象(Object) → 类的具体实例
属性(Attribute) → 对象的数据（特征）
方法(Method) → 对象的行为（动作）
```

### 8.2 定义类

```python
class Person:
    # 类属性（所有实例共享）
    species = "Homo sapiens"

    # 初始化方法（构造器）
    def __init__(self, name, age):
        self.name = name    # 实例属性
        self.age = age

    # 实例方法
    def introduce(self):
        return f"我是{self.name}，{self.age}岁"

    # 类方法
    @classmethod
    def create_anonymous(cls):
        return cls("匿名", 0)

    # 静态方法
    @staticmethod
    def is_adult(age):
        return age >= 18

    # 特殊方法
    def __str__(self):
        return f"Person({self.name})"

    def __del__(self):
        print(f"{self.name}被销毁")
```

### 8.3 self

- 代表**实例对象本身**
- 定义方法时第一个参数必须是 self（名称约定）
- 调用时 Python 自动传入，不需要手动传

### 8.4 动态特性

```python
p = Person("Alice", 25)
p.hobby = "reading"   # 动态添加属性
del p.hobby            # 动态删除

# 动态添加方法
import types
def say_hi(self):
    return "Hi!"
p.say_hi = types.MethodType(say_hi, p)

# __slots__ 限制实例属性
class Student:
    __slots__ = ('name', 'age')  # 只能有name和age
```

### 每日一考·类与对象

> **Q**：`__init__` 和 `__new__` 的区别？  
> **A**：`__new__` 创建并返回实例（先调用），`__init__` 初始化实例属性（后调用）。

---

## 9 面向对象：三大特性

### 9.1 封装 (Encapsulation)

```python
class BankAccount:
    def __init__(self):
        self.__balance = 0   # 双下划线→私有（名称改写为_BankAccount__balance）

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    # @property：方法变属性
    @property
    def balance(self):
        return self.__balance

    # @name.setter：支持赋值
    @balance.setter
    def balance(self, value):
        if value >= 0:
            self.__balance = value
```

- `_单下划线`：约定私有，可访问但不应访问
- `__双下划线`：名称改写 name mangling，`_类名__属性名`
- `@property`：方法像属性一样访问，支持 getter/setter/deleter

### 9.2 继承 (Inheritance)

```python
class Animal:
    def speak(self):
        return "I am an animal"

class Cat(Animal):         # 单继承
    def speak(self):        # 方法重写
        return "Meow"

class Dog(Animal):
    def speak(self):
        return "Woof"

# 多继承
class C(A, B):
    pass

# MRO（方法解析顺序）
C.__mro__  # C → A → B → object

# 调用父类方法
super().speak()            # 推荐
ParentClass.speak(self)    # 显式调用
```

> 重写 `__init__` 时记得调用 `super().__init__()` 以继承父类初始化。

### 9.3 多态 (Polymorphism)

```python
# 不同子类对同一方法有不同实现
def make_sound(animal):
    print(animal.speak())

make_sound(Cat())  # "Meow"
make_sound(Dog())  # "Woof"

# Shape → Rectangle → Circle 的 area() 统一接口
shapes = [Rectangle(4, 5), Circle(3)]
for shape in shapes:
    print(shape.area())  # 20, 28.27...
```

---

## 10 综合案例：愤怒的小鸟

面向对象综合实战，展示继承、多态、对象交互。

```python
class Birds:
    def __init__(self, name, color, attack_power):
        self.name = name
        self.color = color
        self.attack_power = attack_power

    def attack(self, obstacle):
        obstacle.hp -= self.attack_power

class RedBirds(Birds):
    def attack(self, obstacle):
        obstacle.hp -= self.attack_power * 2  # 双倍伤害

class YellowBirds(Birds):
    def attack(self, obstacle):
        obstacle.hp -= self.attack_power * 3  # 三倍伤害

class Obstacle:
    def __init__(self, type_name, hp):
        self.type_name = type_name
        self.hp = hp
```

---

## 11 错误和异常

### 11.1 异常处理语法

```python
try:
    # 可能出错的代码
    result = 10 / 0
except ZeroDivisionError as e:
    # 处理特定异常
    print(f"除零错误：{e}")
except (ValueError, TypeError) as e:
    # 处理多种异常
    print(f"类型/值错误：{e}")
except Exception as e:
    # 处理其他异常
    print(f"未知错误：{e}")
else:
    # try成功时执行（无异常）
    print("执行成功")
finally:
    # 无论是否异常都执行（释放资源）
    print("清理工作")
```

### 11.2 raise 与 assert

```python
# raise 抛出异常
def check_age(age):
    if age < 0:
        raise ValueError("年龄不能为负数")

# assert 断言（调试用）
assert x > 0, "x必须大于0"
# python -O 可禁用assert
```

### 11.3 自定义异常

```python
class InvalidAgeError(Exception):
    """自定义异常，继承自Exception"""
    pass

raise InvalidAgeError("年龄不合法")
```

### 11.4 with 上下文管理器

```python
# 自动管理资源，等价于 try...finally
with open('file.txt') as f:
    content = f.read()
# 自动调用 f.close()
```

### 11.5 常见异常速查

| 异常 | 触发场景 |
|------|----------|
| `KeyError` | 字典键不存在 |
| `IndexError` | 索引越界 |
| `ValueError` | 类型对但值不对（如 `int('abc')`） |
| `TypeError` | 类型不匹配 |
| `AttributeError` | 对象无此属性 |
| `FileNotFoundError` | 文件不存在 |
| `ZeroDivisionError` | 除零 |

---

## 12 模块和包

### 12.1 模块

```python
# 创建模块：math_operations.py
def add(a, b):
    return a + b

# 导入方式
import math_operations          # math_operations.add(3, 5)
import math_operations as mo    # mo.add(3, 5)
from math_operations import add # add(3, 5)
from math_operations import *   # 全部导入（受__all__限制）

# 模块搜索顺序：当前目录 → PYTHONPATH → 标准库
import sys
sys.path  # 查看搜索路径

# if __name__ == "__main__"
if __name__ == "__main__":
    # 直接运行时执行，被import时不执行
    print("模块被直接运行")
```

### 12.2 包

```
my_package/
    __init__.py    # 包的标志文件
    module_a.py
    module_b.py
    sub_package/
        __init__.py
        module_c.py
```

```python
import my_package.module_a
from my_package import module_a
from my_package.sub_package import module_c
```

### 12.3 安装第三方库

```bash
pip install package_name
pip install package_name==1.0.0
pip uninstall package_name
pip list
```

### 12.4 打包自己的库

```python
# setup.py
from setuptools import setup, find_packages
setup(
    name='mypackage',
    version='1.0',
    packages=find_packages(),
)
```

```bash
python setup.py sdist    # 生成源码包
pip install dist/mypackage-1.0.tar.gz
```

---

## 13 Python高级语法

### 13.1 浅拷贝与深拷贝

```python
import copy

# 浅拷贝：只拷贝第一层
lst = [[1, 2], [3, 4]]
shallow = copy.copy(lst)
shallow[0][0] = 99  # 影响原列表（内层共享）

# 深拷贝：递归拷贝所有层级
deep = copy.deepcopy(lst)
deep[0][0] = 88      # 不影响原列表

# 特殊：不可变类型的copy返回自身
a = (1, 2, 3)
copy.copy(a) is a  # True
```

### 13.2 迭代器

```python
# 可迭代对象 vs 迭代器
lst = [1, 2, 3]       # 可迭代(Iterable)，不是迭代器
it = iter(lst)         # 创建迭代器
next(it)               # 1

# 自定义迭代器
class MyIterator:
    def __init__(self, data):
        self.data = data
        self.index = 0
    def __iter__(self):
        return self
    def __next__(self):
        if self.index >= len(self.data):
            raise StopIteration
        value = self.data[self.index]
        self.index += 1
        return value
```

### 13.3 生成器

```python
# yield 函数→生成器
def my_range(start, end):
    current = start
    while current < end:
        yield current
        current += 1

# 生成器表达式（括号而不是方括号）
gen = (x**2 for x in range(10))

# send() 向生成器发送数据
def echo():
    while True:
        received = yield
        print(f"收到: {received}")
```

### 13.4 装饰器

```python
# 函数装饰器
def log(func):
    def wrapper(*args, **kwargs):
        print(f"调用 {func.__name__}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} 返回 {result}")
        return result
    return wrapper

@log
def add(a, b):
    return a + b

# 带参数的装饰器（三层嵌套）
def repeat(times):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(times):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def say_hello():
    print("Hello")

# 类装饰器
class LogDecorator:
    def __init__(self, func):
        self.func = func
    def __call__(self, *args, **kwargs):
        print(f"调用 {self.func.__name__}")
        return self.func(*args, **kwargs)

@LogDecorator
def greet(name):
    return f"Hello, {name}"
```

### 13.5 闭包

```python
def outer(x):
    def inner(y):
        return x + y    # inner记住了outer的x
    return inner

add5 = outer(5)
add5(3)   # 8
add5(10)  # 15
```

---

## 14 进程与线程

### 14.1 核心概念

| | 进程 (Process) | 线程 (Thread) |
|---|---|---|
| 内存 | 独立内存空间 | 共享进程内存 |
| 创建开销 | 大 | 小 |
| 通信 | 管道/Queue/共享内存 | 直接访问共享变量 |
| 适合 | CPU密集型 | I/O密集型 |
| GIL影响 | 不受影响 | 受影响 |

> **GIL（全局解释器锁）**：CPython中同一时刻只有一个线程执行Python代码。CPU密集型任务用**多进程**，I/O密集型任务用**多线程**。

### 14.2 多进程

```python
import multiprocessing

def worker(name):
    print(f"进程{name}工作中")

if __name__ == '__main__':
    p1 = multiprocessing.Process(target=worker, args=('A',))
    p2 = multiprocessing.Process(target=worker, args=('B',))
    p1.start()
    p2.start()
    p1.join()  # 等待进程结束
    p2.join()

# 进程池
pool = multiprocessing.Pool(processes=4)
pool.apply_async(worker, args=('C',))
pool.close()
pool.join()

# 进程间通信（Queue）
q = multiprocessing.Queue()
q.put(data)
data = q.get()
```

### 14.3 多线程

```python
import threading

# 基本用法同multiprocessing
t = threading.Thread(target=func, args=(arg,))
t.start()
t.join()

# 线程池
from concurrent.futures import ThreadPoolExecutor
with ThreadPoolExecutor(max_workers=4) as executor:
    future = executor.submit(func, arg)
    result = future.result()

# 线程安全：加锁
lock = threading.Lock()
lock.acquire()
# 临界区代码
lock.release()

# 推荐写法
with lock:
    # 临界区代码
```

### 每日一考·进程线程

> **Q**：一个进程可以包含几个线程？进程间共享内存吗？  
> **A**：一个进程可包含多个线程；进程间**不**共享内存（线程共享）。

> **Q**：创建进程和创建线程哪个开销更大？  
> **A**：进程开销更大（需要分配独立内存空间）。

---

## 15 网络编程

### 15.1 网络基础

- **IP地址**：网络中主机的唯一标识（IPv4: 4字节，IPv6: 16字节）
- **端口号**：0-65535（0-1023为知名端口：HTTP 80, HTTPS 443, SSH 22, MySQL 3306）
- **协议**：通信规则的集合

#### TCP/IP 五层模型

| 层 | 协议 |
|----|------|
| 应用层 | HTTP, HTTPS, FTP, DNS, SMTP |
| 传输层 | TCP, UDP |
| 网络层 | IP, ICMP, ARP |
| 数据链路层 | 以太网 |
| 物理层 | 网线/光纤/无线 |

### 15.2 UDP 编程

```python
# 服务器端
import socket
server = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server.bind(('127.0.0.1', 8888))
data, addr = server.recvfrom(1024)  # 收数据
server.sendto(response, addr)       # 发数据
server.close()

# 客户端
client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
client.sendto(message, ('127.0.0.1', 8888))
data, _ = client.recvfrom(1024)
client.close()
```

### 15.3 TCP 编程

```python
# 服务器端
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('127.0.0.1', 8888))
server.listen(5)                              # 最大连接数
client_socket, addr = server.accept()         # 阻塞等待
data = client_socket.recv(1024)
client_socket.send(response.encode('utf-8'))
client_socket.close()
server.close()

# 客户端
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(('127.0.0.1', 8888))          # 三次握手
client.send(message.encode('utf-8'))
data = client.recv(1024)
client.close()
```

### 15.4 TCP多线程服务器

```python
import threading

def handle_client(client_socket, addr):
    try:
        while True:
            data = client_socket.recv(1024)
            if not data: break
            response = process(data)
            client_socket.send(response)
    except Exception as e:
        print(f"错误: {e}")
    finally:
        client_socket.close()

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('127.0.0.1', 8888))
server.listen(5)
while True:
    client, addr = server.accept()
    threading.Thread(target=handle_client, args=(client, addr)).start()
```

### 15.5 HTTP 请求

```python
import requests
response = requests.get('https://v1.hitokoto.cn/')
data = response.json()
```

---

## 16 正则表达式

### 16.1 常用模式

| 模式 | 含义 | 模式 | 含义 |
|------|------|------|------|
| `.` | 任意字符 | `\d` | 数字 |
| `\D` | 非数字 | `\w` | 字母数字下划线 |
| `\s` | 空白 | `^` | 行首 |
| `$` | 行尾 | `\b` | 单词边界 |
| `*` | 0次+ | `+` | 1次+ |
| `?` | 0或1次 | `{n}` | 恰好n次 |
| `{n,}` | n次+ | `{n,m}` | n到m次 |
| `[abc]` | a或b或c | `[^abc]` | 不是a/b/c |
| `x|y` | x或y | `()` | 分组 |
| `(?:)` | 非捕获分组 | `(?P<name>)` | 命名分组 |

> **建议用 `r""` 原始字符串**避免 `\` 转义问题。

### 16.2 re 模块

```python
import re

re.search(r'\d+', 'abc123')    # 搜索→Match对象或None
re.match(r'\d+', '123abc')     # 从头匹配
re.findall(r'\d+', 'a1b2c3')   # ['1', '2', '3']
re.sub(r'\d+', 'X', 'a1b2')     # 'aXbX'
re.split(r'[,;]', 'a,b;c')      # ['a', 'b', 'c']

# 编译正则（复用提高性能）
pattern = re.compile(r'\d+')
pattern.findall('a1b2c3')
```

### 16.3 常用验证

```python
# 手机号
re.match(r'^1[3-9]\d{9}$', phone)

# 邮箱
re.match(r'^[\w.-]+@[\w.-]+\.\w+$', email)

# 身份证
re.match(r'^\d{17}[\dXx]$', id_card)
```

---

## 17 综合案例：客户信息管理系统

### 17.1 项目结构

```python
# customer.py — 客户实体类
class Customer:
    def __init__(self, customer_id, name, age=None, phone=None, email=None):
        self.customer_id = customer_id
        self.name = name
        self.age = age
        self.phone = phone
        self.email = email

    @staticmethod
    def check_phone(phone):
        import re
        return bool(re.match(r'^1[3-9]\d{9}$', phone))

    @staticmethod
    def check_email(email):
        import re
        return bool(re.match(r'^[\w.-]+@[\w.-]+\.\w+$', email))
```

### 17.2 系统功能

```python
# cms.py — 管理系统
class CMS:
    def __init__(self):
        self.customer_id_dict = {}    # {id: Customer}
        self.customer_name_dict = {}  # {name: Customer}

    def display_menu(self):
        """显示主菜单：1添加 2删除 3修改 4查询 5显示全部 6退出"""

    def add_customer(self):
        """添加客户，ID和姓名必填（3次输入机会），手机和邮箱需验证"""

    def delete_customer(self):
        """按ID删除客户"""

    def update_customer(self):
        """按ID修改客户信息"""

    def search_customer(self):
        """按ID或姓名查询客户"""

    def display_customer(self):
        """显示所有客户信息"""
```

### 17.3 涉及技术点

- 面向对象：Customer类和CMS类设计
- 正则表达式：手机号和邮箱验证
- 异常处理：try/except捕获EOFError和KeyboardInterrupt
- match-case：菜单选择
- 海象运算符 `:=`：简化条件赋值
- 双字典索引：`id_dict` + `name_dict` 提供O(1)查询

---

## 附录

### A. 阶段考试题目（选择题）

1. 合法变量名：C. `_var1`
2. 不可变数据类型：D. tuple
3. `5 // 3` 结果：A. 1
4. if-elif-else 正确说法：A. elif可有多个，也可没有
5. 字符串→整数函数：B. int()
6. 关于函数错误说法：C. 函数内部变量是全局变量
7. 处理日期时间模块：C. datetime
8. break 跳出循环后输出：A. 1 2
9. 字典正确说法：B. 值可以重复 且 D. 可通过键访问
10. sum_list函数功能：B. 计算列表元素总和

### B. PyCharm 常用快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl + /` | 行注释 |
| `Ctrl + Alt + L` | 代码格式化 |
| `Ctrl + D` | 复制当前行 |
| `Ctrl + Y` | 删除当前行 |
| `Ctrl + Shift + ↑/↓` | 移动当前行 |
| `Ctrl + W` | 选中单词/代码块 |
| `Ctrl + P` | 查看方法参数 |
| `Tab / Shift+Tab` | 缩进/反缩进 |

### C. Python 内置函数速查

```python
# 类型转换
int() float() str() bool() list() tuple() set() dict() eval() chr() ord()

# 数学相关
abs() round() pow() sum() min() max() len() divmod()

# 迭代相关
range() enumerate() zip() map() filter() sorted() reversed() iter() next()

# 判断相关
type() isinstance() hasattr() callable() issubclass()

# 其他
print() input() open() help() dir() id() hash() bin() oct() hex()
```

---

> 📝 **学习路线回顾**：基础知识 → 流程控制 → 容器类型 → 函数 → 文件 → OOP → 异常 → 模块包 → 高级语法 → 进程线程 → 网络编程 → 正则 → 项目实战
>
> 📚 本笔记基于尚硅谷大模型技术之Python基础课程 V1.0，整合了课堂讲义、每日一考(58题)、课后练习(含答案)和阶段考试。

---

## 附录D: 虚拟环境与pip依赖管理

### D.1 为什么需要虚拟环境

不同项目需要不同版本的库。比如项目A用 numpy 1.24，项目B用 numpy 2.0。没有虚拟环境，它们会互相冲突。

**虚拟环境 = 给每个项目一个独立的 Python 包空间**，互不干扰。

### D.2 创建虚拟环境

```bash
# 方式1: venv（Python内置，推荐）
python -m venv myenv

# 方式2: conda（需安装Anaconda/Miniconda）
conda create -n myenv python=3.12
```

### D.3 激活虚拟环境

```bash
# Windows (PowerShell / CMD)
myenv\Scripts\activate

# Windows (Git Bash)
source myenv/Scripts/activate

# macOS / Linux
source myenv/bin/activate

# conda 环境
conda activate myenv
```

激活后终端前面会显示 `(myenv)`。

### D.4 退出虚拟环境

```bash
deactivate
# conda: conda deactivate
```

### D.5 PyCharm 中配置虚拟环境

创建新项目时选择解释器类型（参见第2章）：
- **Project venv**：自动在项目目录下创建 `.venv`，推荐
- **Base Conda**：使用 Anaconda 环境
- **Custom environment**：自定义或选择已有环境

已有项目切换解释器：`File → Settings → Project → Python Interpreter → 齿轮图标 → Add`

### D.6 pip 常用命令

```bash
pip install numpy                 # 安装包
pip install numpy==1.24.0         # 安装指定版本
pip install numpy>=1.24           # 安装最低版本
pip install -r requirements.txt   # 批量安装
pip uninstall numpy               # 卸载
pip list                          # 查看已安装的包
pip show numpy                    # 查看包详情
pip freeze > requirements.txt     # 导出当前环境
```

### D.7 requirements.txt

LLM 项目中，`requirements.txt` 是标配——别人拿到你的代码，一条命令就能还原环境。

```txt
# requirements.txt 示例
numpy==1.24.0
pandas>=2.0
requests
torch>=2.0
transformers
```

生成和安装：
```bash
pip freeze > requirements.txt    # 导出当前环境的所有包
pip install -r requirements.txt  # 一键安装所有依赖
```

---

## 附录E: JSON 处理

JSON (JavaScript Object Notation) 是数据交换的事实标准。**LLM API 的请求和响应几乎全是 JSON**。

### E.1 基本操作

```python
import json

# Python dict → JSON 字符串（序列化）
data = {"name": "Alice", "age": 25, "skills": ["Python", "ML"]}
json_str = json.dumps(data)
print(json_str)
# {"name": "Alice", "age": 25, "skills": ["Python", "ML"]}

# JSON 字符串 → Python dict（反序列化）
data = json.loads('{"name": "Alice", "age": 25}')
print(data["name"])  # Alice
```

### E.2 美化输出

```python
# indent: 缩进层级, ensure_ascii=False: 不转义中文
json_str = json.dumps(data, indent=2, ensure_ascii=False)
print(json_str)
# {
#   "name": "小明",
#   "age": 25,
#   "skills": ["Python", "ML"]
# }
```

### E.3 文件读写

```python
# 写入 JSON 文件
with open("data.json", "w", encoding="utf-8") as f:
    json.dump(data, f, indent=2, ensure_ascii=False)

# 读取 JSON 文件
with open("data.json", "r", encoding="utf-8") as f:
    data = json.load(f)
```

### E.4 LLM API 实战示例

```python
import requests

# 调用一言 API，响应是 JSON
response = requests.get("https://v1.hitokoto.cn/")
data = response.json()               # 直接解析 JSON

print(f"句子：{data['hitokoto']}")
print(f"来源：{data['from']}")
```

### E.5 JSON 与 Python 类型对照

| JSON 类型 | Python 类型 |
|-----------|------------|
| object `{}` | dict |
| array `[]` | list |
| string `"..."` | str |
| number (整数) | int |
| number (小数) | float |
| `true` / `false` | True / False |
| `null` | None |

---

## 附录F: datetime 时间处理

### F.1 获取当前时间

```python
from datetime import datetime, date, timedelta

now = datetime.now()
print(now)          # 2025-07-01 19:30:00.123456
print(now.date())   # 2025-07-01
print(now.time())   # 19:30:00.123456
print(date.today()) # 2025-07-01
```

### F.2 字符串与时间互转

```python
# 字符串 → datetime
dt = datetime.strptime("2025-07-01 19:30", "%Y-%m-%d %H:%M")

# datetime → 字符串
s = dt.strftime("%Y年%m月%d日 %H:%M")
print(s)  # 2025年07月01日 19:30
```

**常用格式码：**

| 代码 | 含义 | 示例 |
|------|------|------|
| `%Y` | 四位年份 | 2025 |
| `%m` | 月份(01-12) | 07 |
| `%d` | 日期(01-31) | 01 |
| `%H` | 小时(00-23) | 19 |
| `%M` | 分钟(00-59) | 30 |
| `%S` | 秒(00-59) | 45 |
| `%A` | 星期全称 | Tuesday |

### F.3 时间计算

```python
from datetime import datetime, timedelta

now = datetime.now()
tomorrow = now + timedelta(days=1)          # 明天
last_week = now - timedelta(weeks=1)        # 上周
three_hours_later = now + timedelta(hours=3)  # 3小时后

# 计算两个日期相差多少天
diff = datetime(2025, 7, 1) - datetime(2025, 6, 1)
print(diff.days)  # 30
```

### F.4 时间戳

```python
import time
from datetime import datetime

# 当前时间戳（秒）
ts = time.time()  # 1751376600.123

# 时间戳 → datetime
dt = datetime.fromtimestamp(ts)

# datetime → 时间戳
ts = dt.timestamp()
```

---

## 附录G: collections 常用数据结构

Python 内置容器之外，`collections` 模块提供了更专业的容器。

### G.1 defaultdict — 带默认值的字典

访问不存在的键不会报错，而是自动创建默认值。**分组操作的神器。**

```python
from collections import defaultdict

# 普通字典：访问不存在的键会 KeyError
d = {}
# d["count"] += 1  # KeyError!

# defaultdict：安全无忧
d = defaultdict(int)   # 默认值 0
d["apple"] += 1
d["apple"] += 1
print(d)  # {'apple': 2}
```

经典用法 — 按班级分组：
```python
students = [("一班", "张三"), ("二班", "李四"), ("一班", "王五")]
groups = defaultdict(list)
for cls, name in students:
    groups[cls].append(name)
# {'一班': ['张三', '王五'], '二班': ['李四']}
```

### G.2 Counter — 计数器

```python
from collections import Counter

# 统计频次
words = ["a", "b", "a", "c", "b", "a"]
c = Counter(words)
print(c)                      # Counter({'a': 3, 'b': 2, 'c': 1})
print(c.most_common(2))       # [('a', 3), ('b', 2)]

# 直接统计字符串
c = Counter("abracadabra")    # Counter({'a': 5, 'b': 2, 'r': 2, ...})
```

### G.3 namedtuple — 有名字的元组

```python
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
p = Point(10, 20)
print(p.x, p.y)    # 10 20 — 像对象属性一样访问
print(p[0], p[1])  # 10 20 — 也可以像元组一样索引

# 轻量级数据记录，不需要定义类
Student = namedtuple("Student", ["name", "age", "score"])
s = Student("张三", 20, 95)
print(f"{s.name}考了{s.score}分")
```

### G.4 deque — 双端队列

```python
from collections import deque

dq = deque([1, 2, 3])
dq.append(4)       # 右侧添加  → [1, 2, 3, 4]
dq.appendleft(0)   # 左侧添加  → [0, 1, 2, 3, 4]
dq.pop()           # 右侧弹出  → 4
dq.popleft()       # 左侧弹出  → 0
# 所有操作 O(1)，比 list 的 insert(0) / pop(0) 快得多
```

---

## 附录H: 类型提示 typing

类型提示让代码意图更清晰，IDE 能提供更智能的自动补全和错误检查。现代 Python 项目的标配。

### H.1 基本类型提示

```python
name: str = "Alice"
age: int = 25
score: float = 95.5
is_student: bool = True
```

### H.2 函数中的类型提示

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

def add(a: int, b: int) -> int:
    return a + b

def log(msg: str) -> None:      # None 表示无返回值
    print(msg)
```

### H.3 容器类型提示（Python 3.9+）

```python
# 直接用小写类型名
names: list[str] = ["Alice", "Bob"]
scores: dict[str, int] = {"Alice": 95, "Bob": 87}
point: tuple[int, int] = (10, 20)
unique_ids: set[int] = {1, 2, 3}
```

### H.4 高级类型

```python
# Optional：可以是 X 或 None（Python 3.10+ 用 X | None）
def get_user(id: int) -> dict | None:
    """查不到用户时返回 None"""
    ...

# Union：多种类型之一
def process(data: str | bytes) -> str:
    ...

# Literal：只能是这几个值
def set_mode(mode: "train | eval | test") -> None:
    ...
```

### H.5 静态类型检查

```bash
pip install mypy
mypy your_script.py   # 检查类型错误，不运行代码
```

---

> 📝 **学习路线回顾**：基础知识 → 流程控制 → 容器类型 → 函数 → 文件 → OOP → 异常 → 模块包 → 高级语法 → 进程线程 → 网络编程 → 正则 → 项目实战
>
> 🛠️ 本笔记基于尚硅谷大模型技术之Python基础课程 V1.0，整合课堂讲义 + 每日一考(58题) + 课后练习 + 阶段考试 + 补充实用主题(虚拟环境/pip/JSON/datetime/collections/typing)。
>
> 📘 本版本为 **PyCharm 版**，适用于使用 PyCharm IDE 的学习者。
