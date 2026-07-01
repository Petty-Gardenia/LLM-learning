### 题目1：分支语句

编写一个 Python 程序，输入一个整数，判断它是正数、负数还是零，并输出相应的结果。

```
num = int(input("请输入一个整数："))
if num > 0:
    print("这个数是正数")
elif num < 0:    
    print("这个数是负数")
else:
    print("这个数是零")
```



### 题目 2：循环控制

编写一个while循环，计算 1 到 100 的整数之和。

```
sum_num = 0
i = 1
while i <= 100:
    sum_num += i
    i += 1
print(sum_num)
```



### 题目 3：输出100~1000中的所有水仙花数

水仙花数:3位正整数等于各个位数字的立方和

```
num = 100

while num < 1000:
    a = num // 100
    b = num // 10 % 10
    c = num % 10
    if num == a ** 3 + b ** 3 + c ** 3:
        print(num)
    num += 1
```

