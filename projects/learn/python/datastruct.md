# 数据结构

### 字符串

命名规则，字符串的增删

### 序列

序列的操作:

```python
# 成员操作
in/ not in

# 拼接操作
'abc' + '123'
  'abc123'

# 重复操作
'abc'*2
  'abcabc'

# 切片操作
'abcdefg'[0:2]
  'ab'
```

### 元组

元组和列表的区别为，元组里的元素不能改变。

### 循环语句和条件语句

```python
for i in xxx:
  print(i)

while True:
  if xxx:
    break
```

### 字典

映射类型: 字典  
字典包含 哈希值 和 指向的对象

```python
{"哈希值": "对象"}
e.g. {'length': 120, 'width': 120}
```

#### 列表推导式和字典推导式

```python
# 列表
# 1 到 11 所有偶数的列表
[i for i range(1, 11) if(i%2) == 0]

# 字典
{key:value for i in xxxx}
```

### 文件的内建函数

```python
open()
  open('filename', encoding="编码1格式")
  open('filename', 'w')
read()
readline()
seek()
write()
cloe()
```

#### 文件常用操作

```python
seek()
# 第一个为偏移量, 第二个参数为偏移位置(0: 默认, 文件开头; 1: 当前位置; 2: 文件末尾)

tell()
# 显示指针当前位置

readlines()
# 对文件 逐行读取
```
