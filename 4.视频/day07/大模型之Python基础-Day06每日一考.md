### 题目 1：函数定义与调用

定义一个函数 add_numbers，它接受两个整数参数 a 和 b，返回这两个数的和，并调用该函数计算 3 和 5 的和。

**答案**：

```python
def add_numbers(a, b):
    return a + b
result = add_numbers(3, 5)
print(result) 
```

**分析**：首先使用 def 关键字定义了 add_numbers 函数，它有两个参数 a 和 b。函数体中通过 return 语句返回两数之和。调用函数时，传入 3 和 5 作为参数，函数执行加法运算后返回结果，将结果赋值给 result 并打印。

### 题目 2：默认参数

定义一个函数 greet，它接受一个字符串参数 name，并且有一个默认参数 message，默认值为 "Hello"，函数功能是打印出问候语，如 "Hello, Alice"。调用该函数时，分别传入和不传入 message 参数进行测试。

**答案**：

```python
def greet(name, message="Hello"):
    print(f"{message}, {name}")
greet("Bob")
greet("Charlie", "Hi")
```

**分析**：在函数定义中，message 参数被赋予了默认值 "Hello"。当调用 greet("Bob") 时，由于没有传入 message 参数，函数使用默认值 "Hello" 打印问候语。而调用 greet("Charlie", "Hi") 时，传入了新的 message 值 "Hi"，函数则使用传入的值打印问候语，体现了默认参数在简化函数调用方面的作用。

### 题目 3：可变参数

定义一个函数 sum_all，它接受任意数量的整数参数，返回所有参数的和。例如调用 sum_all(1, 2, 3) 应返回 6，调用 sum_all(10, 20, 30, 40) 应返回 100。

**答案**：

```python
def sum_all(*args):
    total = 0
    for num in args:
        total += num
    return total
result1 = sum_all(1, 2, 3)
result2 = sum_all(10, 20, 30, 40)
print(result1)
print(result2) 
```

**分析**：函数定义中的 *args 表示可变参数，它可以接收任意数量的位置参数。在函数内部，通过循环遍历 args 元组，将所有参数累加起来，最后返回总和。这样函数就可以灵活处理不同数量参数的求和操作。

### 题目 4：函数嵌套调用

定义两个函数，square 函数接受一个整数参数，返回该数的平方；cube 函数接受一个整数参数，通过调用 square 函数返回该数的立方（立方 = 平方 × 该数）。调用 cube 函数计算 3 的立方。

**答案**：

```python
def square(num):
    return num * num
def cube(num):
    return square(num) * num
result = cube(3)
print(result) 
```

**分析**：square 函数实现了计算平方的功能。cube 函数内部调用了 square 函数获取参数的平方值，再乘以参数本身得到立方值。这种函数嵌套调用展示了如何利用已有的函数构建更复杂的功能，提高代码的复用性。