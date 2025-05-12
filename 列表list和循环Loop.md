## For循环



```python
fruits = ["apple","pear","orange"]
for fruit in fruits:
	print(fruit)
```

for name in list,这个name变量名字可以随意取

for一行的结尾有一个冒号

for下方如果要被循环控制，需要体检加4个空格，代表被for控制

Range函数

range(起始位置数字包含这个数字，结束为止的数字不包含这个数字，补仓每次间隔多少个数字)

range(start,stop,setp)

举例：

rang(1,5)  生成1,2,3,4，包含1不包含5

range(1,10,2) 生成1,3,5,7,9，从起始位置开始间隔2包含结尾的10

range(5) 生产0,1,2,3,4 意思是0~5 ，不包含5，共5个值

## 列表简单统计计算

### 列表统计函数：

max(list):返回最大值

min(list):返回最小值

sum(list):反馈列表的值的加和

len(list):返回列表的元素的个数

```python
data = [5,4,3,6,7,8]
print(f"最大值是{max(data)}")
print(f"最小值是{min(data)}")
print(f"和是{sum(data)}")
print(f"长度是{len(data)}")
print(f"平均数是{sum(data)/len(data)}")

```

## 列表循环练习题

计算1-100的数字的平方和：

1. ​	使用rage生成一个列表，包含1-100
2. ​	计算这些数字的平方和(举例：3的平方，就是3*3)
3. ​	输出最终计算结果

```python
numbers = list(range(1,101))
b = 0
for i in numbers:
	b += i*i
	
print(b)

```

列表推导式

使用for循环，快速使用现在的序列或者列表生成一个新的列表

```python
# 生成1-100所有数字的平方列表
numbers = [i * i for i in range(1,101)]
# 生成1-100 的所有偶数平方列表
numbers = [i * i for i in range(1,101) if i % 2 ==0]


```

![列表推导式](https://github.com/huaerlxl/PythonLearning/blob/main/imgs/列表推导式.png)

## 列表的切片

切片是指从列表中获取子列表

number[start:stop:step]

> start: 起始位置数字包含这个数字
>
> stop：结束为止，不包含这个数字
>
> step：步长，每次间隔多少数字
>
> 列表的切片，会返回一个新列表，不影响原来的列表

```python
numbers = list(range(1,11))
#从2的位置开始，到位置5结束，不包含5
print("2:5",numbers[2:5])
#从0开始，到5位置结束，不包含5
print("0:5",numbers[:5])
#从2开始，到结束
print("2:",numbers[2:])
#包含所有元素
print(":",numbers[:])
#从3开始，到9，步长为2
print("3:9:2",numbers[3:9:2])
```

列表循环练习题

怎样计算成绩的前三名

1. 新建一个列表grades，里面的值分别是[77,88,73,99,82,89,95,86,93]
2. 将列表降序排列
3. 输出成绩的最高分，最低分，平均分
4. 提取grades最高分前三名

```python
grades = [77,88,73,99,82,89,95,86,93]
grades.sort(reverse=True)
print(f"最高分：{max(grades)}")
print(f"最低分：{min(grades)}")
print(f"平均分{sum(grades) / len(grades)}")
print("前三名的成绩是")
for grade in grades[:3]:
    print(grade)
print(f"第一名{grades[0]}")
print(f"第二名{grades[1]}")
print(f"第三名{grades[2]}")
```

## 元组Tuple

- 元组是一种类似列表的数据序列类型

- 不可变、不可添加、删除、更新元素

- 支持索引、切片、遍历

- 用两个小括号包括，元素之间用逗号分隔

  

创建方式：

```python
student = (101，'xiaoming',20)
#元祖的括号可以省略
tup = "a","b","c"


```

创建空元祖和单个元素元祖的方式：

```
tup = ()
tup = (50,)
```

索引和切片

```
#得到单个元素
tup[idx]
#得到切片，类型也是元祖
tup[start,stop,step]
```

| 区别     | 元祖tuple      | 列表list       | 说明                                                         |
| -------- | -------------- | -------------- | ------------------------------------------------------------ |
| 内容区别 | 异质、不同类型 | 同质、相同类型 | 用一个元祖表示一个人的信息people(id,name,age); 用list来表示很多人的信息列表[p1,p2,p3] |
| 使用区别 | 更多用于拆包   | 循环遍历       | 元祖pack和unpack： id,name,age=1001,'xiaoming',20 ; 列表循环遍历： for s in students : print(s) |
| 是否可变 | 不可           | 可变           | 元祖的不可变性质： 代码更安全，如果是一个元祖就放心使用，不怕被更改；有些场景需要不可变的列表，比如字典的key要求不可变对象 |

## 元组练习题

- 新建一个元组，叫student，信息有：学号，姓名，年龄，身高，内容有(1001，'xiaoming',20,176)

- 使用for循环，遍历student的各个元素

- 使用变量拆包的方式，得到学号、姓名、年龄、身高多个变量，打印结果

- 修改姓名元素，变成daming，会发现报错不允许修改

- 只能整体修改student，例如设置新的学生信息(1002,'xiaobai',21,173)

  

```python
student = (1001,'xiaoming',20,176)
print(student,type(student))

for x in student:
    print(x)

学号,姓名,年龄,身高 = student
print("学号:",学号)
print("姓名:",姓名)
print("年龄:",年龄)
print("身高:",身高)

student = (1002,'xiaobai',21,173)
```

