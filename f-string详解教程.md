# 🎯 专章：Python print()函数中的f-string用法详解

欢迎来到f-string的神奇世界！本章将详细介绍Python中最强大、最简洁的字符串格式化方法。

---

## 📚 第一部分：什么是f-string？

在Python中，**f-string**（格式化字符串字面量）是一种便捷的字符串格式化方法。它以字母 `f` 或 `F` 作为前缀，将表达式直接嵌入到字符串中，表达式会在运行时计算并替换成结果。

### 💡 基本示例

```python
name = "小明"
age = 10
print(f"大家好，我叫{name}，今年{age}岁。")
# 输出：大家好，我叫小明，今年10岁。
```

---

## 📚 第二部分：f-string的基本语法

### ✅ 语法规则：
- 字符串前加 `f` 或 `F` 前缀
- 花括号 `{}` 中可以嵌入变量、表达式

### 💡 基本语法示例

```python
score = 98
print(f"你的分数是{score}分！")

# 可以使用不同类型的引号
student_name = "小红"
print(f'学生姓名：{student_name}')  # 单引号
print(f"学生姓名：{student_name}")  # 双引号
print(f"""学生姓名：{student_name}""")  # 三引号
```

### 📌 注意事项：
- `f` 或 `F` 必须紧贴在引号前面
- 花括号内的变量必须已经定义
- 可以使用单引号、双引号或三引号

---

## 📚 第三部分：f-string中表达式的应用

f-string不仅能插入变量，也可直接插入计算表达式。这是它最强大的功能之一！

### 💡 数学运算示例

```python
x = 5
y = 6
print(f"x = {x}, y = {y}")
print(f"x + y = {x + y}")
print(f"x * y = {x * y}")
print(f"x ** y = {x ** y}")
# 输出：x = 5, y = 6
# 输出：x + y = 11
# 输出：x * y = 30
# 输出：x ** y = 15625
```

### 💡 字符串操作示例

```python
first_name = "张"
last_name = "三"
full_name = first_name + last_name

print(f"姓：{first_name}")
print(f"名：{last_name}")
print(f"全名：{first_name + last_name}")
print(f"全名长度：{len(first_name + last_name)}个字")
print(f"姓名大写：{full_name.upper()}")
```

### 💡 函数调用示例

```python
numbers = [85, 92, 78, 96, 88]
print(f"成绩单：{numbers}")
print(f"最高分：{max(numbers)}")
print(f"最低分：{min(numbers)}")
print(f"总分：{sum(numbers)}")
print(f"平均分：{sum(numbers)/len(numbers):.1f}")
```

---

## 📚 第四部分：格式化输出

可以用冒号 `:` 在花括号内指定格式，例如保留小数点后两位。

### 💡 小数位数控制示例

```python
pi = 3.1415926535897932
print(f"原始π值：{pi}")
print(f"保留2位小数：{pi:.2f}")
print(f"保留4位小数：{pi:.4f}")
print(f"保留0位小数：{pi:.0f}")
# 输出：圆周率约为3.14
```

### 💡 数字格式化示例

```python
big_number = 1234567890
print(f"原始数字：{big_number}")
print(f"添加千位分隔符：{big_number:,}")
print(f"科学计数法：{big_number:.2e}")
```

### 💡 百分比格式示例

```python
ratio = 0.8567
print(f"原始比率：{ratio}")
print(f"百分比格式：{ratio:.1%}")
print(f"百分比格式（2位小数）：{ratio:.2%}")
```

### 💡 字符串对齐示例

```python
items = ["苹果", "香蕉", "橙子"]
prices = [3.5, 2.8, 4.2]
print("商品价格表：")
for item, price in zip(items, prices):
    print(f"{item:^6} | {price:>6.1f}元")
```

### 💡 进制转换示例

```python
number = 255
print(f"十进制：{number}")
print(f"二进制：{number:b}")
print(f"八进制：{number:o}")
print(f"十六进制：{number:x}")
print(f"十六进制（大写）：{number:X}")
```

---

## 📚 第五部分：f-string常见错误示例

### ⚠️ 常见错误类型及解决方法：

#### ❌ 错误1：变量名拼写错误

```python
name = "小明"
# 正确写法：
print(f"我是{name}")

# 错误写法（会报错）：
# print(f"我是{namee}")  # NameError: name 'namee' is not defined
```

#### ❌ 错误2：花括号未闭合

```python
score = 100
# 正确写法：
print(f"分数是{score}分")

# 错误写法（会报错）：
# print(f"分数是{score分")  # SyntaxError: f-string: unterminated string
```

