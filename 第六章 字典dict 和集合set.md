# 第六章 字典dict 和集合set

## 字典dict

字典dict是一种表达“键值对”的数据结构，可以根据“键KEY”设置和获取对应的值“value”

语法 dict = {key1：value1, key2: value2}

举例： user = {"id":123,"name":"liming"}

```python
#创建一个空字典
data = {}
#创建一个人的信息字典
user = {"id":123,"name":"小明","age":20}
#创建一个多人信息的字典
users = {
    "小明":"男",
    "小花":"女",
    "小张":"男",
    "小白":"女"
}
```

### 访问字典中的值

dict[key] 可以获取对应的value，如果key不存在会报错keyerror

使用dict.get(key,default)可以获取对应的value，如果key不存在会返回none

```python
#创建一个人的信息字典
user = {"id":123,"name":"小明","age":20}
print(user["id"])
print(user["name"])
print(user["age"])
# 如卸载如果写 user["grade"]会报错说keyError:'grade'
# 如果写get就不会报错，也可以制定默认值
print(user.get("grade"))
print(user.get("grade",80))
```

### 字典dict：给字典添加键值对

使用dict[key] = value的形式，可以添加键值对

如果键不存在，则会新增这个键值对，如果键已经存在了，会覆盖这个value的值

```py
#创建多个个人信息的字典
grades = {"小明":80,"小花":99,"小张":77,"小白":85}
print(grades)

#如下两个，因为key不存在，会新增键值对
grades["小李"] = 90
grades["小花"] = 88
#如下一个，因为小张之前存在键，所以值会被修改
grades["小张"] = 79
print(grades)
```



### 字典dict练习题

定义一个字典

- 初始化3个人的信息，key是朋友的名字，value是她喜欢的水果
  - 例如：xiaoming：apple
- 添加2个人的键值对，即新的名字：喜欢的水果数据
- 根据人名，更新一个人喜欢的水果，例如从orange 改成apple
- 打印最新的的结果数据

```py
frinds = {
    "xiaoming":"apple",
    "xiaohuang":"pear",
    "xiaozhao":"banana"
}
frinds["xiaolei"] = "banana"
frinds["xiaoqiang"] = "watermelon"
print(frinds)
frinds["xiaolei"] = "apple"
print(frinds)
```

### 遍历字典：同时遍历键值对

有如下遍历字典键值对的方法：

- dict.items()以列表返回可遍历的(键，值)元祖数组，常常用于for遍历
- dict.key()以列表返回字典所有的键
- dict.value()以列表返回字典的所有的值

```py
#创建一个人的信息字典
user = {"id":123,"name":"小明","age":20}
#遍历键值对
for key,value in user.items():
    print(key,value)
```

### 只遍历键列表

```py
#创建多个人的成绩数据
grade = {"小明":88,"小花":99,"小张":77,"小白":85}
for name in grade.keys():
#可以只使用key，也可以用字典的方式获得value
    print(name,grade[name])
```

### 只遍历值列表

```py
#创建多个人的成绩数据
grades = {"小明":88,"小花":99,"小张":77,"小白":85}
for grade in grades.values():
    print(grade)
```

### 遍历字典练习题

新建 一个字典，包含朋友喜欢的水果数据

- 小明 apple
- 小花 orange
- 小张 banana
- 小白 pear

使用for循环，遍历字典，输出如下信息：

朋友 小明 最喜欢的水果是 apple

朋友 小花 最喜欢的水果是 orange

朋友 小张最喜欢的水果是banana

朋友小白最喜欢的水果是pear

```py
friend_fruits = {
    "小明":"apple",
    "小花":"orange",
    "小张":"banana",
    "小白":"pear",
}
for name,fruits in friend_fruits.items():
    print(f"朋友{name}最喜欢的水果是{fruits}")
```

### 字典嵌套：

#### 列表的元素是字典

数据的嵌套：将字典存储到列表中，或者字典的value是列表，或者字典的value是字典

```PY
#学生信息的字典列表，表达很多个学生信息
students = [
    {"id":101,"name":"xiaozhang","grade":88},
    {"id":102,"name":"xiaowang","grade":99},
    {"id":104,"name":"xiaoli","grade":77},
    {"id":105,"name":"xiaozhao","grade":86},
]
for student in students:
    id,name,grade = student["id"],student["name"],student["grade"]
    print(f"学号为{id}的姓名是{name},成绩是{grade}")
```

字典的vlue是列表

```py
#字典的value是列表，表达每个人列表类型信息
students = {
    "小张":["足球","篮球"],
    "xiaowang":["篮球","乒乓球"],
    "xiaoli":["篮球","棒球","台球"],
    "xiaozhao":["乒乓球","羽毛球"],
}
for student,like in students.items():
    print(f"学生{student}，爱好有这些{like}")
```

字典的value是字典

```python
#学生的信息字典的列表，表达很多个学生信息
students = {
    "xiaozhang":{"id":101,"grade":88},
    "xiaowang":{"id":102,"grade":99},
    "xiaoli":{"id":103,"grade":77},
    "xiaozhao":{"id":104,"grade":86}
}
for name,info in students.items():
    id,grade = info["id"],info["grade"]
    print(f"姓名为{name}，学号为{id},成绩是{grade}")
```

### 字典嵌套练习题

有如下字典

```py
#学生信息字典的列表，表达很多个学生信息
students = {
    "xiaozhang":{"id":101,"grade":88},
    "xiaowang":{"id":102,"grade":99},
    "xiaoli":{"id":103,"grade":77},
    "xiaozhao":{"id":104,"grade":86}
```

实现如下效果：

1. 将xiaoli的成绩从77分改成87分
2. 将所有grade放到一个列表里，叫做grades
3. 将grades降序排列后输出

```py
students = {
    "xiaozhang":{"id":101,"grade":88},
    "xiaowang":{"id":102,"grade":99},
    "xiaoli":{"id":103,"grade":77},
    "xiaozhao":{"id":104,"grade":86}
}
students["xiaoli"]["grade"] = 87
print(students["xiaoli"])

result = []
for grade in students.values():
    result.append(grade["grade"])
result.sort(reverse=True)
print(result)
```

