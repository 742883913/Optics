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