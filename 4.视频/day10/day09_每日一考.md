### 题目 1：封装特性

定义一个 BankAccount 类，有一个私有属性 __balance（初始余额为 0），提供一个 deposit 方法用于存钱，一个 withdraw 方法用于取钱，取钱时如果余额不足则打印提示信息。

**答案**：

```python
class BankAccount:
    def __init__(self):
        self.__balance = 0
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"存入{amount}元，当前余额为{self.__balance}元")
        else:
            print("存入金额需大于0")
    def withdraw(self, amount):
        if amount > 0 and amount <= self.__balance:
            self.__balance -= amount
            print(f"取出{amount}元，当前余额为{self.__balance}元")
        else:
            print("余额不足或取出金额不合法")
```

**分析**：通过在属性名前加双下划线 __ 将 __balance 设置为私有属性，外部无法直接访问和修改。deposit 方法和 withdraw 方法用于对 __balance 进行合法操作，体现了封装特性，即把数据和对数据的操作封装在一起，对外隐藏内部实现细节，保证数据的安全性。

### 题目 2：继承特性

定义一个 Animal 类，有一个 speak 方法打印 "I am an animal"。再定义一个 Cat 类继承自 Animal 类，并重写 speak 方法打印 "Meow"，创建 Cat 类的对象并调用 speak 方法。

**答案**：

```python
class Animal:
    def speak(self):
        print("I am an animal")
class Cat(Animal):
    def speak(self):
        print("Meow")
c = Cat()
c.speak()
```

**分析**：Cat 类继承自 Animal 类，因此 Cat 类拥有 Animal 类的属性和方法。Cat 类重写了从 Animal 类继承来的 speak 方法，当创建 Cat 类的对象 c 并调用 c.speak() 时，执行的是 Cat 类中重写后的 speak 方法，打印 "Meow"，展示了继承中方法重写的特性，子类可以根据自身需求对父类方法进行修改。

### 题目 3：多态特性

定义一个 Shape 类，有一个抽象方法 area（方法体为空）。再定义 Rectangle 类和 Circle 类继承自 Shape 类，分别实现 area 方法计算矩形面积（长 × 宽）和圆的面积（\(\pi r^2\)）。创建 Rectangle 和 Circle 类的对象，将它们放入一个列表中，遍历列表并调用每个对象的 area 方法。

**答案**：

```python
import math

class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width
    def area(self): 
        return self.length * self.width
    
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    def area(self): 
        return math.pi * self.radius ** 2
    
shapes = [Rectangle(4, 5), Circle(3)]
for shape in shapes:
    print(shape.area())
```

**分析**：Shape 类定义了一个抽象方法 area，作为子类必须实现的接口。Rectangle 类和 Circle 类继承自 Shape 类，并分别实现了 area 方法。将不同子类的对象放入同一个列表 shapes 中，遍历列表时，尽管 shape 变量在不同循环中引用不同类型的对象，但都能正确调用各自实现的 area 方法，这就是多态的体现，即不同对象对同一消息（方法调用）做出不同的响应。