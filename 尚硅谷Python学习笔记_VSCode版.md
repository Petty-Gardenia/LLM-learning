# 尚硅谷大模型技术之Python基础 — 学习笔记（VS Code 版）

> 版本：V1.0 | 作者：尚硅谷研究院 | 课程使用 Python 3.12.8
> 本笔记整合课程讲义、每日一考、课后练习与阶段考试，共17章，涵盖Python从入门到网络编程。
> VS Code 适配版：使用 VS Code 作为开发环境。

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

### 2.2 VS Code 安装与配置

1. 官网下载：https://code.visualstudio.com/
2. 安装完成后，打开 VS Code
3. 安装 Python 扩展：
   - 点击左侧活动栏的 **Extensions** 图标（或按 `Ctrl+Shift+X`）
   - 搜索框输入 "Python"
   - 找到 Microsoft 发布的 **Python** 扩展，点击 **Install**
4. Pylance 通常会随 Python 扩展自动安装（提供智能代码补全、类型检查等）
5. 推荐安装的扩展：

   | 扩展名 | 用途 |
   |--------|------|
   | Python | Python 语言支持（调试、运行、格式化） |
   | Pylance | 语言服务器，提供智能提示和类型检查 |
   | Jupyter | 在 VS Code 中运行 Jupyter Notebook |
   | GitLens | Git 增强工具，可视化代码历史 |

### 2.3 VS Code 中创建 Python 项目

1. **打开项目文件夹**：`File` → `Open Folder`（或 `Ctrl+K Ctrl+O`），选择一个空文件夹作为项目目录
2. **创建虚拟环境**：
   - 按 `Ctrl+Shift+P` 打开命令面板
   - 输入 "Python: Create Environment"
   - 选择 **venv**（Python 内置虚拟环境工具）
   - 选择要使用的 Python 版本
3. VS Code 会自动检测到虚拟环境，并在右下角提示你是否要选择它为解释器 → 点击 **Yes**
4. 在文件资源管理器中点击新建文件图标，创建 `.py` 文件，开始编码

### 2.4 第一个 Python 程序（VS Code 版）

创建一个新的 `.py` 文件，输入以下代码：

```python
print("hello world")
```

**三种运行方式：**

| 方式 | 操作 |
|------|------|
| 方式一 | 点击编辑器右上角的 **Run** 按钮（▶） |
| 方式二 | 右键编辑器 → "Run Python" → "Run Python File in Terminal" |
| 方式三 | 按 `Ctrl+F5`（Run without debugging，直接运行不调试） |

输出结果会显示在下方 **Terminal** 面板中。

### 2.5 VS Code 常用快捷键

```
Ctrl+Shift+P    → 命令面板（最重要的快捷键，几乎所有功能都能从这里找到）
Ctrl+`          → 打开/关闭终端
Ctrl+B          → 切换侧边栏
Ctrl+Shift+X    → 扩展面板
Ctrl+K Ctrl+O   → 打开文件夹
Ctrl+S          → 保存
Ctrl+Z          → 撤销
Ctrl+/          → 行注释
Shift+Alt+F     → 代码格式化
Ctrl+F          → 查找
Ctrl+H          → 替换
Ctrl+D          → 选中下一个相同词
Ctrl+Shift+K    → 删除当前行
Alt+↑/↓         → 移动当前行
Ctrl+Shift+Enter → 上方插入行
Shift+Enter     → 下方插入行（光标可在任意位置）
F5              → 启动调试
Ctrl+F5         → 直接运行（不调试）
F9              → 切换断点
F10             → 单步跳过
F11             → 单步进入
Ctrl+Click      → 跳转到定义
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

#### 进制转换手工计算

**二进制→十进制**：从最低位开始，每位乘以2的(位数-1)次方，求和。
- 例：`1011` = 1×2³ + 0×2² + 1×2¹ + 1×2⁰ = 8 + 0 + 2 + 1 = **11**

**十进制→二进制**：不断除以2，余数倒序排列。
- 例：`56` → 56÷2=28余0, 28÷2=14余0, 14÷2=7余0, 7÷2=3余1, 3÷2=1余1, 1÷2=0余1 → **111000**

**二进制→十六进制**：4位一组，转对应十六进制。
- 例：`1001011` → 0100 1011 → 4 B → **0x4B**

**十六进制→二进制**：每位转4位二进制。
- 例：`0x23B` → 2=0010, 3=0011, B=1011 → **001000111011**

**二进制→八进制**：3位一组；**八进制→二进制**：每位转3位。

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
a, b = 0b1100, 0b1010  # 12, 10

# 按位与(&)：全1才1
print(f"{a:08b} & {b:08b} = {a & b:08b}")  # 00001000 = 8

# 按位或(|)：有1则1
print(f"{a:08b} | {b:08b} = {a | b:08b}")  # 00001110 = 14

