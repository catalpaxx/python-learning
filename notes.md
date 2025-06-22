# Python 学习笔记
## 基础概念
### 1.变量与数据类型

**- 整数** (int)、浮点数 (float)：x = 5 / y = 3.14

**- 字符串** (str): name = "Cindy"

**- 布尔值** (bool)：用于表示逻辑值，它有两个可能的值True/False，常用于条件判断中，比如if语句/循环/逻辑运算。

**- 变量赋值**：x = 5

**- 类型转换**：str(5)，int("5")

### 2.运算符

**- 算数运算符**： +, -, *, /, 

//：地板除，用于整数除法，结果向下取整：例如 print(7 // 3) 即 7 除以 3 商是 2.33，地板除会取整为 2

% ：取余数，例如 print(7 % 3) 即 7 除以 3 商是 2，余数是 1

**：幂运算，一个数乘以自身若干次，例如 print(2 ** 3) 即 2 的 3 次方是 8

**- 赋值运算符**： 

+= ：例如 x += y（即x = x + y ）-=， *=， /=， //=， %=， **= 同理

    在循环中常见的用法：
    total = 0
    for i in range(5):  # i 依次是 0, 1, 2, 3, 4
        total += i  # 相当于 total = total + i
    print(total)  # 输出 0+1+2+3+4 = 10

**- 比较运算符**：<, >, <=, >=

==（等于）：用于检查两个值是否相等。如果相等，返回 True，否则返回 False。

!=（不等于）：用于检查两个值是否不相等。如果不相等，返回 True，否则返回 False。

**- 逻辑运算符**：and, or, not

### 3.条件从句

**- if 语句**：判断条件是否成立（if-elif-else）elif的作用是 在多个条件中依次判断哪一个成立，并且只执行第一个为真的代码块。

    if 条件1:
    # 如果条件1成立，就执行这里
    elif 条件2:
    # 如果条件1不成立，但条件2成立，就执行这里
    elif 条件3:
    # 如果前面条件都不成立，但条件3成立，就执行这里
    else:
    # 如果上面所有条件都不成立，就执行这里

### 4. 循环

**- for 循环**：遍历可迭代对象（如列表、字典）

    for i in range(5):
    print(i)

**- while 循环**：条件成立时循环执行

    while x > 0:
    x -= 1

### 5. 列表与字典

**- 列表**：[1, 2, 3, 4]，支持索引、切片、增删改查

    my_list = [1, 2, 3, 4]
    my_list.append(5)
    print(my_list[0])  # 输出 1

**- 字典**：键值对结构，{"name": "Cindy", "age": 25}

    my_dict = {"name": "Cindy", "age": 25}
    print(my_dict["name"])  # 输出 Cindy

### 6. 函数

**- 定义函数**：def 关键字

    def greet(name):
        print(f"Hello, {name}")
    greet("Cindy")

### 7. 模块与导入

**- 使用 import 导入标准库或第三方库**

    import math
    print(math.sqrt(16))  # 输出 4.0

### 8. 异常处理

**- 使用 try/except 语句处理异常**

    try:
        x = 10 / 0
    except ZeroDivisionError:
        print("除数不能为零")

### 9. 列表推导式与字典推导式

**- 列表推导式**：快速生成列表

    squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]

**- 字典推导式**：生成字典

    square_dict = {x: x**2 for x in range(5)}  # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

### 10. 文件操作

**- 打开文件并读取、写入**

    with open("file.txt", "r") as file:
        content = file.read()
        print(content)

### 11. 常用标准库

**- datetime**：日期和时间操作

    import datetime
    now = datetime.datetime.now()
    print(now)

**- os**：操作系统相关功能

    import os
    print(os.getcwd())  # 获取当前工作目录


















