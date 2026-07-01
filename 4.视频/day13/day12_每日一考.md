### 编程题

1. 创建一个简单的 Python 模块math_operations.py，其中定义两个函数add和multiply，分别用于实现两个数的加法和乘法运算。在另一个 Python 文件中导入该模块，并调用这两个函数计算3 + 5和3 * 5的结果。

**答案**：

math_operations.py

```python
def add(a, b):
    return a + b
def multiply(a, b):
    return a * b
```

**主程序文件（假设为main.py）**

```python
import math_operations

result_add = math_operations.add(3, 5)
result_multiply = math_operations.multiply(3, 5)
print(f"3 + 5 = {result_add}")
print(f"3 * 5 = {result_multiply}")
```

**分析**：在math_operations.py模块中定义了add和multiply两个函数。在main.py文件中，使用import语句导入math_operations模块，然后通过模块名.函数名的方式调用模块中的函数进行计算，并打印结果，展示了模块的定义和使用过程。

2. 使用生成器表达式创建一个生成器，生成 1 到 10 的偶数。然后使用for循环遍历该生成器，打印每个偶数。

**答案**：

```python
even_numbers = (num for num in range(1, 11) if num % 2 == 0)
for num in even_numbers:
    print(num)
```

**分析**：生成器表达式(num for num in range(1, 11) if num % 2 == 0)创建了一个生成器对象even_numbers，它会生成 1 到 10 中的偶数。通过for循环遍历该生成器，每次循环时生成器生成一个偶数并赋值给num，然后打印出来，体现了生成器表达式的用法和生成器的迭代特性。

3. 创建一个迭代器类MyIterator，用于遍历一个给定列表的元素。实现__iter__和__next__方法。使用该迭代器类遍历列表[10, 20, 30, 40]，并打印每个元素。

**答案**：

```python
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
my_list = [10, 20, 30, 40]
my_iter = MyIterator(my_list)
for num in my_iter:
    print(num)
```

**分析**：MyIterator类实现了迭代器协议，__init__方法初始化迭代器，接收一个列表数据并设置初始索引为 0。__iter__方法返回迭代器对象本身。__next__方法在每次调用时，检查索引是否超出列表长度，如果超出则抛出StopIteration异常，表示迭代结束；否则返回当前索引位置的元素，并将索引加 1。在主程序中，创建MyIterator对象并使用for循环遍历，展示了自定义迭代器的创建和使用过程。