# 按位异或(^)：不同为1
print(f"{a:08b} ^ {b:08b} = {a ^ b:08b}")  # 00000110 = 6

# 取反(~)：~x = -(x+1)
print(f"~{a} = {~a}")  # ~12 = -13

# 左移(<<)：高位丢弃，低位补0，每移一位相当于×2
print(f"{a} << 2 = {a << 2}")  # 48 = 12 × 4

# 右移(>>)：低位丢弃，高位补符号位，每移一位相当于÷2
print(f"{a} >> 2 = {a >> 2}")  # 3 = 12 ÷ 4

# 判断奇偶（性能最优）
num & 1  # 1=奇数, 0=偶数
```

> 负数参与位运算时，Python 使用补码表示。实际开发中位运算主要用于位标志、权限控制、性能优化等场景。

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

### 8.1 面向过程 vs 面向对象

**面向过程**：以"做什么"为主线，把问题分解为一系列函数调用。

```python
# 面向过程：做一顿饭
def buy(): return "食材"
def wash(ingredients): return "洗好的食材"
def cut(ingredients): return "切好的食材"
def cook(ingredients): return "做好的菜"
def serve(dish): print(f"上菜：{dish}")

ingredients = buy()
ingredients = wash(ingredients)
ingredients = cut(ingredients)
dish = cook(ingredients)
serve(dish)
```

**面向对象**：以"谁来做"为主线，把数据和操作封装在一起。

```python
# 面向对象：不同菜由不同对象负责
class Dish:
    def cook(self): pass

class Salad(Dish):
    def cook(self): return "沙拉"

class Stew(Dish):
    def cook(self): return "炖菜"

# 多态：同样的 cook() 方法，不同菜有不同实现
menu = [Salad(), Stew()]
for dish in menu:
    print(f"上菜：{dish.cook()}")
```

| | 面向过程 | 面向对象 |
|---|---|---|
| 思考方式 | 做什么（动词） | 谁来做（名词） |
| 组织方式 | 函数 | 类+对象 |
| 复用方式 | 函数调用 | 继承+组合+多态 |
| 适合场景 | 小脚本、简单逻辑 | 大型项目、复杂系统 |

### 8.2 基本概念

```
类(Class)  →  对象的模板/蓝图
对象(Object) → 类的具体实例
属性(Attribute) → 对象的数据（特征）
方法(Method) → 对象的行为（动作）
```

### 8.3 定义类

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

### 8.4 self

- 代表**实例对象本身**
- 定义方法时第一个参数必须是 self（名称约定）
- 调用时 Python 自动传入，不需要手动传

### 8.5 属性

#### 类属性 vs 实例属性（重要陷阱）

```python
class Person:
    home = "earth"      # 类属性：所有实例共享

p1 = Person()
p2 = Person()
print(p1.home, p2.home)  # earth earth

# 陷阱：通过实例赋值会创建实例属性，而非修改类属性！
p1.home = "mars"
print(p1.home, p2.home)  # mars earth ← p2 没变！
print(Person.home)       # earth ← 类属性也没变！

# 正确修改类属性
Person.home = "venus"
print(p1.home, p2.home)  # mars venus ← p1有实例属性所以遮蔽了类属性
```

### 8.6 动态特性

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

#### @property setter 验证

```python
class Student:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, value):
        if value == "李四":
            raise ValueError("不许叫李四！")
        self._name = value

s = Student("张三")
s.name = "王五"    # OK
# s.name = "李四"  # ValueError: 不许叫李四！
```

> ⚠️ **递归陷阱**：`@property` 装饰的方法名不要和实例属性同名！如果 `def name(self): return self.name` 会导致无限递归（RecursionError），因为 `self.name` 又会调用 property。正确做法是用 `_name` 存储实际值。

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

> 面向对象综合实战 — 继承、多态、对象交互。

### 10.1 游戏背景

绿色小猪偷走了鸟蛋，小鸟们组成愤怒复仇联盟，利用各自技能砸毁小猪的障碍物。

### 10.2 类设计

#### Birds 基类

```python
class Birds:
    def __init__(self, name, color, skill_description):
        self.name = name
        self.color = color
        self.skill_description = skill_description

    def fly(self):
        return f"{self.name}正在飞翔"

    def call(self):
        return f"{self.name}发出叫声"

    def use_skill(self):
        return f"{self.name}使用技能：{self.skill_description}"

    def __str__(self):
        return f"{self.color}的{self.name}"
```

#### 三种小鸟子类

```python
class RedBirds(Birds):
    def __init__(self):
        super().__init__("红鸟", "红色", "加速冲击")
    def fly(self):
        return f"{self.name}以稳定的速度飞翔"
    def call(self):
        return f"{self.name}：喂呀..."

class YellowBirds(Birds):
    def __init__(self):
        super().__init__("黄鸟", "黄色", "二次加速")
    def fly(self):
        return f"{self.name}以极快的速度飞翔"
    def call(self):
        return f"{self.name}：啾啾啾..."

