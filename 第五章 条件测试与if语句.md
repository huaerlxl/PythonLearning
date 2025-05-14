# 条件测试与if语句

[toc]



if 开头，后面是一个“条件测试，后面是冒号，类似for语句，下面可以通过锁紧多行代码，被if控制else是”否则“的意思，如果if不通过，执行else语句

if条件：执行A else 执行B

如果条件通过执行A，否则执行B

```python
#学生成绩
grades = [66,55,75,80,43,90]
for grade in grades:
    print("你的成绩是：", grade)
    if grade >= 60:
        print("恭喜你，通过了考试")
    else:
        print("很遗憾你成绩不及格")
        print("请继续努力")
```

> grade in grades 和 grade >=60
>
> 这个语句叫做条件测试表达式，返回true和False，表达真和假

## 更多的条件测试

这些条件测试，都返回True 或者False，放在if语句中用于判断



#字符串和数字比较运算符

```python
a == b   #等于
a != b	#不等于
a > b	#大于
a >= b	#大于等于
a < b	#小于
a <= b	#小于等于

```

注意：

```python
a = 3	#意思是把3这个数字，赋值给a变量
a == 3	#则是一个判断测试，a的值等于3吗
```

```py
#成员运算符
data = [2,3,4,5]
3 in data	#包含
3 not in data	#不包含
```

```py
#逻辑运算符
a == b and c == d	#并且
a == b or c == d	#或者
not a == b			#非

#也可以加括号区分
(a == b) and (c == d)
```



字符串的等于、不等于判断

```py
value = 'apple'
print(value == "banana")
print(value == "apple")
print(value == "pear")

#输出结果
False
True
False

value = 'apple'
print(value != "banana")
print(value != "apple")
print(value != "pear")
#输出结果
True
False
True
```

数字的等于、不等于、大于、大于等于、小于、小于等于

```py
a,b = 3,7
print("a == b",a == b)
print("a != b",a != b)
print("a > b",a > b)
print("a < b",a < b)
print("a <= b",a <= b)
#输出结果
a == b False
a != b True
a > b False
a < b True
a <= b True
```

使用and和or，可以组合多个条件做测试



or要求，任何一个条件满足，整体就是True，or的条件可以很多个，可以加括号区分逻辑

```py
a == 3 and "pear" not in fruits and value == "ok"	# and要求，所有条件都满足，整体才是True，and的条件可以很多个，可以加括号区分逻辑
a == 3 or "pear" not in fruits or value == "ok"		#or要求，任何一个条件满足，整体就是True，or的条件可以很多个，可以加括号区分逻辑#
```

and 和 or可以混用，and的优先级更高(限制性and再执行or)

![条件测试](https://github.com/huaerlxl/PythonLearning/blob/main/imgs/条件测试.png)

## 条件测试练习题

给定一个成绩grade，例如你设定一个值，例如70分

用print输出如下条件

- 是否及格，大于60分则及格
- 是否不及格，小于60分则不及格
- 是否满分，等于100则满分
- 是否不是满分，不等于100分，就不是满分
- 判断属于(优秀，中等，良好)中的中等成绩，判断是否大于70分并且小于90分
- 判断成绩数字是否顺口，成绩等于66，或者等于88，或等于99
- 判断成绩及格并且是否是0结尾，判断成绩大于60，并且为60/70/80/90/100中的一个

```py
grade = 70
shunkou = [66,88,99]

print("是否不及格:",grade <= 60)
print("是否及格:",grade >= 60)
print("否满分:", grade == 100)
print("是否不是满分:", grade != 100)
print("是否中等成绩:",90>grade>70)
print("判断成绩数字是否顺口:",grade in shunkou)
print("判断成绩及格并且是否是0结尾:", grade % 10 == 0)
```



## if判断语句语法

最简单的判断，只有if判断

```py
grade = 70
if grade >= 60:
	print("你的成绩及格了")
```

if 配合 else，表达如果、否则的含义

```py
grade = 70
if grade >= 60:
    print("你的成绩及格了")
else:
    print("很遗憾，你没通过考试")
```

If 配合多个elif和else，表达很多个条件

```py
grade = 70
if grade < 60:
    print("不及格")
elif grade < 80:
    print("良好")
elif grade < 90:
    print("中等")
else:
    print("游戏")
```

> 注意：如果if.. elif..else 的写法，只会有一个条件会被执行

## if判断年龄练习题

给顶一个年龄age,例如数字20

做如下判断：

- 如果小于13岁，输出“小孩”
- 如果大于等于13，并且小于18，打印“青少年”
- 如果大于等于18，并且小于65，打印“成年人”
- 如果大于65，打印“老年人”

```py
age = input("请输入年龄：")
age = int(age)
if age < 13:
    print("小孩")
elif  18 > age >= 13:
    print("青少年")
elif 65 > age > 18:
    print("成年人")
else:
    print("老年人")
```

## if 判断和列表的配合

在for循环中，增加判断，可以实现特殊的处理

```py
numbers = range(11)
for number in numbers:
    if number % 2 == 0:
        print("发现一个偶数：",number)
    else:
        print("发现一个奇数：",number)
print("数据读取完毕")
```

有时候需要先判断列表是否为空，如果不为空才遍历，如果为空则直接提示信息

```python
fruits = ["apple","pear","orange"]
if fruits:
    for fruit in fruits:
        print(f"接下来吃这个水果：{fruit}")
else:
    print("没有水果可吃")
```

> 如果列表不为空，那么if判断可以直接通过

对多个用户来说，挨个判断是否已经被注册过

```py
current_users = ["小明","小王","小李","小董"]
new_users = ["小张","小李","小黑"]
for new_user in new_users:
    if new_user in current_users:
        print(f"{new_user},该用户名已被注册")
    else:
        print(f"{new_user},该用户名可用")
```

## if 判断与循环练习题

两数之和

- 输入一个数字列表 numbers:[2,3,5,8,7,4,1,6]
- 输入一个数字目标，例如：8
- 用代码查找，那些数字加和等于 8， 例如2和6,3和5,7和1；
  - 注意：如果5和3已经出现一对了，不要在出现3和5的，这是一回事
- 提示用两次for循环这个列表即可实现

```py
numbers = [2,3,5,8,7,4,1,6]
target = 8
result = []
for number1 in numbers:
    for number2 in numbers:
        if number1+number2 == target and (number1,number2) not in result:
            print(f"{number1}+{number2} = 8")
            result.append((number1,number2))
            result.append((number2, number1))
```

