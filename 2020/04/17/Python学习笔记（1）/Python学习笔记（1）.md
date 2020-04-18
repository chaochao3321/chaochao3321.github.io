# 1.基本数据类型
```
a = 123
b = 456.789
c = 1 + 2j
d = 'Hello World'
e = True
print(type(a))
print(type(b))
print(type(c))
print(type(d))
print(type(e))
```
# 2.输入输出
## (1).使用input()函数获取键盘输入(字符串)
## (2).使用int()函数将输入的字符串转换成整数
## (3).使用print()函数输出带占位符的字符串

```
import sys

a = int(input('a = '))
b = int(input('b = '))
print('%d + %d = %d' % (a, b, a + b))
print('%d - %d = %d' % (a, b, a - b))
print('%d * %d = %d' % (a, b, a * b))
print('%d / %d = %f' % (a, b, a / b))
print('%d // %d = %d' % (a, b, a // b))
print('%d %% %d = %d' % (a, b, a % b))
print('%d ** %d = %d' % (a, b, a ** b))
```

# 3.将华氏温度转换为摄氏温度

```
f = float(input('请输入华氏温度：'))
c = (f-32) / 1.8
# print('%.1f华氏度 = %.1f摄氏度' % (f, c))
print(f'{f:.1f}华氏温度 = {c:.1f}摄氏温度') # 注意单引号前面有个f

```

# 4.输入圆的半径计算圆的周长和面积

```
pi = 3.14
r = float(input('请输入半径：'))
zhouchang = 2 * pi * r
mianji = pi * r * r
print('圆的周长是%.2f' % zhouchang)
print('圆的半径是%.2f' % mianji)

```

# 5.判断年份是不是闰年

```
year = int(input('请输入年份：'))
	is_leap = year % 4 == 0 and year % 100 != 0 or year % 400 == 0
	print(is_leap)

```

# 6.用户身份验证

```
username = input('请输入用户名：')
password = input('请输入密码：')
if username == 'chen' and password == 'wscjy1337':
    print('用户身份验证成功！')
else:
    print('用户身份验证失败！')
```

# 7.分段函数求值

```
x = float(input('x = '))
if x > 1:
    y = 3 *x -5
elif x >= -1 and x <= 1:
    y = x + 2
else:
    y = 5 * x +3
print('f(%.2f) = %.2f' % (x,y))
```

# 8.英制单位英寸和公职单位厘米互换

```
value = float(input('请输入长度：'))
unit = input('请输入单位：')
if unit == 'in' or unit == '英寸':
    print('%f英寸 = %f厘米' % (value, value * 2.54))
elif unit == 'cm' or unit == '厘米':
    print('%f厘米 = %f英寸' % (value, value / 2.54))
else:
    print('输入单位无效！')
```

# 9.百分之成绩转换为等级制成绩

```
score = int(input('请输入百分制成绩：'))
if score >= 90:
    grade = 'A'
elif score >= 80 and score <90:
    grade = 'B'
elif score >= 70 and score <80:
    grade = 'C'
elif score >=60 and score <70:
    grade = 'D'
else:
    grade = 'E'
print('你的等级制成绩为：', grade)
```

# 10.输入三条边长，判断能否构成三角形，如果能则计算三角形的周长和面积

```
a = float(input('a = '))
b = float(input('b = '))
c = float(input('c = '))
if a + b > c and a + c > b and b + c >a:
    print('周长为：%f' % (a + b +c))
    p = (a + b +c) / 2                                  # 此为计算三角形面积的
    area = (p * (p - a) * (p - b) * (p - c)) ** 0.5     # 公式：海伦公式
    print('面积为：%f' % (area))
else:
    print('三条边不能构成三角形！')
```

# 11.利用for循环实现1到100求和

```
sum = 0
for x in range(101):
    sum += x
print(sum)
# 1到100的偶数求和
sum1 = 0
for x1 in range(0,101,2):
    sum1 += x1
print(sum1)
```

# 12.猜数字小游戏，猜数字游戏的规则是：计算机出一个1到100之间的随机数，玩家输入自己猜的数字，计算机给出对应的提示信息（大一点、小一点或猜对了），如果玩家猜中了数字，计算机提示用户一共猜了多少次，游戏结束，否则游戏继续。

