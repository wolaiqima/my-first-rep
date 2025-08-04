# Python 学习笔记汇总：2025-08-03 至 2025-08-04

---

## 📆 2025-08-03：Python 基础语法学习进度

你学习了 Python 的以下基础语法：

### ✅ 1. 数据类型和变量
- 掌握了整数、浮点数、字符串、布尔值、None
- 了解了变量命名、动态类型

### ✅ 2. 字符串和编码
- 理解了 Unicode 与 UTF-8
- 掌握了字符串的基本操作与转义字符

### ✅ 3. list 和 tuple
- list 可变、tuple 不可变
- 学习了索引、切片、嵌套等操作

### ✅ 4. 条件判断
- 掌握了 `if` / `elif` / `else` 结构
- 理解了条件表达式的写法

### ✅ 5. 模式匹配（match-case）
- 学习了 Python 3.10+ 中新增的 `match` 模式匹配语法
- 熟悉了 `case _` 通配符与结构模式

### ✅ 6. 循环（学习记录待补充）
- 已学习 for 和 while 循环语法
- 后续将撰写相关练习与总结笔记

### ✅ 7. 使用 dict 和 set（学习记录待补充）
- 已掌握基本的 dict 创建、查找、添加、删除等操作
- set 的去重功能已了解，笔记待完善

---

## 📆 2025-08-04：函数定义、返回值、解包与测试

你学习了函数调用的整个流程，并理解了 Python 中“返回多个值”其实是返回一个 tuple。

### ✅ 1. 函数调用与参数传递

```python
def move(x, y, step, angle=0):
    ...
```

调用方式：

```python
move(100, 100, 60, math.pi / 6)
```

---

### ✅ 2. 返回值其实是 tuple（元组）

```python
return x1, x2  # 实际等价于 return (x1, x2)
```

解包方式：

```python
a, b = quadratic(1, 3, -4)
```

或者：

```python
result = quadratic(1, 3, -4)
print(result[0], result[1])
```

---

### ✅ 3. move 函数示例

```python
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny

x, y = move(100, 100, 60, math.pi / 6)
print(x, y)  # 输出: 151.96..., 70.0
```

---

### ✅ 4. 一元二次方程函数 quadratic(a, b, c)

数学公式：

\[
x = \frac{{-b \pm \sqrt{{b^2 - 4ac}}}}{{2a}}
\]

Python 实现：

```python
import math

def quadratic(a, b, c):
    delta = b ** 2 - 4 * a * c
    x1 = (-b + math.sqrt(delta)) / (2 * a)
    x2 = (-b - math.sqrt(delta)) / (2 * a)
    return x1, x2
```

---

### ✅ 5. 测试代码示例

```python
print('quadratic(2, 3, 1) =', quadratic(2, 3, 1))
print('quadratic(1, 3, -4) =', quadratic(1, 3, -4))

if quadratic(2, 3, 1) != (-0.5, -1.0):
    print('测试失败')
elif quadratic(1, 3, -4) != (1.0, -4.0):
    print('测试失败')
else:
    print('测试成功')
```

---

## 📌 总结

- 函数是组织代码的基本单位。
- Python 函数返回一个值，可以是元组（同时解包多个变量）。
- 可通过 `math` 模块进行数学计算。
- 测试函数是否正确，可以直接比较返回结果。

