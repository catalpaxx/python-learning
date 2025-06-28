# Python 学习笔记
## 基础概念
### 1.变量与数据类型

**- 整数** (int)、浮点数 (float)：x = 5 / y = 3.14

**- 字符串** (str): name = "Cindy"

    字符串操作基础：
    1. 拼接：
    greeting = "Hello, " + "Cindy!"
    print(greeting)  # 输出: Hello, Cindy!
    也可以用 join() 来连接多个字符串：
    words = ["Hello", "Cindy"]
    greeting = " ".join(words)
    print(greeting)  # 输出: Hello Cindy
    
    2. 提取子串（切片）:
    text = "Hello, world!"
    print(text[0:5])  # 输出: Hello
        text[start:end] 会提取从 start 到 end-1 的字符。如果省略 start，默认从开始处开始；如果省略 end，默认到字符串的末尾。

    3. 字符串大小写转换:
    message = "hello, Cindy!"
    print(message.upper())  # 输出: HELLO, CINDY!
    print(message.lower())  # 输出: hello, cindy!

    4. 去除空格:
    message = "  Hello, Cindy!  "
    print(message.strip())  # 输出: Hello, Cindy!

    5. 查找和替换:
    查找：用 find() 找到子字符串的位置：
    message = "Hello, Cindy!"
    print(message.find("Cindy"))  # 输出: 7
    替换：用 replace() 替换字符串中的部分内容：
    message = "Hello, Cindy!"
    print(message.replace("Cindy", "Tom"))  # 输出: Hello, Tom!

    6. 计算字符个数:
    用 count() 计算某个字符或子字符串在字符串中出现的次数：
    message = "Hello, Cindy! Cindy is awesome."
    print(message.count("Cindy"))  # 输出: 2

    7. 首字母大写capitalize() + 每个单词首字母大写title():
    print(message.capitalize())  # 输出：Good night
    print(message.title())  # 输出：Good Night

    8. 替换字符串内容replace():
    print(message.replace("night", "morning"))  # 输出：good morning

    9. 检查子字符串是否存在in:
    print("night" in message)  # 输出：True
    print("hello" in message)  # 输出：False

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
    或者
    for fruit in fruits:
        print("我喜欢吃", fruit)

**- while 循环**：条件成立时循环执行

    while x > 0:
    x -= 1

### 5. 列表与字典

**- 列表**：是一串有顺序的元素，可以包含数字、字符串、布尔值，甚至是列表本身，支持索引、切片、增删改查

    my_list = [1, 2, 3, 4]
    my_list.append(5)
    print(my_list[0])  # 输出 1

列表中的每个元素都有编号，叫做索引（index），从 0 开始。

    修改元素：
    fruits[0] = "桃子"

    添加元素：
    fruits.append("西瓜")  # 添加到最后
    fruits.insert(1, "柠檬")  # 在索引 1 的位置插入

    删除元素：
    fruits.remove("香蕉")  # 按值删除
    del fruits[0]          # 按索引删除

列表常用方法：

    1. len()：获取列表长度
    print(len(fruits))  # 计算列表中元素的个数
    
    2. .sort()：对列表排序（永久修改）
    numbers = [5, 3, 8, 1]
    numbers.sort()
    print(numbers)  # 输出：[1, 3, 5, 8]
    
    3. sorted()：排序，但不修改原列表，默认是升序排序
    numbers = [5, 3, 8, 1]
    new_numbers = sorted(numbers)
    print(new_numbers)  # [1, 3, 5, 8]
    print(numbers)      # 原列表仍是 [5, 3, 8, 1]

它们都可以接收一个 key 参数，用来指定排序规则。这个 key 参数是一个函数，它的作用是决定每个元素应该按照什么方式进行排序。

    4. .reverse()：列表反转（不是排序）
    fruits = ["苹果", "香蕉", "橘子"]
    fruits.reverse()
    print(fruits)  # ['橘子', '香蕉', '苹果']

    **降序排序**：.sort(reverse=True)
    eg：my_list.sort(reverse=True)

    5. .count(元素)：统计某个元素出现的次数
    nums = [1, 2, 3, 2, 4, 2]
    print(nums.count(2))  # 输出：3

    6. .index(元素)：获取某个元素的第一次出现的位置
    print(nums.index(3))  # 输出：2

    7. .copy()：复制一个新列表
    new_fruits = fruits.copy()

    8. .clear()：清空列表
    fruits.clear()
    print(fruits)  # 输出：[]



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


