```
import random

answer = random.randint(1,100)
counter = 0
while True:
    counter += 1
    number = int(input('请输入一个数字：'))
    if number < answer:
        print('大一点')
    elif number >answer:
        print('小一点')
    else:
        print('恭喜你猜对了！')
        break
print('你一共猜了%d次' % (counter))
if counter > 7:
    print('猜的次数似乎有点多哦！')
```

# 13.九九乘法表

```
for i in range(1,10):
    for j in range(1,i+1):
        print('%d*%d=%d' % (i, j, i*j), end = '\t')
    print()
```

# 14.输入一个正整数判断它是不是素数

```
from math import sqrt

num = int(input('请输入一个正整数: '))
end = int(sqrt(num))
is_prime = True
for x in range(2, end + 1):
    if num % x == 0:
        is_prime = False
        break
if is_prime and num != 1:
    print('%d是素数' % num)
else:
    print('%d不是素数' % num)
```

# 15.输入两个正整数计算它们的最大公约数和最小公倍数

```
x = int(input('x = '))
y = int(input('y = '))
# 如果x大于y就交换x和y的值
if x > y:
    # 通过下面的操作将y的值赋给x, 将x的值赋给y
    x, y = y, x
# 从两个数中较的数开始做递减的循环
for factor in range(x, 0, -1):
    if x % factor == 0 and y % factor == 0:
        print('%d和%d的最大公约数是%d' % (x, y, factor))
        print('%d和%d的最小公倍数是%d' % (x, y, x * y // factor))  # //是整除运算符
        break
```

# 16.打印三角形图案

```

row = int(input('请输入行数: '))
for i in range(row):
    for _ in range(i + 1):
        print('*', end='')
    print()


for i in range(row):
     for j in range(row):
         if j < row - i - 1:
             print(' ', end='')
         else:
             print('*', end='')
     print()

for i in range(row):
     for _ in range(row - i - 1):
         print(' ', end='')
     for _ in range(2 * i + 1):
         print('*', end='')
     print()
```

寻找水仙花数，说明：水仙花数也被称为超完全数字不变数、自恋数、自幂数、阿姆斯特朗数，它是一个3位数，该数字每个位上数字的立方之和正好等于它本身，例如：$1^3 + 5^3+ 3^3=153$。
"""
# for num in range(100,100000):
#     low = num % 10
#     mid = num // 10 % 10
#     high = num //100
#     if num == low ** 3 + mid ** 3 + high ** 3:
#         print(num)
"""

正整数的反转

"""
# num = int(input('num = '))
# reversed_num = 0
# while num > 0:
#     reversed_num = reversed_num * 10 + num % 10
#     num //= 10
# print(reversed_num)
"""

百钱百鸡问题：公鸡5元一只，母鸡3元一只，小鸡1元三只，用100块钱买一百只鸡，问公鸡、母鸡、小鸡各有多少只？

"""
# 穷举法求解
# for x in range (0,20): # 如果只买公鸡，最多买20只
#     for y in range (0,33): # 如果只买母鸡，最多33只
#         z = 100 - x - y
#         if 5 * x + 3 * y + (1/3) * z == 100:
#             print('公鸡有%d只，母鸡有%d只，小鸡有%d只' % (x, y, z))
"""

CRAPS又称花旗骰，是美国拉斯维加斯非常受欢迎的一种的桌上赌博游戏。该游戏使用两粒骰子，玩家通过摇两粒骰子获得点数进行游戏。简单的规则是：玩家第一次摇骰子如果摇出了7点或11点，玩家胜；玩家第一次如果摇出2点、3点或12点，庄家胜；其他点数玩家继续摇骰子，如果玩家摇出了7点，庄家胜；如果玩家摇出了第一次摇的点数，玩家胜；其他点数，玩家继续要骰子，直到分出胜负。我们设定玩家开始游戏时有1000元的赌注
游戏结束的条件是玩家输光所有的赌注