class BlueBirds(Birds):
    def __init__(self):
        super().__init__("蓝鸟", "蓝色", "分身攻击")
    def fly(self):
        return f"{self.name}以优雅的姿态飞翔"
    def call(self):
        return f"{self.name}：叽叽叽..."
    def use_skill(self):
        return f"{self.name}分裂成三只小鸟，分散攻击多个目标！"
```

#### 障碍物类

```python
class Obstacle:
    def __init__(self, type_name, hp):
        self.type_name = type_name
        self.hp = hp

    def be_attacked(self, bird):
        # 不同鸟造成不同伤害
        if isinstance(bird, RedBirds):
            damage = 80
        elif isinstance(bird, YellowBirds):
            damage = 50
        elif isinstance(bird, BlueBirds):
            damage = 30
        else:
            damage = 20
        self.hp -= damage
        return damage

    def __str__(self):
        return f"{self.type_name}(HP:{self.hp})"
```

### 10.3 游戏模拟

```python
if __name__ == "__main__":
    # 创建小鸟
    red = RedBirds()
    yellow = YellowBirds()
    blue = BlueBirds()

    # 创建障碍物
    wood = Obstacle("木箱", 200)
    stone = Obstacle("石墙", 300)

    birds = [red, yellow, blue]
    obstacles = [wood, stone]

    # 攻击
    for bird in birds:
        print(bird.fly())
        print(bird.call())
        print(bird.use_skill())
        for obs in obstacles:
            if obs.hp > 0:
                damage = obs.be_attacked(bird)
                print(f"  {bird.name}攻击{obs.type_name}，造成{damage}伤害，剩余HP={obs.hp}")
        print()
```

**知识点总结**：Birds基类定义公共属性(fly/call/use_skill) → 子类个性化重写 → Obstacle用isinstance判断不同鸟类型 → 多态统一接口遍历攻击。

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

#### finally vs 外部代码的区别

```python
# 对比1：代码放在 finally 中
def test_finally():
    try:
        10 / 0                  # ZeroDivisionError
    except ValueError:          # 不匹配 ZeroDivisionError
        print("捕获异常")
    finally:
        print("finally 块执行") # ✅ 一定执行

# 输出：finally 块执行  → 程序崩溃（异常未被捕获）

# 对比2：代码放在 try-except 外面
def test_outside():
    try:
        10 / 0
    except ValueError:
        print("捕获异常")
    print("外部代码执行")       # ❌ 不执行（崩溃了）

# 结论：finally 确保即使异常未处理也会执行，适合释放资源
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

### 13.5 命名空间

命名空间 = 名字到对象的映射，Python 用字典实现。

| 命名空间 | 生命周期 | 示例 |
|----------|----------|------|
| **内置名称** | 解释器启动→退出，永不删除 | `print`, `len`, `range` |
| **模块全局** | 导入模块→解释器退出 | 模块级变量和函数 |
| **函数局部** | 函数调用→返回/异常时删除 | 函数内定义的变量 |

```python
# 三种命名空间演示
x = 100           # 模块全局命名空间

def test():
    y = 200       # 函数局部命名空间
    print(len)    # 内置命名空间 (len)
    print(x)      # 访问全局命名空间
    print(y)      # 访问局部命名空间
```

> 作用域决定了代码可以访问哪些命名空间中的名字。LEGB 规则（L→E→G→B）就是从这四个命名空间按顺序查找。

### 13.6 闭包

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

### 15.5 HTTP 协议

#### 请求消息结构

```
请求行（方法 URI 版本）   GET /index.html HTTP/1.1
请求头（键值对）           Host: example.com
                          User-Agent: python-requests/2.31
空行（\r\n）
请求体（可选）             {"key": "value"}
```

#### 响应消息结构

```
状态行（版本 状态码 信息）  HTTP/1.1 200 OK
响应头（键值对）            Content-Type: application/json
空行（\r\n）
响应体                      {"data": "..."}
```

#### HTTP 请求方法

| 方法 | 用途 | 安全性 |
|------|------|--------|
| GET | 获取资源 | 幂等 |
| POST | 创建资源/提交数据 | 非幂等 |
| PUT | 更新/替换资源 | 幂等 |
| DELETE | 删除资源 | 幂等 |
| HEAD | 只获取响应头 | 幂等 |
| OPTIONS | 查询支持的方法 | 幂等 |

#### HTTP 状态码分类

| 范围 | 类型 | 常见状态码 |
|------|------|-----------|
| 1xx | 信息 | 100 Continue, 101 Switching Protocols |
| 2xx | 成功 | 200 OK, 201 Created, 202 Accepted |
| 3xx | 重定向 | 301 永久, 302 临时, 304 Not Modified |
| 4xx | 客户端错误 | 400 Bad Request, 403 Forbidden, 404 Not Found |
| 5xx | 服务器错误 | 500 Internal Error, 502 Bad Gateway, 503 Unavailable |

