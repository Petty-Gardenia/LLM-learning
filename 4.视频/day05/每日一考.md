### 题目1：列表操作

现有列表 my_list = [10, 20, 30, 40, 50]，请编写代码实现：

1. 向列表末尾添加一个元素 60。

1. 取出列表中索引为 2 的元素。

1. 计算列表中所有元素的和。

   ```python
   my_list = [10, 20, 30, 40, 50]
   # 向列表末尾添加元素60
   my_list.append(60)
   # 取出索引为2的元素
   element = my_list[2]
   # 计算列表元素和
   sum_value = sum(my_list)
   print(my_list)
   print(element)
   print(sum_value)
   ```

   

### 题目2：列表操作

给定两个列表 `list1 = [1, 2, 3]` 和 `list2 = [4, 5, 6]`，使用列表推导式生成一个包含所有可能的元素对的列表，即 `[(1, 4), (1, 5), (1, 6), (2, 4), (2, 5), (2, 6), (3, 4), (3, 5), (3, 6)]`。 

```python

list1 = [1, 2, 3]
list2 = [4, 5, 6]
list3 = [(i,j) for i in list1  for j in list2]
print(list3)
```



### 题目3：循环控制

使用for循环的嵌套，打印如下图形的*

```python
    *
   ***
  *****
 *******
*********
n = 5
for i in range(1,n + 1):
    for j in range(n - i ):
          print(" ", end="")
    for k in range(2 * i - 1):
          print("*", end="")
    print()
```

