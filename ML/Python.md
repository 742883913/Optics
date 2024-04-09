


<div align="center"><img src="./cover1.png" width="800"></div>


# 初级阶段学习


### 数据类型

名称|类型
---|---
string|字符串
int|整数
float|浮点数

> 可以直接使用Type来查看数据类型

        type(数据)

### 数据类型转换

语句|类型
---|---
int(x)|将x转换为整数
float(x)|将x转换为浮点数
str(x)|将x转换为字符串

> 并不是所有的字符串都能转换成数字

### 标识符

1. 标识符只能带有数字、字母、下划线，其中数字不能放在开头。
2. 标识符不能使用关键字

### 运算符

符号|输出
---|---
//|除取整
%|除取余
**|次方

复合赋值如：
   
        c+=a为c=c+a

### 字符串格式化与拼接

1. 可以直接使用+来拼接，注意仅能拼接字符串。
2. 使用%s将内容变为字符串类型放入(d整数类型,f浮点数类型)，%的组合来拼接，这种方法可以拼接字符串与数字

                name = 'Wangmusi'
                salary = 100000
                print(("His name is %s,his salary is %d") %(name,salary))


3. 快速的格式化采用以下方法
       
                name = 'Wang'
                deposit = 100
                print(f"He is {name}. He has {deposit}")
                He is Wang. He has 100

这个方法不限精度，不限数据类型。
> 常用m.n来控制精度，m表示数据宽度，n表示小数点后位数。如：

                print(%5.2f %11.323)
                 11.32

### 表达式的格式化

表达式：一条具有明确运行结果的代码语句。
表达式可以直接用在格式化过程中，如以下括号内的就是表达式

                print(f"1*1 等于 {1*1}")
                1*1 等于 1

这种写法可以简化变量。

练习：

                company = 'Wang'
                stock_price = 10
                stock_price_daily_growth = 0.01
                days = 7
                price = stock_price*(stock_price_daily_growth+1)**days
                print(f"公司名称：{company}",f"公司目前股价 {stock_price}")
                print(("每日增长系数为：%.2f ;经过 %d 天后股价为 %.3f") %(stock_price_daily_growth,days,price))

                公司名称：Wang 公司目前股价 10
                每日增长系数为：0.01 ;经过 7 天后股价为 10.721  


### 数据输入
input 语句不管你输入的是什么都看作是字符串
> input（）括号内可以放入提示作用的字符串

                admin = input("你的银行账号是")
                admin = int(admin)
                num = input("余额为")
                num = float(num)
                print("你%d账号内的余额为%.2f" %(admin,num))
                你的银行账号是 123
                余额为 222
                你123账号内的余额为222.00


### 布尔类型和比较运算符

  <div align="center"><img src="./Ppic/p1.png" width="400"></div>

### 逻辑判断语句
1. if else 组合
        
        age = input("你的年龄")
        age = int(age)
        if age >= 18:
                print("你已经%d岁了，可以玩点花的了" %age)
        else:
                print("你还小，好好学习。")

        你的年龄 20
        你已经20岁了，可以玩点花的了

2. if elif else 组合

> 注意，判断语句之间是互斥的并且是按顺序执行的，满足一条语句后下面的语句就不会再执行

        age = int(input("输入答案"))

        if  int(input("输入你的答案")) == age:
                print("猜对了")
        elif int(input("再次输入你的答案")) == age:
                print("你终于猜对了")
        else:
                print("给你机会你也不中用啊！")


        输入答案 5
        输入你的答案 6
        再次输入你的答案 5
        你终于猜对了


### 循环语句

1. while循环
        
        i = 0
        while i<100:
                print("我爱你")
                i+=1

例题：

        import random
        num = random.randint(1,100)
        i = 1
        num_guess = int(input("输入猜的值"))
        while num_guess != num:
                if num_guess > num:
                        print("大了")
                else:
                        print("小了")
                num_guess = int(input("再次输入猜的值"))
                i += 1
        print(num_guess,i)

<div align="center"><img src="./Ppic/p2.png" width="400"></div>

> end='':print(hello,end='')即可达到输出不换行，
> \t可替代空格对齐单词，如pring("hello\tworld")；\n可换行

2. for循环
   1. 该循环无法控制循环条件
        
                for 临时变量 in 待处理数据集
                        开始循环
        
   2. 可以通过range生成序列

                range(num) 从0开始
                range(num1,num2) 从num1开始不包含num2
                range(num1,num2,step) 从num1开始不包含num2,步长为step

   3. for 中的变量只能在 for 中使用，如果想要在for外调用，可以在for 前面先定义变量。

3. continue 和 break

continue : 结束本次循环，直接进行下次循环。且只能影响内层循环。

break : 直接结束循环。同样只对内层循环生效。

### 函数

1. 函数的定义

   1. 参数不需要可以省略
   2. 返回值不需要可以省略

   
                def 函数名(输入参数):
                        函数体
                        return 返回值

2. 函数返回值none类型
   
   1. 没定义返回值的，都会自动返回none，类型为type_none
   2. 在if语句中，none就等同于false

3. 作用域：函数体内的局部变量只会在函数体内生效，如果要在函数体内修改全局变量，则可以使用global关键字
        
        num = 100
        def test():
                global num
                num = 200
                num = 2000

### 数据容器

数据容器：是一种可以存储多个元素的数据类型，共有列表(list)、元组(tuple)、字符串(str)、集合(set)、字典(dict)五种。

#### 列表

**定义方法**

        [1,2,3,4]
        a = [1,2,3,4]
        a = list()
        a = []

> 列表内可以存列表

**列表的下表索引取出元素**
下表从零开始，可以通过以下代码取出列表元素：

        name = [0,1,2,3,[0,1,2]]
        print(name[0])
        print(name[4][0])

**列表功能调用**

1. 列表.index(元素)：查下标
2. 列表[下标] = 值：修改下标对应的值
3. 列表.insert(下标，插入的元素)：插入元素
4. 列表.append(元素)：追加元素至胃尾部
5. 列表.extend(其他数据容器)：将数据容器添加到列表尾部
6. del 列表[下标]：删除元素
7. 列表.pop(下标)：将元素从列表中取出，可以返回值
8. 列表.remove(元素)：删除指定元素
9. 列表.clear():清空列表
10. 列表.count(元素)：统计列表中同一元素的数量
11. len(列表)：查看列表有多少元素

**列表的循环和遍历**

将列表中的内容依次取出，叫做遍历或迭代。

1. while

        index = 0
        while index < len(列表):
                element = 列表[index]
                print("元素内容为：{element}")
                index += 1
        
2. for 

        for index in 列表:
                print(f"元素内容为{index}")

#### 元组

元组同列表相似，但一旦完成封装就不可再篡改。但是如果元组内嵌套list，则可以修改list内的内容。

**元组的定义**

        x = (1,2,3,4)
        x = tuple()
        x = ()

> 当定义但元素元组时，得在元素后加个逗号，否则不是元组类型。

**元组数据的取出**

        num = 元组[][]

**元组的调用**

仅有index，count，len三种。

        x = (1,2,[4,5,6])
        x[2].remove(6)
        print(x)

#### 字符串

字符串也是一种容器，且也是不可修改的容器。

1. 字符串.replace(字符串1，字符串2)：将字符串中的1替换为2，并得到一个新的字符串
2. 字符串.split(字符串)：将字符串按输入内容分割，并输出一个列表。