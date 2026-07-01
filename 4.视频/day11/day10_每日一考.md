### 一、选择题

- 以下哪种异常通常在尝试访问字典中不存在的键时引发？（  ）

A. KeyError

B. IndexError

C. ValueError

D. TypeError

**答案**：A

**分析**：当使用字典的键来获取值，而该键不存在时，Python 会引发KeyError异常。IndexError通常与列表、元组等序列类型中超出索引范围的操作相关；ValueError常见于函数接收到类型正确但值不合适的参数时，如int('abc')；TypeError则是在操作或函数应用于不适当类型的对象时引发，例如对字符串和数字进行不支持的加法运算。

- 以下关于try - except - finally语句的描述，正确的是（  ）

A. finally块中的代码只有在没有异常发生时才会执行

B. finally块中的代码无论是否发生异常都会执行

C. 如果try块中发生异常，except块和finally块都不会执行

D. except块和finally块只能存在一个

**答案**：B

**分析**：finally块的主要特点就是无论try块中是否发生异常，也无论异常是否被except块捕获，finally块中的代码都会执行。它通常用于释放资源等操作，如关闭文件。选项 A 错误，finally块并非只在无异常时执行；选项 C 错误，发生异常时except块会执行（如果有匹配的异常类型），finally块也会执行；选项 D 错误，try - except - finally语句中，except块和finally块可以同时存在。

### 二、简答题

1. 简述异常处理的作用。

**答案**：异常处理的作用主要有以下几点：

- 增强程序的健壮性：当程序运行过程中遇到错误（如除零操作、文件不存在等）时，异常处理机制可以捕获这些错误，避免程序因未处理的错误而崩溃，确保程序能够继续运行或者以一种可控的方式结束。

- 提高代码的可读性：通过将可能出现错误的代码放在try块中，对应的错误处理代码放在except块中，使得代码结构更加清晰，阅读代码的人能够清楚地知道哪些部分可能出错以及出错后如何处理。

- 便于调试和维护：异常处理能够提供详细的错误信息，帮助开发者快速定位和解决问题，同时在维护代码时，清晰的异常处理结构有助于理解代码在不同情况下的行为。

2. 自定义异常类通常继承自哪个基类？为什么要继承自这个基类？

**答案**：自定义异常类通常继承自Exception类。继承自Exception类的原因是，Exception类处于 Python 异常类层次结构的较高层级，它作为所有内置异常类的基类，具有通用性。继承自Exception类可以让自定义异常类自动拥有一些标准的异常特性和行为，同时也方便在try - except语句中与其他内置异常一起进行捕获和处理，使得代码的异常处理逻辑更加统一和规范。

### 三、编程题

1. 编写一段 Python 代码，尝试将字符串 "123abc" 转换为整数，如果转换失败，捕获 ValueError 异常，将异常信息记录到一个文本文件 error.log 中。

**答案**：

```python
try:
    num = int("123abc")
except ValueError as e:
    with open('error.log', 'a', encoding='utf - 8') as file:
        file.write(str(e) + '\n')
```

**分析**：try块尝试将字符串 "123abc" 转换为整数，由于该字符串不是有效的数字形式，会引发ValueError异常。except ValueError as e捕获异常，并将异常对象e转换为字符串形式，使用with open语句以追加模式打开error.log文件，将异常信息写入文件中并换行，以便后续查看错误记录。

2. 定义一个函数check_age，该函数接受一个年龄参数。如果年龄小于 0，抛出一个自定义异常InvalidAgeError；如果年龄大于 120，抛出UnrealisticAgeError。这两个自定义异常类都继承自Exception类。调用该函数并传入一个不合法的年龄值，捕获并处理异常。

**答案**：

```python
class InvalidAgeError(Exception):
    pass

class UnrealisticAgeError(Exception):
    pass

def check_age(age):
    if age < 0:
        raise InvalidAgeError("年龄不能为负数")
    elif age > 120:
        raise UnrealisticAgeError("年龄超过120不太现实")

try:
    check_age(-5)
except InvalidAgeError as e:
    print(e)
except UnrealisticAgeError as e:
    print(e)
```

**分析**：首先定义了两个自定义异常类InvalidAgeError和UnrealisticAgeError，都继承自Exception类。check_age函数根据传入的年龄参数进行判断，如果年龄小于 0，抛出InvalidAgeError异常并附带错误信息；如果年龄大于 120，抛出UnrealisticAgeError异常及相应信息。在try - except块中调用check_age(-5)，触发InvalidAgeError异常，被对应的except块捕获并打印异常信息，展示了自定义异常的定义、抛出和捕获处理过程。