"""
# from random import randint
#
# money = 1000
# while money > 0:
#     print('你的总资产为:', money)
#     needs_go_on = False
#     while True:
#         debt = int(input('请下注：'))
#         if 0 < debt <= money:
#             break # 判断资金是否足够用来下注
#     first = randint(1,6) + randint(1,6)
#     print('玩家摇出了%d点' % first)
#     if first == 7 or first == 11:
#         print('玩家胜！')
#         money += debt
#     elif first == 2 or first == 3 or first == 12:
#         print('庄家胜！')
#         money -= debt
#     else:
#         needs_go_on = False
#     while needs_go_on:
#         needs_go_on = False
#         current = randint(1,6) + randint(1,6)
#         print('玩家摇出了%d点' % current)
#         if current == 7:
#             print('庄家胜！')
#             money -= debt
#         elif current == first:
#             print('玩家胜！')
#             money += debt
#         else:
#             needs_go_on = True
# print('你破产了，游戏结束！')
"""

生成斐波那契数列的前20个数。

"""
# currnet = 0
# next = 1
# i = 0
# print('1', end = ' ')
# for i in range (2,21):
#     tmp = next
#     next += currnet
#     currnet = tmp
#     i += 1
#     print(next, end=' ')
"""

找出10000以内的完美数：完美数又称为完全数或完备数，它的所有的真因子（即除了自身以外的因子）的和（即因子函数）恰好等于它本身。例如：6（$6=1+2+3$）和28（$28=1+2+4+7+14$）就是完美数

""" # 没看懂
# import math
#
# for num in range(1, 10000):
#     result = 0
#     for factor in range(1, int(math.sqrt(num)) + 1):
#         if num % factor == 0:
#             result += factor
#             if factor > 1 and num // factor != factor:
#                 result += num // factor
#     if result == num:
#         print(num)
# import math
#
# for num in range(2, 2^1024):
#     is_prime = True
#     for factor in range(2, int(math.sqrt(num)) + 1):
#         if num % factor == 0:
#             is_prime = False
#             break
#     if is_prime:
#         print(num)
"""

输入M和N计算C(M,N)

"""
# m = int(input('m = '))
# n = int(input('n = '))
# fm = 1
# for num in range(1, m + 1):
#     fm *= num
# fn = 1
# for num in range(1, n + 1):
#     fn *= num
# fm_n = 1
# for num in range(1, m - n + 1):
#     fm_n *= num
# print(fm // fn // fm_n)
# def fac(num):
#     """ 求阶乘 """
#     result = 1
#     for n in range (1, num+1):
#         result *= n
#     return result
# m = int(input('m = '))
# n = int(input('n = '))
# print(fac(m) // fac(n) // fac(m - n))
# print(fac(3))
"""

函数的参数

"""
# from random import randint
# def roll_dice(n=2):
#     """摇骰子"""
#     total = 0
#     for _ in range(2):
#         total += randint(1,6)
#     return total
#
# def add(a=0, b=0, c=0):
#     """三个数相加"""
#     return a + b + c
# # print(roll_dice())
# # print(roll_dice(3))
# # print(add())
# # print(add(1))
# # print(add(1,2))
# # print(add(1,2,3))
# # print(add(c=50, a=100, b=200))
# # 可变参数
# def add_b(*args):   # 在参数名前面的*是一个可变参数
#     total = 0
#     for val in args:
#         total += val
#     return total
# print(add_b())
# print(add_b(1))
# print(add_b(1,2))
# print(add_b(1,2,3))
# print(add_b(1,3,4,7,9))
"""

模块管理函数