#### ❌ 错误3：忘记f前缀

```python
age = 15
# 正确写法：
print(f"我今年{age}岁")

# 错误写法（不会报错，但输出不正确）：
print("我今年{age}岁")  # 这会直接输出 {age} 而不是 15
```

#### ❌ 错误4：在花括号内使用相同类型的引号

```python
message = "你好"
# 正确写法：
print(f'消息内容："{message}"')
# 或者：
print(f"消息内容：'{message}'")

# 错误写法（会报错）：
# print(f"消息内容:"{message}"")  # SyntaxError
```

#### ❌ 错误5：变量未定义就使用

```python
# 错误写法（会报错）：
# print(f"未定义的变量：{undefined_var}")  # NameError

# 正确做法：先定义变量
undefined_var = "现在定义了"
print(f"已定义的变量：{undefined_var}")
```

---

## 📚 第六部分：练习题

现在到了实践的时间！完成下面的练习题来检验你的学习成果。

### 🎯 练习题1：用f-string输出自己的姓名和年龄
**要求**：定义name和age变量，用f-string输出完整句子

```python
# 示例答案：
student_name = "李小华"
student_age = 12
print(f"大家好，我叫{student_name}，今年{student_age}岁了。")
```

### 🎯 练习题2：用f-string展示两个数字的和
**要求**：定义两个数字变量，计算并用f-string显示计算过程和结果

```python
# 示例答案：
num1 = 25
num2 = 17
result = num1 + num2
print(f"{num1} + {num2} = {result}")
print(f"两个数字 {num1} 和 {num2} 的和是 {num1 + num2}")
```

### 🎯 练习题3：用f-string输出保留两位小数的成绩
**要求**：定义一个包含小数的成绩变量，用f-string格式化输出

```python
# 示例答案：
math_score = 87.6789
chinese_score = 92.3456
english_score = 89.1234
print(f"数学成绩：{math_score:.2f}分")
print(f"语文成绩：{chinese_score:.2f}分")
print(f"英语成绩：{english_score:.2f}分")
average_score = (math_score + chinese_score + english_score) / 3
print(f"平均成绩：{average_score:.2f}分")
```

---

## 🌟 综合实践示例：学生成绩报告卡

让我们用所学的知识创建一个完整的学生成绩报告卡！

```python
# 学生信息
student_info = {
    "姓名": "王小明",
    "班级": "三年级一班",
    "学号": "20240001"
}

# 各科成绩
subjects = {
    "语文": 88.5,
    "数学": 95.0,
    "英语": 92.5,
    "科学": 87.0,
    "音乐": 90.0
}

# 生成报告卡
print("=" * 50)
print(f"📋 学生成绩报告卡")
print(f"姓名：{student_info['姓名']:^10}")
print(f"班级：{student_info['班级']}")
print(f"学号：{student_info['学号']}")
print("-" * 30)

total_score = 0
for subject, score in subjects.items():
    print(f"{subject:^6} | {score:>6.1f}分")
    total_score += score

average = total_score / len(subjects)
print("-" * 30)
print(f"总分：{total_score:.1f}分")
print(f"平均分：{average:.2f}分")

# 等级评定
if average >= 90:
    grade = "优秀"
elif average >= 80:
    grade = "良好"
elif average >= 70:
    grade = "中等"
else:
    grade = "需要努力"

print(f"综合评价：{grade}")
print("=" * 50)
```

---

## 🎉 学习总结

**恭喜你！通过本章学习，你已经掌握了f-string的核心用法！**

### 💪 现在你可以：
- 灵活使用f-string进行字符串格式化
- 大大提升代码的可读性和编程效率
- 避免常见的f-string错误
- 使用各种格式化选项美化输出

### 📝 学习要点回顾：
✅ **f-string语法简洁明了** - 只需在字符串前加f  
✅ **支持变量和表达式嵌入** - 花括号内可以放任何Python表达式  
✅ **提供丰富的格式化选项** - 小数位数、对齐、进制转换等  
✅ **错误提示清晰** - 便于调试和学习  
✅ **性能优秀** - Python推荐使用的格式化方法  

### 🚀 继续学习建议：
通过本章学习，学生将能灵活使用f-string进行字符串格式化，提升代码的可读性和编程效率。继续努力学习Python，你会越来越厉害的！

---

**记住：f-string是现代Python中最推荐的字符串格式化方法，多练习，你会爱上它的简洁和强大！** 💪✨