### 题目 1：动态添加属性

定义一个 Person 类，在类外动态地给 Person 类的一个对象添加一个 hobby 属性，值为 "reading"，并打印该属性。

**答案**：

```python
class Person:
    pass
p = Person()
p.hobby = "reading"
print(p.hobby)
```

**分析**：Person 类定义较为简单，没有属性和方法。创建 Person 类的对象 p 后，直接通过 对象.属性名 = 值 的方式动态添加了 hobby 属性，并赋值为 "reading"。最后打印该属性，体现了 Python 中对象动态添加属性的灵活性。

### 题目 2：动态添加方法

定义一个 Circle 类，该类有一个 radius 属性。在类外定义一个函数 calculate_area，功能是计算圆的面积（面积公式：\(S = π r^2），然后将这个函数动态地添加为 Circle 类的一个对象的方法，并调用该方法计算半径为 5 的圆的面积。（提示：可使用 types.MethodType）

**答案**：

```python
import types
import math
class Circle:
    def __init__(self, radius):
        self.radius = radius
def calculate_area(self):
    return math.pi * self.radius ** 2
c = Circle(5)
c.calculate_area = types.MethodType(calculate_area, c)
area = c.calculate_area()
print(area)
```

**分析**：Circle 类有一个用于初始化半径的构造函数。calculate_area 函数接收 self 参数（代表对象本身），计算圆的面积。通过 types.MethodType 将 calculate_area 函数绑定到 Circle 类的对象 c 上，使其成为 c 的一个方法。调用 c.calculate_area() 即可计算并打印出半径为 5 的圆的面积，展示了动态添加方法的过程。