"""
# from module1 import foo
# foo()
# from module2 import foo
# foo()
# import module1 as m1
# import module2 as m2
# m1.foo()
# m2.foo()
# import module3
"""实现计算最大公约数和最小公倍数的函数"""
# def gcd(x,y):
#     """求最大公约数"""
#     if x > y:
#         (x,y) = (y,x)
#     else:
#         (x,y)
#     for factor in range(x,0,-1):
#         if x % factor == 0 and y %factor == 0:
#             return factor
# def lcm(x,y):
#     """求最小公倍数"""
#     return x * y // gcd(x,y)
# print(gcd(1243,3423))
# print(lcm(12321,23))
"""判断一个数是不是回文数的函数"""
# 运行有问题
# def is_palindrome(num):
#     tmp = num
#     total = 0
#     while tmp > 0:
#         total =total * 10 + tmp % 10
#         tmp //= 10
#     return total == num
"""变量的作用域"""
# def foo():
#     b = 'hello'
#
#     # Python中可以在函数内部再定义函数
#     def bar():
#         c = True
#         print(a)
#         print(b)
#         print(c)
#
#     bar()
#     # print(c)  # NameError: name 'c' is not defined
#
#
# if __name__ == '__main__':
#     a = 100
#     # print(b)  # NameError: name 'b' is not defined
#     foo()
# def foo():
#     a = 200
#     print(a)  # 200
#
#
# if __name__ == '__main__':
#     a = 100
#     foo()
#     print(a)  # 100
# global关键字修改全局作用域的a
# 如果我们希望函数内部的函数能够修改嵌套作用域中的变量，可以使用nonlocal关键字来指示变量来自于嵌套作用域
# def foo():
#     global a
#     a = 200
#     print(a)  # 200
#
#
# if __name__ == '__main__':
#     a = 100
#     foo()
#     print(a)  # 200
"""使用字符串"""
# s1 = 'Hello, World!'
# s2 = 'Hello, World!'
# # # 以三个双引号或单引号开头的字符串可以折行
# s3 = """
# Hello,
# World!
# """
# def youxiu():
#     print('\u4F18\u79C0')
#     return '\u771f\u7684\u4f18\u79c0'
# print(s1,s2,s3,end='')
# s3 = '\'hello, world!\''
# s4 = '\n\\hello, world!\\\n'
# print(s3, s4, end='')
# s5 = youxiu()
# print(s5,end='')
# s6 = '\n' + r'\'hello, world!\''
# s7 = r'\n\\hello, world!\\\n'
# print(s6, s7, end='')
"""我们可以使用+运算符来实现字符串的拼接，可以使用*运算符来重复一个字符串的内容，可以使用in和not in来判断一个字符串是否包含另外一个字符串（成员运算），我们也可以用[]和[:]运算符从字符串取出某个字符或某些字符（切片运算）"""
# s8 = 'hello ' * 3
# print('\n' + s8) # hello hello hello
# s9 = 'world'
# s8 += s9
# print(s8) # hello hello hello world
# print('ll' in s8) # True
# print('good' in s8) # False
# str20 = 'abc123456'
# # 从字符串中取出指定位置的字符(下标运算)
# print(str20[2]) # c
# # 字符串切片(从指定的开始索引到指定的结束索引)
# print(str20[2:5]) # c12
# print(str20[2:]) # c123456
# print(str20[2::2]) # c246
# print(str20[::2]) # ac246
# print(str20[::-1]) # 654321cba
# print(str20[-3:-1]) # 45
"""字符串的处理"""
# str1 = 'hello, world!'
# # 通过内置函数len计算字符串的长度
# print(len(str1)) # 13
# # 获得字符串首字母大写的拷贝
# print(str1.capitalize()) # Hello, world!
# # 获得字符串每个单词首字母大写的拷贝
# print(str1.title()) # Hello, World!
# # 获得字符串变大写后的拷贝
# print(str1.upper()) # HELLO, WORLD!
# # 从字符串中查找子串所在位置
# print(str1.find('or')) # 8
# print(str1.find('shit')) # -1
# # 与find类似但找不到子串时会引发异常
# # print(str1.index('or'))
# # print(str1.index('shit'))
# # 检查字符串是否以指定的字符串开头
# print(str1.startswith('He')) # False
# print(str1.startswith('hel')) # True
# # 检查字符串是否以指定的字符串结尾
# print(str1.endswith('!')) # True
# # 将字符串以指定的宽度居中并在两侧填充指定的字符
# print(str1.center(50, '*'))
# # 将字符串以指定的宽度靠右放置左侧填充指定的字符
# print(str1.rjust(50, ' '))
# str2 = 'abc123456'
# # 检查字符串是否由数字构成
# print(str2.isdigit())  # False
# # 检查字符串是否以字母构成
# print(str2.isalpha())  # False
# # 检查字符串是否以数字和字母构成
# print(str2.isalnum())  # True
# str3 = '  jackfrued@126.com '
# print(str3)
# # 获得字符串修剪左右两侧空格之后的拷贝
# print(str3.strip())
"""格式化输出字符串"""
# a, b = 5, 10
# print('{0} * {1} = {2}'.format(a, b, a * b))
# print(f'{a} * {b} = {a * b}') # python3.6之后的版本才支持
"""使用列表"""
# list1 = [1, 3, 5, 7, 100]
# print(list1)
# list2 = list1 * 3
# print(list2)
# print(len(list2))
# print(list2[5])
# print(list2[-2])
# list2[-2] = 200
# print(list2[-2])
# for index in range(len(list2)):
#     print(list2[index],end=' ')
# for elem in list2:
#     print(elem,end=' ')
# for index, elem in enumerate(list2):
#     print(index,elem)
"""向列表中添加元素以及如何从列表中移除元素。"""
# list1 = [1, 3, 5, 7, 100]
# list2 = [2, 4, 6, 8, 200]
# # 添加元素
# list1.append(1997)
# list2.insert(4,1997) # insert函数需要指明插入的数的数值以及其在列表中的位置
# print(list1)
# print(list2)
# # 合并两个列表
# list1 += [1008,1009]
# list2.extend([1008,1009])
# print(list1)
# print(list2)
# # 先通过成员运算判断元素是否在列表中，如果存在就删除该元素
# if 3 in list1:
#     list1.remove(3)
#     print(list1)
# if 4 in list2:
#     list2.remove(4)
#     print(list2)
# # 从指定的位置删除元素
# list1.pop(0)
# list2.pop(len(list2) - len(list2))
# print(list1)
# print(list2)
# list1.clear()
# print(list1)
"""通过切片操作我们可以实现对列表的复制或者将列表中的一部分取出来创建出新的列表"""
# fruits = ['grape', 'apple', 'strawberry', 'waxberry']
# fruits += ['pitaya', 'pear', 'mongo']
# # 列表切片
# fruits2 = fruits[1:4] # 切出来的是fruits的第1个，第2个，第3个，注意，序号是从0开始的
# print(fruits)
# print(fruits2)
# # 可以通过完整切片操作来复制列表
# fruits3 = fruits[:]
# print(fruits3)
# fruits4 = fruits[-4:-1]
# print(fruits4)
# # 可以通过反向切片操作来获得倒转后的列表的拷贝
# fruits5 = fruits[::-1]
# print(fruits5)
"""对列表的排序操作"""
# list1 = ['orange', 'apple', 'zoo', 'internationalization', 'blueberry']
# list2 = sorted(list1)
# print(list2)                           #默认升序排列
# list3 = sorted(list1, reverse= True)   #reverse = Ture为降序排列
# print(list3)
# list4 = sorted(list1, key=len, reverse=True) # 按长度关键字排序
# print(list4)
# print(list1)
# # 给列表对象发出排序消息直接在列表对象上进行排序，会修改原来的list
# list1.sort(key=len, reverse=True)
# print(list1)
"""使用列表的生成式语法来创建列表"""
# 列表的生成式语法
# f = [x for x in range(1,10)]
# print(f)
# f = [x + y for x in 'ABCDE' for y in '1234567']
# print(f)
# 用这种语法创建列表之后元素已经准备就绪所以需要耗费较多的内存空间
# f = [x ** 2 for x in range(1,1000)]
# print(sys.getsizeof(f))
# print(f)
# 请注意下面的代码创建的不是一个列表而是一个生成器对象
# 通过生成器可以获取到数据但它不占用额外的空间存储数据
# 每次需要数据的时候就通过内部的运算得到数据(需要花费额外的时间)
# f = (x ** 2 for x in range(1,1000))
# print(sys.getsizeof(f))
# print(f)
# for val in f:
#     print(val)
"""实现一个生成斐波拉切数列的生成器"""
# def fib(n):
#     a, b = 0, 1
#     for _ in range(n):
#         a, b = b, a + b
#         yield a
#
#
# def main():
#     for val in fib(20):
#         print(val)
#
#
# if __name__ == '__main__':
#     main()
"""使用元组"""
# # Python中的元组与列表类似也是一种容器数据类型，可以用一个变量（对象）来存储多个数据，不同之处在于元组的元素不能修改
# # 定义元组
# t = ('陈俊宇', 23, True, '四川广安')
# print(t)
# # 获取元组中的数据
# print(t[0])
# print(t[3])
# # 遍历元组中的数值
# for menber in t:
#     print(menber,end=' ')
# # 重新给元组赋值
# # t[0] = '王大锤'，# TypeError 其中的元素不能赋值修改，但可以对整个元组重新赋值
# t = ('王大锤', 40, False, '云南昆明')
# print(t)
# # 将元组转换成列表
# person = list(t)
# print(person)
# person[0] = '陈俊宇'
# person[1] = 23
# print(person)
# # 将列表转换为元组
# person_yuanzu = tuple(person)
# print(person_yuanzu)
"""使用集合"""
# # Python中的集合跟数学上的集合是一致的，不允许有重复元素，而且可以进行交集、并集、差集等运算。
# # 创建集合的字面量语法
# set1 = {1, 2, 3, 3, 3, 2, 14}
# print(set1)
# # print('Lenth = ', len(set1))
# # 创造集合的构造器语法
# set2 = set(range(1,10))
# print(set2)
# set3 = {(1, 2, 3, 3, 2, 1)}
# # print(set2, set3)
# # # 创造集合的推导式语法
# set4 = {num for num in range(1,100) if num % 3 == 0 or num % 5 ==0}
# # print(set4)
# # 从集合添加元素和删除元素
# set1.add(4)
# set1.add(5)
# set2.update([11,12])
# set2.discard(5)
# if 4 in set2:
#     set2.remove(4)
# print(set1, set2)
# print(set3.pop()) # 只有列表和集合可以使用pop函数，元组不可以，作用是删除
# print(set3)
# print(set1)
# print(set2)
# # 集合的成员、交集、并集与差集等运算
# print(set1 & set2) # 交集
# print(set1 | set2) # 并集
# print(set1 - set2) # 差集
# print(set1 ^ set2) # 不晓得
# # 判断子集和超集
# print(set2 <= set1)
# print(set3 <= set1)
# print(set1 >= set2)
# print(set1 >= set3)
"""使用字典"""
# # 字典的每个元素都是由一个键和一个值组成的“键值对”，键和值通过冒号分开
# # 创建字典的字面量语法
# scores = {'陈俊宇': 95, '张三': 87, '李四': 74}
# print(scores)
# # 创造字典的构造器语法
# items1 = dict(one=1, two=2, three=3, four=4)
# # 通过zip函数将两个序列压缩成字典
# items2 = dict(zip(['a', 'b', 'c'], '123'))
# # 创建字典的推导式语法
# items3 = {num: num ** 2 for num in range(1,10)}
# print(items1,items2,items3)
# # 通过键获取字典中对应的值
# print(scores['陈俊宇'])
# print(scores['张三'])
# # 对字典中所有键值进行遍历
# for key in scores:
#     print(f'{key}: {scores[key]}')
# # 更新字典中的元素
# scores['陈俊宇'] = 88
# scores['张三'] = 71
# scores.update(冷面=67, 方启鹤=85)
# print(scores)
# if '武则天' in scores:
#     print(scores['武则天'])
# print(scores.get('武则天'))
# # get方法也是通过键获取对应的值但是可以设置默认值
# print(scores.get('武则天', 60))
# # 删除字典中的元素
# print(scores.popitem())
# print(scores.pop('陈俊宇',88))
# # 清空字典
# scores.clear()
# print(scores)
"""在屏幕上显示跑马灯文字"""
import os
import time

def main():
    content = '北京欢迎你，为你开天辟地！'
    while True:
        # 清理屏幕上的输出
        os.system('cls')    # os.system('clear')
        print(content)
        # 休眠200毫秒
        time.sleep(0.2)
        content = content[1:] + content[0]

if __name__ == '__main__':
    main()
