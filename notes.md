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

    4. 去除 空格/标点符号:
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

    10. 格式化字符串（f-string 全称formatted string）：用 f"{}" 来格式化字符串，它的优势在于能够直接在字符串内部嵌入表达式
    age = 25
    greeting = f"你好，{name}，今年 {age} 岁"  # f-string 格式化
    print(greeting)  # 输出: 你好，Cindy，今年 25 岁

    11. **正则表达式（Regular Expressions）**
    正则表达式是一个强大的字符串匹配工具，常用于文本的模式匹配、查找、替换和验证。
    
    基本语法：
    .：匹配任意单个字符（除了换行符）。
    ^：匹配字符串的开头。
    $：匹配字符串的结尾。
    []：匹配括号内的任意字符。
    *：匹配前面的元素零次或多次。
    +：匹配前面的元素一次或多次。
    ?：匹配前面的元素零次或一次。
    |：匹配左边或右边的表达式。
    \d：匹配一个数字。
    \w：匹配一个字母、数字或下划线。
    
    常见应用
    查找文本中的模式：
    import re
    text = "abc 123 def"
    pattern = r"\d+"  # 匹配一个或多个数字
    matches = re.findall(pattern, text)
    print(matches)  # 输出: ['123']
    替换文本中的匹配项：
    text = "My email is abc@example.com"
    pattern = r"\S+@\S+"  # 匹配邮箱地址
    replaced_text = re.sub(pattern, "REDACTED", text)
    print(replaced_text)  # 输出: My email is REDACTED
    验证字符串格式：
    email = "test@example.com"
    pattern = r"^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$"
    if re.match(pattern, email):
        print("Valid email!")
    else:
        print("Invalid email!")

**- 元组 Tuple**：一个不可变的、序列化的数据结构，通常用圆括号 () 表示。

    1. 创建元组：
    my_tuple = (1, 2, 3, 4)
    
    2. 访问元组中的元素：
    print(my_tuple[0])  # 输出：1
    
    3. 元组解包：
    a, b, c = my_tuple
    print(a, b, c)  # 输出：1 2 3
    
    4. 元组与列表的区别：
    元组是不可变的（immutable），而列表是可变的（mutable）。
    元组通常用于存储不需要修改的数据。

    5. 元组与字典的区别：
    元组：像一个“固定格式的容器”，注重顺序；
    my_tuple = (1, 2, 3)
    通过索引（位置）访问，如 my_tuple[0]
    字典：像一个“带标签的容器”，注重含义。
    my_dict = {"name": "Cindy", "age": 25}
    通过键访问，如 my_dict["name"]
    

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



**- 字典**：是一种无序的数据结构，它通过 键（key） 来映射 值（value），就像是一个电话簿，键是人名，值是电话号码。

    1. 创建字典
    person = {
    "name": "Cindy",
    "age": 25,
    "email": "cindy@example.com"
    }
    print(person)

    person 是字典，包含了三个键值对：name, age, email。字典的键（key）是不可重复的，值（value）可以是任何类型。

    2. 访问字典中的值
    print(person["name"])  # 输出: Cindy
    print(person["age"])   # 输出: 25

    3. 添加和修改值
    person["phone"] = "1234567890"  # 添加新的键值对
    person["age"] = 26  # 修改已有的键值对
    print(person)

    如果键已经存在，person["age"] = 26 会更新原来的值。
    如果键不存在，person["phone"] = "1234567890" 会新增一个键值对。

    4. 删除字典中的键值对
    del person["email"]  # 删除指定键的键值对
    print(person)

    5. 遍历字典
    for key, value in person.items():
        print(key, ":", value)
        
    person.items() 返回一个包含键值对的可迭代对象，for 循环可以用来遍历字典中的所有键值对。

    6. 判断键是否存在
    if "name" in person:
        print("Name exists:", person["name"])
    else:
        print("Name not found.")

    使用 in 来检查字典中是否包含某个键。

    7. 字典的合并
    在 Python 3.9 及以上版本中可以使用 | 运算符来合并两个字典。
    dict1 = {'a': 1, 'b': 2}
    dict2 = {'b': 3, 'c': 4}
    result = dict1 | dict2
    print(result)
    在这个例子中，dict1 和 dict2 中的键 b 会被合并，dict2 中的 b 值会覆盖 dict1 中的值。如果键是唯一的，则会直接合并。

    8. get 方法
    get() 方法可以通过键来获取字典中的值，但它会避免抛出异常，如果键不存在，则返回 None 或指定的默认值。示例：
    my_dict = {'name': 'Alice', 'age': 25}
    print(my_dict.get('name'))  # 输出 'Alice'
    print(my_dict.get('address', 'No Address'))  # 输出 'No Address' 因为 'address' 不存在

    9. setdefault 方法
    setdefault 方法不仅用于访问字典中的值，还可以在键不存在时为该键设定默认值。示例：
    my_dict = {'name': 'Alice', 'age': 25}
    print(my_dict.setdefault('address', 'Unknown'))  # 如果 'address' 不存在，则返回 'Unknown' 并插入 'address': 'Unknown'
    print(my_dict)

    10. 字典的排序
    字典本身是无序的，但你可以对字典的键或值进行排序。示例：
    my_dict = {'name': 'Alice', 'age': 25, 'city': 'New York'}
    sorted_dict_by_keys = dict(sorted(my_dict.items()))  # 按键排序
    sorted_dict_by_values = dict(sorted(my_dict.items(), key=lambda item: item[1]))  # 按值排序
    print(sorted_dict_by_keys)
    print(sorted_dict_by_values)

    11. 字典推导式
    字典推导式允许你以一种简洁的方式创建新的字典。示例：
    my_dict = {x: x**2 for x in range(5)}
    print(my_dict)
    这会创建一个字典，其中每个键是一个数字，值是该数字的平方。