### 15.6 HTTP 请求实战

```python
import requests

response = requests.get('https://v1.hitokoto.cn/')
if response.status_code == 200:
    data = response.json()
    print(f"句子：{data['hitokoto']}")
    print(f"来源：{data['from']}")
else:
    print(f"请求失败：{response.status_code}")
```

### 15.7 Starlette + Uvicorn 搭建 Web API

```python
# 安装：pip install starlette uvicorn
from starlette.applications import Starlette
from starlette.responses import JSONResponse
from starlette.routing import Route
import uvicorn

async def homepage(request):
    return JSONResponse({"message": "Hello, Starlette!"})

async def greet(request):
    name = request.path_params.get("name", "World")
    return JSONResponse({"greeting": f"Hello, {name}!"})

app = Starlette(routes=[
    Route("/", homepage),
    Route("/greet/{name}", greet),
])

if __name__ == "__main__":
    uvicorn.run(app, host="127.0.0.1", port=8000)
```

访问 `http://127.0.0.1:8000/` 返回 `{"message": "Hello, Starlette!"}`
访问 `http://127.0.0.1:8000/greet/Python` 返回 `{"greeting": "Hello, Python!"}`

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

### 17.2 Customer 类完整实现

```python
import re

class Customer:
    def __init__(self, c_id, name, age="None", phone="None", email="None"):
        self.c_id = c_id
        self.name = name
        self.age = age
        self.phone = phone
        self.email = email

    def __str__(self):
        return f"ID: {self.c_id:<15} Name: {self.name:<15} Age: {self.age:<15} Phone: {self.phone:<15} Email: {self.email:<15}"

    @staticmethod
    def check_id(c_id):
        return c_id.isdigit()

    @staticmethod
    def check_name(name):
        return name.isalpha()

    @staticmethod
    def check_age(age):
        return age.isdigit()

    @staticmethod
    def check_phone(phone):
        pattern = r"^1[3456789]\d{9}$"
        return bool(re.match(pattern, phone))

    @staticmethod
    def check_email(email):
        pattern = r"[\w!#$%&'*+-/=?^`{|}~.]+@[\w!#$%&'*+-/=?^`{|}~.]+\.[a-zA-Z]{2,}$"
        return bool(re.match(pattern, email))
```

### 17.3 CMS 类完整实现

```python
import time

class CMS:
    def __init__(self):
        self.customer_id_dict = {}      # {cid: Customer}
        self.customer_name_dict = {}    # {name: {cid: Customer}} — 同名客户支持

    # ============ 输入方法 ============

    def set_customer_id(self):
        """输入客户ID，3次机会，纯数字验证，检查重复"""
        for i in range(3):
            if i < 2:
                customer_id = input("请输入客户ID：")
            else:
                customer_id = input("还剩最后一次机会，请慎重：")
            if Customer.check_id(customer_id):
                if customer_id in self.customer_id_dict:
                    print("该ID已存在！")
                    return False
                return customer_id
            print("ID必须为纯数字！")
        print("3次机会已用完")
        return False

    def set_customer_name(self):
        """输入客户姓名，3次机会，纯字母验证"""
        for i in range(3):
            if i < 2:
                name = input("请输入客户姓名：")
            else:
                name = input("还剩最后一次机会：")
            if Customer.check_name(name):
                return name
            print("姓名必须为纯字母！")
        print("3次机会已用完")
        return False

    def set_customer_age(self):
        """输入年龄，1次机会，可跳过"""
        age = input("请输入客户年龄（直接回车跳过）：")
        if age == "":
            return "None"
        if Customer.check_age(age):
            return age
        print("年龄不合理，设为空")
        return "None"

    def set_customer_phone(self):
        """输入电话，1次机会，可跳过"""
        phone = input("请输入客户电话（直接回车跳过）：")
        if phone == "":
            return "None"
        if Customer.check_phone(phone):
            return phone
        # 兼容不常见格式
        if re.match(r"^[\d\-]+$", phone):
            print("格式不常见，但仍可添加")
            return phone
        print("电话格式错误，设为空")
        return "None"

    def set_customer_email(self):
        """输入邮箱，1次机会，可跳过"""
        email = input("请输入客户邮箱（直接回车跳过）：")
        if email == "":
            return "None"
        if Customer.check_email(email):
            return email
        print("邮箱格式错误，设为空")
        return "None"

    # ============ 业务方法 ============

    def add_customer(self):
        print("\n===== 添加客户 =====")
        if not (customer_id := self.set_customer_id()):
            return
        if not (customer_name := self.set_customer_name()):
            return

        customer = Customer(
            customer_id,
            customer_name,
            self.set_customer_age(),
            self.set_customer_phone(),
            self.set_customer_email()
        )

        # 双字典索引
        self.customer_id_dict[customer_id] = customer
        inner_dict = self.customer_name_dict.get(customer_name, {})
        inner_dict[customer_id] = customer
        self.customer_name_dict[customer_name] = inner_dict
        print("✅ 添加客户成功！")

    def delete_customer(self):
        print("\n===== 删除客户 =====")
        customer_id = input("请输入要删除的客户ID：")
        if customer_id not in self.customer_id_dict:
            print("该客户不存在")
            return
        customer = self.customer_id_dict.pop(customer_id)
        # 同步删除 name_dict
        name_dict = self.customer_name_dict.get(customer.name, {})
        name_dict.pop(customer_id, None)
        if not name_dict:
            self.customer_name_dict.pop(customer.name, None)
        print(f"✅ 已删除客户：{customer.name}")

    def update_customer(self):
        print("\n===== 修改客户 =====")
        customer_id = input("请输入要修改的客户ID：")
        if customer_id not in self.customer_id_dict:
            print("该客户不存在")
            return
        c = self.customer_id_dict[customer_id]
        print(f"当前值：{c}")
        # 逐字段更新
        if (name := input(f"新姓名（{c.name}，回车跳过）：")):
            if Customer.check_name(name):
                # 更新双字典中的姓名索引
                old_name = c.name
                c.name = name
                inner = self.customer_name_dict.get(old_name, {})
                inner.pop(customer_id, None)
                if not inner:
                    self.customer_name_dict.pop(old_name, None)
                new_inner = self.customer_name_dict.get(name, {})
                new_inner[customer_id] = c
                self.customer_name_dict[name] = new_inner
        if (age := input(f"新年龄（{c.age}，回车跳过）：")):
            if Customer.check_age(age): c.age = age
        if (phone := input(f"新电话（{c.phone}，回车跳过）：")):
            if Customer.check_phone(phone): c.phone = phone
        if (email := input(f"新邮箱（{c.email}，回车跳过）：")):
            if Customer.check_email(email): c.email = email
        print("✅ 修改成功！")

    def search_customer(self):
        print("\n===== 查询客户 =====")
        keyword = input("请输入客户ID或姓名：")
        if keyword.isdigit():
            c = self.customer_id_dict.get(keyword)
            print(c if c else "未找到")
        elif keyword.isalpha():
            inner = self.customer_name_dict.get(keyword, {})
            if inner:
                for c in inner.values():
                    print(c)
            else:
                print("未找到")
        else:
            print("输入格式不正确")

    def display_customer(self):
        print("\n===== 所有客户 =====")
        if not self.customer_id_dict:
            print("暂无客户信息")
            return
        for c in self.customer_id_dict.values():
            print(c)

    def display_menu(self):
        print("""
        ~~~~~~~~~~~~~ 硅谷客户管理系统 ~~~~~~~~~~~~~
            1. 添加客户      2. 删除客户
            3. 修改客户      4. 查询客户
            5. 显示所有客户   6. 退出系统
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
        """)

    def start(self):
        try:
            while True:
                self.display_menu()
                choice = input("请输入操作编号：")
                match choice:
                    case "1": self.add_customer()
                    case "2": self.delete_customer()
                    case "3": self.update_customer()
                    case "4": self.search_customer()
                    case "5": self.display_customer()
                    case "6":
                        print("\b \b" * 50 + "感谢使用，再见！")
                        break
                    case _:
                        print("输入有误，请重新输入")
                        time.sleep(1)
        except (EOFError, KeyboardInterrupt):
            print("\n系统异常退出")

if __name__ == "__main__":
    CMS().start()
```

### 17.4 涉及技术点

| 技术 | 应用位置 |
|------|----------|
| 面向对象 | Customer类和CMS类设计 |
| 正则表达式 | `check_phone()` 和 `check_email()` |
| 异常处理 | `try/except` 捕获 EOFError 和 KeyboardInterrupt |
| match-case | `start()` 中菜单选择 |
| 海象运算符 `:=` | `add_customer()` 中判断输入同时赋值 |
| 双字典索引 | `customer_id_dict` + `customer_name_dict` 实现 O(1) 查询 |
| 字符串格式化 | `__str__()` 中对齐输出 |

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

### B. VS Code 常用快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl+Shift+P` | 命令面板（最重要的快捷键） |
| `Ctrl+` ` | 打开/关闭终端 |
| `Ctrl+B` | 切换侧边栏 |
| `Ctrl+Shift+X` | 扩展面板 |
| `Ctrl+K Ctrl+O` | 打开文件夹 |
| `Ctrl+S` | 保存 |
| `Ctrl+Z` | 撤销 |
| `Ctrl+/` | 行注释 |
| `Shift+Alt+F` | 代码格式化 |
| `Ctrl+F` | 查找 |
| `Ctrl+H` | 替换 |
| `Ctrl+D` | 选中下一个相同词 |
| `Ctrl+Shift+K` | 删除当前行 |
| `Alt+↑/↓` | 移动当前行 |
| `Ctrl+Shift+Enter` | 上方插入行 |
| `Shift+Enter` | 下方插入行（光标可在任意位置） |
| `F5` | 启动调试 |
| `Ctrl+F5` | 直接运行（不调试） |
| `F9` | 切换断点 |
| `F10` | 单步跳过 |
| `F11` | 单步进入 |
| `Ctrl+Click` | 跳转到定义 |

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

### D. 虚拟环境与pip依赖管理

#### D.1 为什么需要虚拟环境

不同项目需要不同版本的库。比如项目A用 numpy 1.24，项目B用 numpy 2.0。没有虚拟环境，它们会互相冲突。

虚拟环境 = 给每个项目一个**独立的 Python 包空间**，互不干扰。

#### D.2 创建虚拟环境

```bash
# 方式1: venv（Python内置，推荐）
python -m venv myenv

# 方式2: conda（需安装Anaconda/Miniconda）
conda create -n myenv python=3.12
```

#### D.3 激活虚拟环境

```bash
# Windows (PowerShell/CMD)
myenv\Scripts\activate

# Windows (Git Bash)
source myenv/Scripts/activate

# macOS / Linux
source myenv/bin/activate

# conda 环境
conda activate myenv
```

激活后终端前面会显示 `(myenv)`。

#### D.4 退出虚拟环境

```bash
deactivate
# conda: conda deactivate
```

#### D.5 pip 常用命令

```bash
pip install numpy              # 安装包
pip install numpy==1.24.0      # 安装指定版本
pip install numpy>=1.24        # 安装最低版本
pip install -r requirements.txt # 批量安装
pip uninstall numpy            # 卸载
pip list                       # 查看已安装的包
pip show numpy                 # 查看包详情
pip freeze > requirements.txt  # 导出当前环境
```

#### D.6 requirements.txt

```txt
# requirements.txt 示例
numpy==1.24.0
pandas>=2.0
requests
```

生成和安装：
```bash
pip freeze > requirements.txt   # 导出
pip install -r requirements.txt # 安装
```

### E. JSON 处理

JSON (JavaScript Object Notation) 是数据交换的事实标准。LLM API 的请求和响应几乎全是 JSON。

#### E.1 基本操作

```python
import json

# Python dict → JSON 字符串（序列化）
data = {"name": "Alice", "age": 25, "skills": ["Python", "ML"]}
json_str = json.dumps(data)
print(json_str)  # {"name": "Alice", "age": 25, "skills": ["Python", "ML"]}

# JSON 字符串 → Python dict（反序列化）
data = json.loads('{"name": "Alice", "age": 25}')
print(data["name"])  # Alice
```

#### E.2 美化输出

```python
# indent: 缩进, ensure_ascii: 不转义中文
json_str = json.dumps(data, indent=2, ensure_ascii=False)
print(json_str)
# {
#   "name": "小明",
#   "age": 25
# }
```

#### E.3 文件读写

```python
# 写入 JSON 文件
with open("data.json", "w", encoding="utf-8") as f:
    json.dump(data, f, indent=2, ensure_ascii=False)

# 读取 JSON 文件
with open("data.json", "r", encoding="utf-8") as f:
    data = json.load(f)
```

#### E.4 处理 LLM API 响应（实战示例）

```python
import json
import requests

# 调用一言 API
response = requests.get("https://v1.hitokoto.cn/")
data = response.json()  # 直接解析 JSON 响应

print(f"句子: {data['hitokoto']}")
print(f"来源: {data['from']}")
```

#### E.5 JSON 与 Python 类型对照

| JSON 类型 | Python 类型 |
|-----------|------------|
| object `{}` | dict |
| array `[]` | list |
| string | str |
| number (int) | int |
| number (float) | float |
| true / false | True / False |
| null | None |

### F. datetime 时间处理

#### F.1 获取当前时间

```python
from datetime import datetime, date, timedelta

now = datetime.now()
print(now)          # 2025-07-01 19:30:00.123456
print(now.date())   # 2025-07-01
print(now.time())   # 19:30:00.123456
print(date.today()) # 2025-07-01
```

#### F.2 字符串与时间互转

```python
# 字符串 → datetime
dt = datetime.strptime("2025-07-01 19:30", "%Y-%m-%d %H:%M")

# datetime → 字符串
s = dt.strftime("%Y年%m月%d日 %H:%M")
print(s)  # 2025年07月01日 19:30
```

常用格式码：

| 代码 | 含义 | 示例 |
|------|------|------|
| %Y | 四位年份 | 2025 |
| %m | 月份(01-12) | 07 |
| %d | 日期(01-31) | 01 |
| %H | 小时(00-23) | 19 |
| %M | 分钟(00-59) | 30 |
| %S | 秒(00-59) | 45 |
| %A | 星期全称 | Tuesday |

#### F.3 时间计算

```python
from datetime import datetime, timedelta

now = datetime.now()
tomorrow = now + timedelta(days=1)        # 明天
last_week = now - timedelta(weeks=1)      # 上周
three_hours_later = now + timedelta(hours=3)  # 3小时后

# 计算时间差
diff = datetime(2025, 7, 1) - datetime(2025, 6, 1)
print(diff.days)  # 30
```

#### F.4 时间戳

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

### G. collections 常用数据结构

#### G.1 defaultdict — 带默认值的字典

```python
from collections import defaultdict

# 普通字典：访问不存在的键会报错
d = {}
# d["count"] += 1  # KeyError!

# defaultdict：访问不存在的键自动创建默认值
d = defaultdict(int)      # 默认值 0
d["apple"] += 1           # 不需要先判断键是否存在
d["apple"] += 1
print(d)  # defaultdict(<class 'int'>, {'apple': 2})

# 其他常见默认值
dd = defaultdict(list)    # 默认空列表
dd = defaultdict(set)     # 默认空集合
dd = defaultdict(str)     # 默认空字符串
```

经典用法 — 分组：
```python
students = [("一班", "张三"), ("二班", "李四"), ("一班", "王五")]
groups = defaultdict(list)
for cls, name in students:
    groups[cls].append(name)
# {'一班': ['张三', '王五'], '二班': ['李四']}
```

#### G.2 Counter — 计数器

```python
from collections import Counter

# 统计频次
words = ["a", "b", "a", "c", "b", "a"]
c = Counter(words)
print(c)              # Counter({'a': 3, 'b': 2, 'c': 1})
print(c.most_common(2))  # [('a', 3), ('b', 2)]

# 统计字符串中字符
c = Counter("abracadabra")
print(c)  # Counter({'a': 5, 'b': 2, 'r': 2, 'c': 1, 'd': 1})
```

#### G.3 namedtuple — 有名字的元组

```python
from collections import namedtuple

# 定义
Point = namedtuple("Point", ["x", "y"])
p = Point(10, 20)
print(p.x, p.y)   # 10 20 → 像对象一样访问
print(p[0], p[1]) # 10 20 → 像元组一样访问

# 用于数据记录
Student = namedtuple("Student", ["name", "age", "score"])
s = Student("张三", 20, 95)
print(f"{s.name}考了{s.score}分")
```

#### G.4 deque — 双端队列

```python
from collections import deque

dq = deque([1, 2, 3])
dq.append(4)        # 右侧添加
dq.appendleft(0)    # 左侧添加
dq.pop()            # 右侧弹出
dq.popleft()        # 左侧弹出
# 两头操作都是 O(1)，比 list 快
```

### H. 类型提示 typing

类型提示让代码更清晰，IDE 能提供更智能的自动补全和错误检查。

#### H.1 基本类型

```python
name: str = "Alice"
age: int = 25
score: float = 95.5
is_student: bool = True
```

#### H.2 函数中的类型提示

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

def add(a: int, b: int) -> int:
    return a + b

# 无返回值
def log(msg: str) -> None:
    print(msg)
```

#### H.3 容器类型（Python 3.9+）

```python
# 不需要 from typing import，直接用
names: list[str] = ["Alice", "Bob"]
scores: dict[str, int] = {"Alice": 95, "Bob": 87}
point: tuple[int, int] = (10, 20)
unique_ids: set[int] = {1, 2, 3}
```

#### H.4 常用 typing 类型

```python
from typing import Optional, Union, Any, Literal

# Optional[X] = X | None（可以是 X 或 None）
def get_user(id: int) -> Optional[dict]:
    """可能查不到用户，返回 None"""
    ...

# Union[X, Y] = X | Y（多种类型之一）
def process(data: Union[str, bytes]) -> str:
    ...

# Python 3.10+ 简化写法
def get_user(id: int) -> dict | None: ...
def process(data: str | bytes) -> str: ...

# Any = 任意类型（尽量少用）
def parse(text: str) -> Any: ...

# Literal = 只能是这几个值
def set_mode(mode: Literal["train", "eval", "test"]) -> None: ...
```

#### H.5 类型检查工具

```bash
pip install mypy
mypy your_script.py  # 静态类型检查
```

### I. VS Code 调试 Python

#### I.1 设置断点

在编辑器左侧行号旁边（称为 gutter）点击，会出现一个**红色圆点**，这就是断点。程序运行到这里时会暂停。

#### I.2 启动调试

按 `F5` 启动调试。如果是第一次调试，VS Code 会提示选择调试配置 → 选择 "Python File"。

#### I.3 调试工具栏

调试启动后，顶部会出现调试工具栏：

| 按钮 | 快捷键 | 功能 |
|------|--------|------|
| Continue | `F5` | 继续运行到下一个断点 |
| Step Over | `F10` | 单步跳过（执行当前行，不进入函数内部） |
| Step Into | `F11` | 单步进入（如果当前行有函数调用，进入函数内部） |
| Step Out | `Shift+F11` | 跳出当前函数 |
| Restart | `Ctrl+Shift+F5` | 重新启动调试 |
| Stop | `Shift+F5` | 停止调试 |

#### I.4 调试面板

调试时左侧会显示 **Run and Debug** 面板，包含：

- **VARIABLES（变量）**：显示当前作用域所有变量的值，包括局部变量和全局变量。点开字典、列表等容器可以查看内部详情。
- **WATCH（监视）**：可以添加任意表达式来监控其值变化。点击 `+` 号，输入表达式（如 `len(lst)` 或 `user.name`），调试时会实时计算并显示结果。
- **CALL STACK（调用堆栈）**：显示当前的函数调用链，点击可以跳转到对应帧查看该层的变量状态。
- **BREAKPOINTS（断点）**：列出所有断点，可以勾选启用/禁用。

#### I.5 调试控制台（Debug Console）

调试暂停时，下方的 **Debug Console** 可以**交互式执行 Python 代码**。可以直接输入变量名查看值，或执行任意 Python 表达式来测试想法。

```
# 在 Debug Console 中输入
>>> user.name
'Alice'
>>> len(data_list)
5
>>> sum(data_list)
150
```

### J. VS Code 中使用 Jupyter Notebook

#### J.1 创建 Notebook

直接在 VS Code 中创建 `.ipynb` 文件：`File` → `New File` → 选择 "Jupyter Notebook"，或直接在文件资源管理器中新建 `xxx.ipynb` 文件。

确保已安装 **Jupyter** 扩展（在扩展面板搜索安装）。

#### J.2 细胞（Cell）操作

每个 Notebook 由多个 cell 组成，每个 cell 可以是**代码（code）**或**Markdown（文档）**。

| 快捷键 | 功能 |
|--------|------|
| `Shift+Enter` | 运行当前 cell 并跳转到下一个 cell |
| `Ctrl+Enter` | 仅运行当前 cell（不跳转） |
| `Alt+Enter` | 运行当前 cell 并在下方插入新 cell |
| `dd`（编辑模式） | 删除当前 cell |
| `a`（编辑模式） | 上方插入 cell |
| `b`（编辑模式） | 下方插入 cell |
| `m`（编辑模式） | 切换为 Markdown cell |
| `y`（编辑模式） | 切换为 Code cell |

#### J.3 变量查看器

在 Notebook 窗口顶部，点击 **Variables** 按钮可以打开变量查看器，显示当前 Kernel 中所有变量的名称、类型和值。

#### J.4 图表内联显示

使用 matplotlib 等绘图库时，图表会自动内联显示在 cell 输出区域：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
y = np.sin(x)
plt.plot(x, y)
plt.title("Sine Wave")
plt.show()
```

### K. VS Code Git 集成

#### K.1 源代码管理面板

按 `Ctrl+Shift+G` 打开 **Source Control**（源代码管理）面板，这里会显示：

- 所有有改动的文件列表
- 每个文件旁有 `M`（修改）、`U`（未跟踪）、`D`（删除）等标记
- 点击文件可查看差异对比

#### K.2 暂存与提交

```text
1. Stage（暂存）：点击文件旁的 + 号，或点击 Changes 旁的 + 一次性暂存所有
2. Commit（提交）：在顶部消息框输入提交信息 → 按 Ctrl+Enter 提交
```

#### K.3 推送与拉取

- 提交后，底部状态栏会显示 "Sync Changes" 按钮 → 点击进行推送（push）
- 也可以点击 `...` 菜单 → Pull / Push
- 按 `Ctrl+Shift+P` → 输入 "Git: Pull" 拉取远程更新

#### K.4 分支管理

- 左下角状态栏显示当前分支名称
- 点击当前分支名 → 弹出分支列表 → 选择切换到已有分支，或选择 "Create new branch..." 创建新分支
- `...` 菜单中还提供 Merge Branch、Delete Branch 等操作

#### K.5 快捷操作

- 侧边栏文件列表中，文件旁颜色标记：
  - **绿色**：新增行
  - **红色**：删除行
  - **蓝色**：修改行
- 点击标记区域可查看行级差异对比

---

> 📝 **学习路线回顾**：基础知识 → 流程控制 → 容器类型 → 函数 → 文件 → OOP → 异常 → 模块包 → 高级语法 → 进程线程 → 网络编程 → 正则 → 项目实战
>
> 📚 本笔记基于尚硅谷大模型技术之Python基础课程 V1.0，整合了课堂讲义、每日一考(58题)、课后练习(含答案)和阶段考试。VS Code 适配版新增附录 D-K，涵盖虚拟环境、JSON、datetime、collections、类型提示、VS Code 调试、Jupyter Notebook 和 Git 集成。