### 6. 集合

集合（Set）是一个无序的、不可重复的元素集合，它支持数学上的集合运算，例如交集、并集、差集等。

**- 基本集合操作**：

    my_set = {1, 2, 3, 4, 5}
    print(my_set)

**- 集合的常见方法**

添加元素

    my_set.add(6)  # 向集合中添加一个元素
    print(my_set)  # {1, 2, 3, 4, 5, 6}

移除元素

    my_set.remove(6)  # 移除指定元素
    print(my_set)  # {1, 2, 3, 4, 5}

**- 集合的高级应用**

集合的高级应用主要包括数学运算：

1) 并集 union() 或 |

并集是两个集合的所有元素，去掉重复的部分。

    set1 = {1, 2, 3}
    set2 = {3, 4, 5}
    union_set = set1 | set2  # 使用 | 运算符
    print(union_set)  # {1, 2, 3, 4, 5}
   或union
   union_set = set1.union(set2)
   print(union_set)  # {1, 2, 3, 4, 5}

2) 交集 intersection() 或 &

交集是两个集合中共同的部分。

    intersection_set = set1 & set2  # 使用 & 运算符
    print(intersection_set)  # {3}
   或者
    intersection_set = set1.intersection(set2)
    print(intersection_set)  # {3}
    
3) 差集 difference() 或 -

差集是一个集合中有，另一个集合中没有的部分。

    difference_set = set1 - set2  # 使用 - 运算符
    print(difference_set)  # {1, 2}
    或者
    difference_set = set1.difference(set2)
    print(difference_set)  # {1, 2}

4) 对称差集 symmetric_difference() 或 ^

对称差集是两个集合中不重复的部分，类似于并集减去交集。

    symmetric_difference_set = set1 ^ set2  # 使用 ^ 运算符
    print(symmetric_difference_set)  # {1, 2, 4, 5}
    或者
    symmetric_difference_set = set1.symmetric_difference(set2)
    print(symmetric_difference_set)  # {1, 2, 4, 5}

5) 子集和超集

issubset(): 判断一个集合是否是另一个集合的子集。
issuperset(): 判断一个集合是否是另一个集合的超集。

    set1 = {1, 2}
    set2 = {1, 2, 3, 4, 5}

    print(set1.issubset(set2))  # True
    print(set2.issuperset(set1))  # True

**- 集合的常见用途**

1) 去重

集合本身不允许重复的元素，因此可以用它来快速去除重复项：

    my_list = [1, 2, 2, 3, 4, 4, 5]
    my_set = set(my_list)  # 转换为集合自动去重
    print(my_set)  # {1, 2, 3, 4, 5}

2) 集合运算

集合运算对于许多应用场景很有用，特别是在数据分析中，像计算两个数据集的交集、并集等，可以用集合运算快速完成。







### 7. 函数

**- 定义函数**：def 关键字

    def greet(name):
        print(f"Hello, {name}")
    greet("Cindy")

### 8. 模块与导入

**- 使用 import 导入标准库或第三方库**

    import math
    print(math.sqrt(16))  # 输出 4.0

### 9. 异常处理

**- 使用 try/except 语句处理异常**

    try:
        x = 10 / 0
    except ZeroDivisionError:
        print("除数不能为零")

### 10. 列表推导式与字典推导式

**- 列表推导式**：快速生成列表

    squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]

**- 字典推导式**：是一种简洁的方式来创建字典。它类似于列表推导式，但用于字典的创建，允许你在一行代码中生成一个字典。

基本语法

    [expression for item in iterable if condition]

expression：对每个元素应用的操作，生成列表的元素。

item：从可迭代对象（如列表、元组等）中提取的元素。

iterable：可迭代对象（如列表、字符串、范围等）。

condition：可选的条件，如果满足条件则加入列表。

### 11. 文件操作

**- 打开文件并读取、写入**
Python 提供了内置的 open() 函数来打开文件，常用的文件操作包括：

    读取文件内容：read(), readline(), readlines()
    写入文件：write(), writelines()
    关闭文件：close()
    
常用的打开模式：

    file = open('file.txt', 'w')
    
    'r'：只读模式（默认模式）。
    'w'：写模式（如果文件存在会覆盖，如果不存在会创建新文件）。
    'a'：追加模式（在文件末尾添加内容）。
    'rb' 或 'wb'：以二进制模式读写文件。

写入文件（write）：

    file = open('file.txt', 'w')  # 打开文件（写入模式）
    file.write("Hello, world!")  # 向文件中写入字符串
    file.close()  # 关闭文件

读取文件（read）：会读取整个文件的内容，返回一个字符串。

    file = open('file.txt', 'r')  # 打开文件（读模式）
    content = file.read()  # 读取文件中的所有内容
    print(content)  # 输出文件内容
    file.close()  # 关闭文件

逐行读取文件（readline）如果文件非常大，可以逐行读取文件，而不是一次性读取所有内容：

    file = open('file.txt', 'r')
    line = file.readline()  # 读取文件的第一行
    print(line)
    file.close()

读取所有行（readlines）

    file = open('file.txt', 'r')
    lines = file.readlines()  # 读取所有行并返回一个列表
    print(lines)  # 输出所有行
    file.close()

自动关闭文件（with 语句）

    with open('file.txt', 'w') as file:
        file.write("Hello, world!")  # 文件操作后，文件会自动关闭

    
### 12. 常用标准库

**- datetime**：日期和时间操作

    import datetime
    now = datetime.datetime.now()
    print(now)

**- os**：操作系统相关功能

    import os
    print(os.getcwd())  # 获取当前工作目录


















