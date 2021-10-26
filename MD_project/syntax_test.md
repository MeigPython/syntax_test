### 一. 基础语法
#### 1.Python保留字

	>>>import keyword
	>>> keyword.kwlist
	
结果：ImportError: no module named 'keyword'
#### 2.字符串

	#!/usr/bin/python3 
	str='123456789' print(str) # 输出字符串 
	print(str[0:-1]) # 输出第一个到倒数第二个的所有字符 
	print(str[0]) # 输出字符串第一个字符 
	print(str[2:5]) # 输出从第三个开始到第五个的字符 
	print(str[2:]) # 输出从第三个开始后的所有字符 

	###存在问题
	print(str[1:5:2]) # 输出从第二个开始到第五个且每隔一个的字符（步长为2）
	print(str * 2) # 输出字符串两次 
	print(str + 'abc') # 连接字符串 
	print('hello\nrunoob') # 使用反斜杠(\)+n转义特殊字符 
	print(r'hello\nrunoob') # 在字符串前面添加一个 r，表示原始字符串，不会发生转义

结果：

123456789

12345678

1

345

3456789

123456789123456789

123456789abc

hello

runoob

hello\nrunoob

#### 3.同一行显示多条语句

	import sys; x = 'runoob'; sys.stdout.write(x + '\\n')

结果:
runoob

7

#### 4.print输出

	x="a" 
	y="b" 
	# 换行输出 
	print( x ) 
	print( y ) 
	print( x, end=" " ) 
	print( y, end=" " ) print()

结果：
a

b

a b 

#### 5.import与from...import

	import sys
	print('================Python import mode==========================')
	print ('canshu:')
	for i in sys.argv:
	    print (i)
	print ('\n python ',sys.path)

结果：

================Python import mode==========================

canshu:

python  ['', '/usr']

	from sys import argv,path  #  导入特定的成员
	 
	print('================python from import===================================')
	print('path:',path) # 因为已经导入path成员，所以此处引用时不需要加sys.path

结果：
================python from import===================================

path: ['', '/usr']

### 二. 基本数据类型
#### 1.number(数字）
	a, b, c, d = 20, 5.5, True, 4+3j
	print(type(a), type(b), type(c), type(d))
结果：
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>

	class A:
	pass
	Class B(A):
	pass
	isinstance(A(), A)         True
	type(A()) == A 	        True
	isinstance(B(), A)         True
	type(B()) == A              False
	2.String(字符串）
	str='Runoob'
	print(str)
	print(str[0:-1])
	print(str[0])
	print(str[2:5])
	print(str[2:])
	print(str*2)
	print(str+"TEST")
结果：

Runoob

Runoo

R

noo

noob

RunoobRunoob

RunoobTEST

	print('Ru\\noob') 
结果：

Ru

oob

	print(r'Ru\\noob')
结果：

Ru\noob      

	word = 'Python'
	print(word[0], word[5])
结果：P n
	print(word[-1], word[-6])
结果：n P

#### 2.List（列表）

	#!/usr/bin/python3
	list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ]
	tinylist = [123, 'runoob']
	print (list)            # 输出完整列表
	print (list[0])         # 输出列表第一个元素
	print (list[1:3])       # 从第二个开始输出到第三个元素
	print (list[2:])        # 输出从第三个元素开始的所有元素
	print (tinylist * 2)    # 输出两次列表
	print (list + tinylist) # 连接列表
结果：

['abcd', 786, 2.23, 'runoob', 70.2]

abcd

[786, 2.23]

[2.23, 'runoob', 70.2]

[123, 'runoob', 123, 'runoob']

['abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob']

	a = [1, 2, 3, 4, 5, 6]
	a[0] = 9
	a[2:5] = [13, 14, 15]
	print(a)
	a[2:5] = []
	print(a)
结果：

[9, 2, 13, 14, 15, 6]

[9, 2, 6]

	def reverseWords(input):
	    # 通过空格将字符串分隔符，把各个单词分隔为列表
	    inputWords = input.split(" ")
	    # 翻转字符串
	    # 假设列表 list = [1,2,3,4],  
	    # list[0]=1, list[1]=2 ，而 -1 表示最后一个元素 list[-1]=4 ( 与 list[3]=4 一样)
	    # inputWords[-1::-1] 有三个参数
	    # 第一个参数 -1 表示最后一个元素
	    # 第二个参数为空，表示移动到列表末尾
	    # 第三个参数为步长，-1 表示逆向
	    inputWords=inputWords[-1::-1]
	    # 重新组合字符串
	    output = ' '.join(inputWords)
	    return output
	if __name__ == "__main__":
	    input = 'I like runoob'
	    rw = reverseWords(input)
	    print(rw)
结果：
runoob like I

#### 3.Tuple（元组）

	#!/usr/bin/python3
	tuple = ( 'abcd', 786 , 2.23, 'runoob', 70.2  )
	tinytuple = (123, 'runoob')
	print (tuple)             # 输出完整元组
	print (tuple[0])          # 输出元组的第一个元素
	print (tuple[1:3])        # 输出从第二个元素开始到第三个元素
	print (tuple[2:])         # 输出从第三个元素开始的所有元素
	print (tinytuple * 2)     # 输出两次元组
	print (tuple + tinytuple) # 连接元组
结果：

('abcd', 786, 2.23, 'runoob', 70.2)

abcd

(786, 2.23)

(2.23, 'runoob', 70.2)

(123, 'runoob', 123, 'runoob')

('abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob')

	tup = (1, 2, 3, 4, 5, 6)
	print(tup[0])
结果：1
	print(tup[1:5])
结果：(2, 3, 4, 5)
	tup[0] = 11
结果：

	Traceback (most recent call last):
	 File "<stdin>", line 1, in <module>
	TypeError: 'tuple' object does not support item assignment

#### 4.Set（集合）

	#!/usr/bin/python3
	sites = {'Google', 'Taobao', 'Runoob', 'Facebook', 'Zhihu', 'Baidu'}
	print(sites)   # 输出集合，重复的元素被自动去掉
	# 成员测试
	if 'Runoob' in sites :
	    print('Runoob in')
	else :
	    print('Runoob not in ')
	# set可以进行集合运算
	a = set('abracadabra')
	b = set('alacazam')
	print(a)
	print(a - b)     # a 和 b 的差集
	print(a | b)     # a 和 b 的并集
	print(a & b)     # a 和 b 的交集
	print(a ^ b)     # a 和 b 中不同时存在的元素
结果：

{'Runoob', 'Facebook', 'Google', 'Zhihu', 'Baidu', 'Taobao'}

Runoob in

{'c', 'b', 'd', 'a', 'r'}

{'b', 'd', 'r'}

{'z', 'd', 'r', 'm', 'a', 'l', 'c', 'b'}

{'c', 'a'}

{'m', 'd', 'z', 'r', 'l', 'b'}

#### 5.Dictionary(字典）

	#!/usr/bin/python3
	dict = {}
	dict['one'] = "1 - adc"
	dict[2]     = "2 - ABC"
	tinydict = {'name': 'runoob','code':1, 'site': 'www.runoob.com'}
	print (dict['one'])       # 输出键为 'one' 的值
	print (dict[2])           # 输出键为 2 的值
	print (tinydict)          # 输出完整的字典
	print (tinydict.keys())   # 输出所有键
	print (tinydict.values()) # 输出所有值
结果：

1 - adc

2 - ABC

{'name': 'runoob', 'site': 'www.runoob.com', 'code': 1}

dict_keys(['name', 'site', 'code'])

dict_values(['runoob', 'www.runoob.com', 1])

	dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
结果：{'Google': 2, 'Runoob': 1, 'Taobao': 3}

	{x: x**2 for x in (2, 4, 6)}
结果：{4: 16, 2: 4, 6: 36}

	dict(Runoob=1, Google=2, Taobao=3)
结果：{'Google': 2, 'Runoob': 1, 'Taobao': 3}

#### 6.Python数据类型转换

##### (1)int(x,[base])
	int(2.5)           结果：2
	int("1001",2)     #将二进制数转换为十进制数      结果：9
	int("0xa",16)     #将十六机制数转换为十进制数     结果：10
	int("17",8)       #将八进制数转换为十进制数       结果：15
##### (2)float(x)
	float(10)            结果：10.0
	float('123')         结果：123.0
##### (3)complex([real[,imag]])
	complex(1, 2)            结果：(1+2j)
	complex("1")             结果：(1 + 0j)
##### (4)str(x)
	dict = {'runoob': 'runoob.com', 'google': 'google.com'};
	str(dict)
结果：

"{'runoob': 'runoob.com', 'google': 'google.com'}"
##### (5)repr(x)
	dict = {'runoob': 'runoob.com', 'google': 'google.com'};
	repr(dict)
结果：

"{'runoob': 'runoob.com', 'google': 'google.com'}"
##### (6)eval(str)
	x = 7
	eval( '3 * x' )
结果：
21

	n=81
	eval("n + 4")
结果：85
##### (7)tuple(s)
	list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
	tuple1=tuple(list1)
	tuple1
结果：('Google', 'Taobao', 'Runoob', 'Baidu')
##### (8)list(s)
	#!/usr/bin/python3
	aTuple = (123, 'Google', 'Runoob', 'Taobao')
	list1 = list(aTuple)
	print ("list1 : ", list1)
	str="Hello World"
	list2=list(str)
	print ("list2 : ", list2)
结果：

list1 :  [123, 'Google', 'Runoob', 'Taobao']

list2 :  ['H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd']
##### (9)Set(s)
	x = set('runoob')
	y = set('google')
	x, y

结果：

({'o', 'r', 'b', 'u', 'n'}, {'e', 'l', 'g', 'o'})

	x & y
结果：{'o'}

	x | y
结果：{'b', 'e', 'o', 'u', 'n', 'l', 'g', 'r'}

	x - y
结果：{'r', 'b', 'u', 'n'}

##### (10)dict(d)

	dict(a='a', b='b', t='t')
结果：{'a': 'a', 't': 't', 'b': 'b'}

	dict([('one', 1), ('two', 2), ('three', 3)])
结果：{'three': 3, 'two': 2, 'one': 1}
##### (11)frozenset(s)
	a = frozenset(range(10))
	a

结果：frozenset({0, 1, 2, 3, 4, 5, 6, 7, 8, 9})
#####（11)chr(x)

	print(chr(0x30), chr(0x31), chr(0x61))
结果：0 1 a

	print(chr(48), chr(49), chr(97))
结果：0 1 a

##### (12)ord(x)
	ord('a')
结果：97

##### (13)hex(x)
	hex(255)
结果：'0xff'
##### (14)oct(x)
	oct(10)
结果：'0o12'

### 三. 运算符

#### 1.算数运算符
	#!/usr/bin/python3
	a = 21
	b = 10
	c = 0
	c = a + b
	print ("c1=", c)
	c = a - b
	print ("c2=", c)
	c = a * b
	print ("c3=", c)
	c = a / b
	print ("c4=", c)
	c = a % b
	print ("c5=", c)
	# 修改变量 a 、b 、c
	a = 2
	b = 3
	c = a**b 
	print ("c6=", c)
	a = 10
	b = 5
	c = a//b 
	print ("c7=", c)

结果：

c1= 31

c2= 11

c3= 210

c4= 2.1

c5= 1

c6= 8

c7= 2

	#!/usr/bin/python3
	a = 21
	b = 10
	c = 0
	if ( a == b ):
	   print ("1 a = b")
	else:
	   print ("1 a != b")
	if ( a != b ):
	   print ("2  a != b")
	else:
	   print ("2  a = b")
	if ( a < b ):
	   print ("3  a < b")
	else:
	   print ("3  a >= b")
	if ( a > b ):
	   print ("4  a > b")
	else:
	   print ("4  a <= b")
	# 修改变量 a 和 b 的值
	a = 5
	b = 20
	if ( a <= b ):
	   print ("5  a <= b")
	else:
	   print ("5  a >  b")
	if ( b >= a ):
	   print ("6  b >= a")
	else:
	   print ("6  b < a")

结果：

1 a != b

2  a != b

3  a >= b

4  a > b

5  a <= b

6  b >= a


#### 2.赋值运算符
 
	#!/usr/bin/python3
	a = 21
	b = 10
	c = 0
	c = a + b
	print ("c1 =", c)
	c += a
	print ("c2 =", c)
	c *= a
	print ("c3 =", c)
	c /= a 
	print ("c4 =", c)
	c = 2
	c %= a
	print ("c5 =", c)
	c **= a
	print ("c6 =", c)
	c //= a
	print ("c7 =", c)
结果：

c1 = 31

c2 = 52

c3 = 1092

c4 = 52.0

c5 = 2

c6 = 2097152

c7 = 99864

#### 3.位运算符
	#!/usr/bin/python3
	a = 60            # 60 = 0011 1100 
	b = 13            # 13 = 0000 1101 
	c = 0
	c = a & b        # 12 = 0000 1100
	print ("c1=",c)
	c = a | b        # 61 = 0011 1101 
	print ("c2=",c)
	c = a ^ b        # 49 = 0011 0001
	print ("c3=",c) 
	c = ~a           # -61 = 1100 0011
	print ("c4=",c) 
	c = a << 2       # 240 = 1111 0000
	print ("c5=",c)
	c = a >> 2       # 15 = 0000 1111
	print ("c6=",c)
结果：

c1= 12

c2= 61

c3= 49

c4= -61

c5= 240

c6= 15

#### 4.逻辑运算符
	#!/usr/bin/python3
	a = 10
	b = 20
	if ( a and b ):
	   print ("Both a and b are true")
	else:
	   print ("Neither a nor B is true")
	if ( a or b ):
	   print ("Both a and b are true, or one of the variables is true")
	else:
	   print ("Neither a nor b is true")
	# 修改变量 a 的值
	a = 0
	if ( a and b ):
	   print ("Both a and b are true")
	else:
	   print ("Neither a nor B is true")
	if ( a or b ):
	   print ("Both a and b are true, or one of the variables is true")
	else:
	   print ("Neither a nor b is true")
	if not( a and b ):
	   print ("Both a and b are false, or one of the variables is false")
	else:
	   print ("Both a and b are true")
结果：

Both a and b are true

Both a and b are true, or one of the variables is true

Neither a nor B is true

Both a and b are true, or one of the variables is true

Both a and b are false, or one of the variables is false

#### 5.成员运算符
	#!/usr/bin/python3
	a = 10
	b = 20
	list = [1, 2, 3, 4, 5 ]
	if ( a in list ):
	   print ("1a in list")
	else:
	   print ("1a not in list")
	if ( b not in list ):
	   print ("2b not in list")
	else:
	   print ("2b in list")
	a = 2
	if ( a in list ):
	   print ("3a in list")
	else:
	   print ("3a not in list")
结果：

1a not in list

2b not in list

3a in list

#### 6.身份运算符
	#!/usr/bin/python3
	a = 20
	b = 20
	if ( a is b ):
	   print ("1 - a and b same")
	else:
	   print ("1 - a and b not same")
	 
	if ( id(a) == id(b) ):
	   print ("2 - a and b same")
	else:
	   print ("2 - a and b not same")
	b = 30
	if ( a is b ):
	   print ("3 - a and b same")
	else:
	   print ("3 - a and b not same")
	 
	if ( a is not b ):
	   print ("4 - a and b not same")
	else:
	   print ("4 - a and b same")
结果：

1 - a and b same

2 - a and b same

3 - a and b not same

4 - a and b not same

#### 7.运算符优先级
	#!/usr/bin/python3
	a = 20
	b = 10
	c = 15
	d = 5
	e = 0
	e = (a + b) * c / d       #( 30 * 15 ) / 5
	print ("(a + b) * c / d =",  e)
	e = ((a + b) * c) / d     # (30 * 15 ) / 5
	print ("((a + b) * c) / d =",  e)
	e = (a + b) * (c / d)    # (30) * (15/5)
	print ("(a + b) * (c / d) =",  e)
	e = a + (b * c) / d      #  20 + (150/5)
	print ("a + (b * c) / d =",  e)
结果：

(a + b) * c / d = 90.0

((a + b) * c) / d = 90.0

(a + b) * (c / d) = 90.0

a + (b * c) / d = 50.0

### 四. 数字（Number）
#### 1.数据类型转换
	a=1.0
	int(a)
结果：1

#### 2.数字运算
	tax = 12.5 / 100
	price = 100.50
	price * tax

结果：12.5625

	price + _

结果：

113.0625

round(_, 2)

113.06

#### 3.数学函数
##### (1)abs(x)
	print ("abs(-40) : ", abs(-40))
结果：abs(-40) :  40

##### (2)ceil(x)
	#!/usr/bin/python3
	import math   # 导入 math 模块
	print ("math.ceil(-45.17) : ", math.ceil(-45.17))
	print ("math.ceil(100.12) : ", math.ceil(100.12))
	print ("math.ceil(100.72) : ", math.ceil(100.72))
	print ("math.ceil(math.pi) : ", math.ceil(math.pi))
结果：

math.ceil(-45.17) :  -45

math.ceil(100.12) :  101

math.ceil(100.72) :  101

math.ceil(math.pi) :  4
##### (3)exp(x)
	import math   
	print("math.exp(-45.17) : ", math.exp(-45.17))
结果：math.exp(-45.17) :  2.415011e-20
##### (4)fabs(x)
	import math
	print ("math.fabs(-45.17) : ", math.fabs(-45.17))
结果：math.fabs(-45.17) :  45.17
##### (5)floor(x)
	import math
	print ("math.floor(-45.17) : ", math.floor(-45.17))
结果：math.floor(-45.17) :  -46
##### (6)log（X）
	import math
	print ("math.log(100.12) : ", math.log(100.12))
结果：math.log(100.12) :  4.606369
##### (7)log10（x）
	import math
	print ("math.log10(100.12) : ", math.log10(100.12))
结果：math.log10(100.12) :  2.000521
##### (8)max(x1,x2,...)
	print ("max(80, 100, 1000) : ", max(80, 100, 1000))
结果：max(80, 100, 1000) :  1000
##### (9)min(x1,x2,...)
	print ("min(80, 100, 1000) : ", min(80, 100, 1000))
结果：min(80, 100, 1000) :  80
##### (10)modf(x)
import math
print ("math.modf(100.12) : ", math.modf(100.12))
结果：math.modf(100.12) :  (0.1200027, 100.0)
##### (11)pow(x,y)

	import math
	print ("math.pow(100, 2) : ", math.pow(100, 2))
	print ("pow(100, 2) : ", pow(100, 2))

结果：
math.pow(100, 2) :  10000.0
pow(100, 2) :  10000
##### (12)round(x[,n])
print ("round(70.23456) : ", round(70.23456))
print ("round(56.659,1) : ", round(56.659,1))
结果：
round(70.23456) :  70
round(56.659,1) :  56.7
##### (13)sqrt(x)
import math
print ("math.sqrt(100) : ", math.sqrt(100))
print ("math.sqrt(7) : ", math.sqrt(7))
结果：
math.sqrt(100) :  10.0
math.sqrt(7) :  2.645751

#### 4.随机数函数
#### (1)choice（seq）

	#!/usr/bin/python3
	import random
	print ("range(100): ",random.choice(range(100)))
	print ("[1, 2, 3, 5, 9]): ", random.choice([1, 2, 3, 5, 9]))
	print ("'Runoob': ", random.choice('Runoob'))
结果：

range(100):  59

[1, 2, 3, 5, 9]):  1

'Runoob':  n

#### (2)randrange ([start,] stop [,step])

	#!/usr/bin/python3
	import random
	# 从 1-100 中选取一个奇数
	print ("randrange(1,100, 2) : ", random.randrange(1, 100, 2))
	# 从 0-99 选取一个随机数
	print ("randrange(100) : ", random.randrange(100))

结果：

randrange(1,100, 2) :  87

randrange(100) :  48

#### (3)random()

	import random
	print ("random() : ", random.random())
	print ("random() : ", random.random())
结果：

random() :  0.1489719

random() :  0.02669346

#### (4)seed([x])

	#!/usr/bin/python3

	import random
	random.seed()
	print ("default:", random.random())
	print ("default:", random.random())
	random.seed(10)
	print ("int 10:", random.random())
	random.seed(10)
	print ("int 10:", random.random())

结果：

default: 0.08007515

default: 0.3725224

int 10: 0.2382998

int 10: 0.2382998

#### (5)shuffle(lst){不支持}

	#!/usr/bin/python3
	import random
	 
	list = [20, 16, 10, 5];
	random.shuffle(list)
	print ("Random list1:",  list)
	 
	random.shuffle(list)
	print ("Random list2:",  list)

#### (6)uniform() 函数

	import random
	print ("uniform(5, 10):",  random.uniform(5, 10))
	print ("uniform(7, 14):",  random.uniform(7, 14))

结果：

uniform(5, 10): 8.839498

uniform(7, 14): 12.81811

#### 5.三角函数
#### (1)acos(x)

	import math
	print ("acos(0.64) : ",  math.acos(0.64))
	print ("acos(0) : ",  math.acos(0))
	print ("acos(-1) : ",  math.acos(-1))
	print ("acos(1) : ",  math.acos(1))

结果：

acos(0.64) :  0.876298

acos(0) :  1.570796

acos(-1) :  3.141593

acos(1) :  0.0

#### (2)asin(x)

	import math
	print ("asin(0.64) : ",  math.asin(0.64))
	print ("asin(0) : ",  math.asin(0))
	print ("asin(-1) : ",  math.asin(-1))
	print ("asin(1) : ",  math.asin(1))

结果：

asin(0.64) :  0.6944983

asin(0) :  0.0

asin(-1) :  -1.570796

asin(1) :  1.570796

#### (3)atan(x)

	import math
	print ("atan(0.64) : ",  math.atan(0.64))
	print ("atan(0) : ",  math.atan(0))
	print ("atan(10) : ",  math.atan(10))
	print ("atan(-1) : ",  math.atan(-1))
	print ("atan(1) : ",  math.atan(1))
结果：

atan(0.64) :  0.5693131

atan(0) :  0.0

atan(10) :  1.471128

atan(-1) :  -0.7853982

atan(1) :  0.7853982

#### (4)atan2(y, x)

	import math
	print ("atan2(-0.50,-0.50) : ",  math.atan2(-0.50,-0.50))
	print ("atan2(0.50,0.50) : ",  math.atan2(0.50,0.50))
	print ("atan2(5,5) : ",  math.atan2(5,5))

结果：

atan2(-0.50,-0.50) :  -2.356194

atan2(0.50,0.50) :  0.7853982

atan2(5,5) :  0.7853982

#### (5)cos(x)

	import math
	print ("cos(3) : ",  math.cos(3))
	print ("cos(-3) : ",  math.cos(-3))
	print ("cos(0) : ",  math.cos(0))

结果：

cos(3) :  -0.9899925

cos(-3) :  -0.9899925

cos(0) :  1.0

#### (6)hypot(x, y){不支持}

	import math
	print ("hypot(3, 2) : ",  math.hypot(3, 2))
	print ("hypot(-3, 3) : ",  math.hypot(-3, 3))

#### (7)sin(x)
	
	import math
	print ("sin(3) : ",  math.sin(3))
	print ("sin(-3) : ",  math.sin(-3))
	print ("sin(0) : ",  math.sin(0))
	print ("sin(math.pi) : ",  math.sin(math.pi))
结果：

sin(3) :  0.14112

sin(-3) :  -0.14112

sin(0) :  0.0

sin(math.pi) :  -8.742278e-08

#### (8)tan(x)

	import math
	print ("tan(3) : ",  math.tan(3))
	print ("tan(-3) : ",  math.tan(-3))
	print ("tan(0) : ",  math.tan(0))
	print ("tan(math.pi) : ",  math.tan(math.pi))
结果：

tan(3) :  -0.1425465

tan(-3) :  0.1425465

tan(0) :  0.0

tan(math.pi) :  8.742278e-08

#### (9)degrees(x)

	import math
	print ("degrees(3) : ",  math.degrees(3))
	print ("degrees(-3) : ",  math.degrees(-3))
	print ("degrees(0) : ",  math.degrees(0))
	print ("degrees(math.pi) : ",  math.degrees(math.pi))

结果：

degrees(3) :  171.8873

degrees(-3) :  -171.8873

degrees(0) :  0.0

degrees(math.pi) :  180.0

#### (10)radians(x)

	import math
	print ("radians(90) : ",  math.radians(90))    
	print ("radians(45) : ",  math.radians(45))
	print ("radians(30) : ",  math.radians(30))
	print ("radians(180) : ",  math.radians(180))  

结果：

radians(90) :  1.570796

radians(45) :  0.7853982

radians(30) :  0.5235988

radians(180) :  3.141593

### 五.字符串
#### 1.访问字符串中的值

	var1 = 'Hello World!'
	var2 = "Runoob"
	print ("var1[0]: ", var1[0])
	print ("var2[1:5]: ", var2[1:5])

结果：

var1[0]:  H

var2[1:5]:  unoo

#### 2.字符串更新
	var1 = 'Hello World!'
	print("已更新字符串 : ", var1[:6] + 'Runoob!')

结果：

Hello Runoob!

#### 3.转义字符
##### (1)\\(在行尾时) 续行符

	print("line1 \
	line2 \
	line3")
结果：

line1 line2 line3

##### (2)\\\\ 反斜杠符号 {python中对应的\\}
	print("\\\")

结果：\
##### (3)\' 单引号
	print('\'')
结果：'
##### (4)\" 双引号
	print("\"")
结果："
##### (5) \b 退格(Backspace)
	print("Hello \b World!")
结果：Hello World!
##### (6) \000 空{不支持}
	print("\000")
##### (7) \\n 换行{相当于python中的\n}
	print("a\\nb")
结果：

a

b
##### (8) \v 纵向制表符
	print("Hello \v World!")
##### (9) \t 横向制表符
	print("Hello \t World!")
结果：

Hello      World!

##### (10) 回车，将 \r 后面的内容移到字符串开头，并逐一替换开头部分的字符，直至将 \r 后面的内容完全替换完成{不支持}
	print("Hello\rWorld!")
	print('google runoob taobao\r123456')
##### (11)八进制数，y 代表 0~7 的字符，例如：\012 代表换行。
	print("\110\145\154\154\157\40\127\157\162\154\144\41")
结果：Hello World!
##### (12)十六进制数，以 \x 开头，y 代表的字符，例如：\x0a 代表换行
	print("\x48\x65\x6c\x6c\x6f\x20\x57\x6f\x72\x6c\x64\x21")
结果：Hello World!
#### 4.字符串运算符

	#!/usr/bin/python3
	a = "Hello"
	b = "Python"
	print("a + b:", a + b)
	print("a * 2:", a * 2)
	print("a[1]:", a[1])
	print("a[1:4]:", a[1:4])
	if( "H" in a):
	    print("H in a")
	else:
	    print("H not in a")
	if( "M" not in a):
	    print("M not in a")
	else:
	    print("M in a")
	print (r'\n')
结果：

a + b: HelloPython

a * 2: HelloHello

a[1]: e

a[1:4]: ell

H in a

M not in a

\n

#### 5.字符串格式化
	print ("%c %s %d %u %o %x %X %f %e %E %g %G" %(66,'1x2', 10,10.5,10,10,12,12,12.345,12.345,12,12))
结果：B 1x2 10 10 12 a C 12.000000 1.234500e+01 1.234500E+01 12 12

#### 6.三引号
	para_str = """
	TAB ( \\t )
	 [ \\n ]
	"""
	print (para_str)
结果：

TAB ( 	 )

 [ 

 ]

#### 7.Unicode字符串
##### 移远支持的字符串功能
	__class__       __name__        count           endswith        
	find            format          index           isalpha         
	isdigit         islower         isspace         isupper         
	join            lower           lstrip          replace         
	rfind           rindex          rsplit          rstrip          
	split           startswith      strip           upper           
	__bases__       __dict__        decode          encode

##### (1)bytes.decode(encoding="utf-8", errors="strict")
	str = "cainiaojiaocheng";
	str_utf8 = str.encode("UTF-8")
	str_gbk = str.encode("GBK")
	print(str)
	print("UTF-8:", str_utf8)
	print("GBK:", str_gbk)
	print("UTF-8:", str_utf8.decode('UTF-8','strict'))
	print("GBK:", str_gbk.decode('GBK','strict'))

结果：

cainiaojiaocheng

UTF-8: b'cainiaojiaocheng'

GBK: b'cainiaojiaocheng'

UTF-8: cainiaojiaocheng

GBK: cainiaojiaocheng

##### (2) encode(encoding='UTF-8',errors='strict')
	#!/usr/bin/python3
	str = "cainiao";
	str_utf8 = str.encode("UTF-8")
	str_gbk = str.encode("GBK")
	print(str)
	print("UTF-8:", str_utf8)
	print("GBK:", str_gbk)
	print("UTF-8:", str_utf8.decode('UTF-8','strict'))
	print("GBK:", str_gbk.decode('GBK','strict'))
结果：

cainiao

UTF-8: b'cainiao'

GBK: b'cainiao'

UTF-8: cainiao

GBK: cainiao

##### (3) find(str, beg=0, end=len(string))

	info = 'abca'
	print(info.find('a'))
	print(info.find('a', 1))
	print(info.find('3'))
结果：

0

3

-1
##### (4) index(str, beg=0, end=len(string))
	str1 = "Runoob example....wow!!!"
	str2 = "exam";
	print (str1.index(str2))
	print (str1.index(str2, 5))
结果:

7

7
##### (5) isalpha()
	str = "runoob"
	print (str.isalpha())
	str = "Runoob example....wow!!!"
	print (str.isalpha())
结果：

True

False

##### (6) isdigit()
	str = "123456";
	print (str.isdigit())
	str = "Runoob example....wow!!!"
	print (str.isdigit())	

结果:

True

False
##### (7) islower()
	str = "RUNOOB example....wow!!!"
	print (str.islower())
	str = "runoob example....wow!!!"
	print (str.islower())
结果：

False 

True
##### (8) isspace()
	str = "       " 
	print (str.isspace())
	str = "Runoob example....wow!!!"
	print (str.isspace())
结果：

True

False
##### (9) isupper()
	str = "THIS IS STRING EXAMPLE....WOW!!!"
	print (str.isupper())
	str = "THIS is string example....wow!!!"
	print (str.isupper())
结果：

True

False
##### (10) join(sequence)
	s1 = "-"
	s2 = ""
	seq = ("r", "u", "n", "o", "o", "b") # 字符串序列
	print (s1.join( seq ))
	print (s2.join( seq ))
结果：

r-u-n-o-o-b

runoob

##### (11) len( s )
	str = "runoob"
	len(str)
结果：6

##### (12) lower()
	str = "Runoob EXAMPLE....WOW!!!"
	print( str.lower() )
结果：runoob example....wow!!!
##### (13) lstrip()
	str = "     this is string example....wow!!!     "
	print( str.lstrip() )
	str = "88888888this is string example....wow!!!8888888"
	print( str.lstrip('8') )
结果：

this is string example....wow!!!

this is string example....wow!!!8888888
#####（14）max(str)
	str = "runoob"
	print ("max:",max(str))
结果：max: u
##### (15) min(str)
	str = "runoob";
	print ("min:" + min(str))
结果：min:b
##### (16) replace(old, new[, max])
	str = "www.w3cschool.cc"
	print ("old address:", str)
	print ("new address:", str.replace("w3cschool.cc", "runoob.com"))
结果：

old address: www.w3cschool.cc

new address: www.runoob.com
##### (17) rfind(str, beg=0 end=len(string))
	str1 = "this is really a string example....wow!!!"
	str2 = "is"
	print (str1.rfind(str2))
	print (str1.rfind(str2, 0, 10))
	print (str1.rfind(str2, 10, 0))
	print (str1.find(str2))
	print (str1.find(str2, 0, 10))
	print (str1.find(str2, 10, 0))
结果：

5

5

-1

2

2

-1
##### (18) rstrip([chars])
	str = "     this is string example....wow!!!     "
	print (str.rstrip())
结果：
     this is string example....wow!!!

##### (19) split(str="", num=string.count(str))
	
	str = "this is string example....wow!!!"
	print (str.split( ))       
	print (str.split('i',1))   
	print (str.split('w'))    
结果：

['this', 'is', 'string', 'example....wow!!!']

['th', 's is string example....wow!!!']

['this is string example....', 'o', '!!!']
##### (20) startswith(substr, beg=0,end=len(string))
	str = "this is string example....wow!!!"
	print (str.startswith( 'this' ))   # 字符串是否以 this 开头
	print (str.startswith( 'string', 8 ))  # 从第九个字符开始的字符串是否以 string 开头
	print (str.startswith( 'this', 2, 4 )) # 从第2个字符开始到第四个字符结束的字符串是否以 this 开头

结果：

True

True

##### (20) strip([chars])
	str = "*****this is **string** example....wow!!!*****"
	print (str.strip( '*' ))

结果:
this is **string** example....wow!!!

##### (21) upper()
	str = "this is string example from runoob....wow!!!";
	print ("str.upper() : ", str.upper())
结果：
str.upper() :  THIS IS STRING EXAMPLE FROM RUNOOB....WOW!!!

##### (22)count()
	str = "this is string example from runoob....wow!!!";
	print(str.count(str))
结果：1

##### (23)endswith
	str = "this is string example from runoob....wow!!!";
	print(str.count(str))
结果：True

##### (24)format()

	str = "this is string example from runoob....wow!!!";
	print (str.format(str))
结果：this is string example from runoob....wow!!!

##### (25)rindex()
	str = "this is string example from runoob....wow!!!";
	print (str.rindex(str))
结果：0

##### (26)
	str = "this is string example from runoob....wow!!!";
	print (str.rsplit(str))
结果:['', '']



### 六. 列表     

#### 1.访问列表中的值
	list = ['red', 'green', 'blue', 'yellow', 'white', 'black']
	print( list[0] )
	print( list[1] )
	print( list[2] )
结果:

red

green

blue
	
	nums = [10, 20, 30, 40, 50, 60, 70, 80, 90]
	print(nums[0:4])
结果：[10, 20, 30, 40]
#### 2.更新列表
	list = ['Google', 'Runoob', 1997, 2000]
	print ("third:", list[2])
	list[2] = 2001
	print ("new third:", list[2])
	list1 = ['Google', 'Runoob', 'Taobao']
	list1.append('Baidu')
	print ("new list:", list1)
结果:

third: 1997

new third: 2001

new list: ['Google', 'Runoob', 'Taobao', 'Baidu']
#### 3.删除列表元素
	list = ['Google', 'Runoob', 1997, 2000]
	print ("list:", list)
	del list[2]
	print ("new list:", list)
结果：

list: ['Google', 'Runoob', 1997, 2000]

new list: ['Google', 'Runoob', 2000]
#### 4.列表脚本操作符
	for x in [1, 2, 3]:
    	print(x, end=" ")
结果：1 2 3
#### 5.列表截取与拼接
	L=['Google', 'Runoob', 'Taobao']
	L[2]
	L[1:]
结果：

'Taobao'

['Runoob', 'Taobao']
#### 6.嵌套列表
	a = ['a', 'b', 'c']
	n = [1, 2, 3]
	x = [a, n]
	x
结果：[['a', 'b', 'c'], [1, 2, 3]]
#### 7.列表函数&方法

##### (1)len(list)
	list1 = ['Google', 'Runoob', 'Taobao']
	print (len(list1))
	list2=list(range(5))
	print (len(list2))
结果：

3

5
##### (2)max(list)
	list1, list2 = ['Google', 'Runoob', 'Taobao'], [456, 700, 200]
	print ("list1 max:", max(list1))
	print ("list2 max:", max(list2))
结果：

list1 max: Taobao

list2 max: 700

##### (3)min(list)
	list1, list2 = ['Google', 'Runoob', 'Taobao'], [456, 700, 200]
	print ("list1 min : ", min(list1))
	print ("list2 min : ", min(list2))

结果：

list1 min :  Google

list2 min :  200
##### (4)list( seq )
	aTuple = (123, 'Google', 'Runoob', 'Taobao')
	list1 = list(aTuple)
	print ("list1: ", list1)
	str="Hello World"
	list2=list(str)
	print ("list2: ", list2)
结果：

list1:  [123, 'Google', 'Runoob', 'Taobao']

list2:  ['H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd']
##### (5)list.append(obj)
	list1 = ['Google', 'Runoob', 'Taobao']
	list1.append('Baidu')
	print ("new list:", list1)
结果：new list: ['Google', 'Runoob', 'Taobao', 'Baidu']
##### (6)list.count(obj)
	aList = [123, 'Google', 'Runoob', 'Taobao', 123];
	print ("123 num : ", aList.count(123))
	print ("Runoob num : ", aList.count('Runoob'))
结果:

123 num :  2

Runoob num :  1
##### (7)list.extend(seq)
	list1 = ['Google', 'Runoob', 'Taobao']
	list2=list(range(5))
	list1.extend(list2)
	print ("new list:", list1)
结果:new list: ['Google', 'Runoob', 'Taobao', 0, 1, 2, 3, 4]
##### (8)list.index(x[, start[, end]])
	list1 = ['Google', 'Runoob', 'Taobao']
	print ('Runoob ', list1.index('Runoob'))
	print ('Taobao', list1.index('Taobao'))
结果:

Runoob  1

Taobao 2
##### (9)list.insert(index, obj)
	list1 = ['Google', 'Runoob', 'Taobao']
	list1.insert(1, 'Baidu')
	print ('new list: ', list1)
结果：new list:  ['Google', 'Baidu', 'Runoob', 'Taobao']
##### (10)list.pop([index=-1])
	list1 = ['Google', 'Runoob', 'Taobao']
	list1.pop()
	print ("new list1 : ", list1)
	list1.pop(1)
	print ("new list2 : ", list1)
结果：

new list1 :  ['Google', 'Runoob']

new list2 :  ['Google']
##### (11)list.remove(obj)
	list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
	list1.remove('Taobao')
	print ("list1 : ", list1)
	list1.remove('Baidu')
	print ("list2: ", list1)
结果:

list1 :  ['Google', 'Runoob', 'Baidu']

list2:  ['Google', 'Runoob']
##### (12)list.reverse()
	list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
	list1.reverse()
	print ("new list: ", list1)
结果:new list:  ['Baidu', 'Taobao', 'Runoob', 'Google']
##### (13)list.sort( key=None, reverse=False)
	aList = ['Google', 'Runoob', 'Taobao', 'Facebook']
	aList.sort()
	print ( "List : ", aList)
结果：
List :  ['Facebook', 'Google', 'Runoob', 'Taobao']
##### (14)list.clear()
	list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
	list1.clear()
	print ("new list: ", list1)
结果：
new list:  []
##### (15)list.copy()
	list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
	list2 = list1.copy()
	print ("list2 : ", list2)
结果：list2 :  ['Google', 'Runoob', 'Taobao', 'Baidu']

### 七. 元组

#### 1.访问元组
	tup1 = ('Google', 'Runoob', 1997, 2000)
	tup2 = (1, 2, 3, 4, 5, 6, 7 )
	print ("tup1[0]: ", tup1[0])
	print ("tup2[1:5]: ", tup2[1:5])
结果:

tup1[0]:  Google

tup2[1:5]:  (2, 3, 4, 5)
#### 2.修改元组
	tup1 = (12, 34.56)
	tup2 = ('abc', 'xyz')
	tup3 = tup1 + tup2
	print (tup3)
结果：
(12, 34.56, 'abc', 'xyz')
#### 3.删除元组
	tup = ('Google', 'Runoob', 1997, 2000)
	print (tup)
	del tup
	print ("new tup : ")
	print (tup)	
结果：

	Traceback (most recent call last):
	  File "<stdin>", in <module>
	NameError: name 'tup' isn't defined
#### 4.元组运算符
	len((1, 2, 3))	
结果:3

	(1, 2, 3) + (4, 5, 6)
结果：(1, 2, 3, 4, 5, 6)

	('Hi!',) * 4	
结果：('Hi!', 'Hi!', 'Hi!', 'Hi!')

	3 in (1, 2, 3)
结果：True

	for x in (1, 2, 3):
	    print(x)
结果:

1

2

3
#### 5.元组索引，截取
	tup = ('Google', 'Runoob', 'Taobao', 'Wiki', 'Weibo','Weixin')
	tup[1]
	tup[-2]
	tup[1:]
	tup[1:4]
结果：

'Runoob'

'Weibo'

('Runoob', 'Taobao', 'Wiki', 'Weibo', 'Weixin')

('Runoob', 'Taobao', 'Wiki')
#### 6.元组内置函数
##### (1)len(tuple)
	tuple1 = ('Google', 'Runoob', 'Taobao')
	len(tuple1)
结果：3
##### (2)max(tuple)
	tuple2 = ('5', '4', '8')
	max(tuple2)
结果：'8'
##### (3)min(tuple)
	tuple2 = ('5', '4', '8')
	min(tuple2)
结果：'4'
##### (4)tuple(iterable)
	list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
	tuple1=tuple(list1)
	tuple1
结果：('Google', 'Taobao', 'Runoob', 'Baidu')

##### (5)count()
	list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
	print(list1.count('Taobao'))
结果：1

##### (6)index()
	list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
	print(list1.index('Taobao'))
结果：1

### 八. 字典
#### 1.访问字典中的值
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	print ("dict['Name']: ", dict['Name'])
	print ("dict['Age']: ", dict['Age'])
结果:

dict['Name']:  Runoob

dict['Age']:  7
#### 2.修改字典
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	 
	dict['Age'] = 8               # 更新 Age
	dict['School'] = "123"  # 添加信息
	print ("dict['Age']: ", dict['Age'])
	print ("dict['School']: ", dict['School'])
结果：

dict['Age']:  8

dict['School']:  123
#### 3.删除字典元素
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} 
	del dict['Name'] # 删除键 'Name'
	dict.clear()     # 清空字典
	del dict         # 删除字典
	print ("dict['Age']: ", dict['Age'])
	print ("dict['School']: ", dict['School'])
结果:
	Traceback (most recent call last):
	  File "<stdin>", in <module>
	TypeError: 'type' object isn't subscriptable

#### 4.字典键的特性
	dict = {'Name': 'Runoob', 'Age': 7, 'Name': 'cainiao'}
	print ("dict['Name']: ", dict['Name'])
结果：
dict['Name']:  cainiao

#### 5.字典内置函数&方法
##### (1)len(dict)
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	len(dict)
结果：3
##### (2)str(dict)
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	str(dict)
结果："{'Age': 7, 'Name': 'Runoob', 'Class': 'First'}"
##### (3)type(variable)
	dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	type(dict)
结果：<class 'dict'>
##### (4)radiansdict.clear()
	dict = {'Name': 'Zara', 'Age': 7}
	print ("dict len: %d" %  len(dict))
	dict.clear()
	print ("new dict len: %d" %  len(dict))
结果：

dict len: 2

new dict len: 0
##### (5)radiansdict.copy()
	dict1 = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
	dict2 = dict1.copy()
	print ("new list: ",dict2)
结果：
new list:  {'Age': 7, 'Name': 'Runoob', 'Class': 'First'}
##### (6)radiansdict.fromkeys() {不支持}
##### (7)radiansdict.get(key, default=None)
	dict = {'Name': 'Runoob', 'Age': 27}
	print ("Age  : %s" %  dict.get('Age'))
	print ("Sex  : %s" %  dict.get('Sex', "NA"))
结果：

Age  : 27

Sex  : NA
##### (8)key in dict
	dict = {'Name': 'Runoob', 'Age': 7}
	# 检测键 Age 是否存在
	if  'Age' in dict:
	    print("Age  in")
	else :
	    print("Age not in")
	# 检测键 Sex 是否存在
	if  'Sex' in dict:
	    print("Sex in")
	else :
	    print("Sex not  in")
	# 检测键 Age 是否存在
	if  'Age' not in dict:
	    print("Age not in")
	else :
	    print("Age  in")
结果：

Age  in

Sex not  in

Age  in
##### (9)radiansdict.items()
	dict = {'Name': 'Runoob', 'Age': 7}
	print ("Value : %s" %  dict.items())
结果：Value : dict_items([('Name', 'Runoob'), ('Age', 7)])
##### (10)radiansdict.keys()
	phone_book={'sam':'1234','tom':'5678'}
	phone_book.keys()
结果：dict_keys(['sam', 'tom'])
##### (11)radiansdict.setdefault(key, default=None)
	d={}
	d.setdefault('name')
	d
结果：{'name': None}
##### (12)radiansdict.update(dict2)
	dict = {'Name': 'Runoob', 'Age': 7}
	dict2 = {'Sex': 'female' }
	dict.update(dict2)
	print ("new dict : ", dict)
结果：new dict :  {'Sex': 'female', 'Name': 'Runoob', 'Age': 7}
##### (13)radiansdict.values()
	dishes = {'eggs': 2, 'sausage': 1, 'bacon': 1, 'spam': 500}
	keys = dishes.keys()
	values = dishes.values()
	n = 0
	for val in values:
	    n += val
	print(n)
结果：504
##### (14)pop(key[,default])
	site= {'name': 'cainiao', 'alexa': 10000, 'url': 'www.runoob.com'}
	pop_obj=site.pop('name')
	print(pop_obj)
结果：cainiao
##### (15)popitem()
	site= {'name': 'cainiao', 'alexa': 10000, 'url': 'www.runoob.com'}
	pop_obj=site.popitem()
	print(pop_obj)  
	print(site)
结果：

('name', 'cainiao')

{'alexa': 10000, 'url': 'www.runoob.com'}


### 九. 集合

#### 1.添加元素
	thisset = set(("Google", "Runoob", "Taobao"))
	thisset.add("Facebook")
	print(thisset)
结果：{'Google', 'Facebook', 'Runoob', 'Taobao'}

	thisset = set(("Google", "Runoob", "Taobao"))
	thisset.update({1,3})
	print(thisset)
结果：{'Runoob', 1, 'Google', 3, 'Taobao'}
#### 2.移除元素
	thisset = set(("Google", "Runoob", "Taobao"))
	thisset.remove("Taobao")
	print(thisset)
结果：{'Google', 'Runoob'}

	thisset = set(("Google", "Runoob", "Taobao"))
	thisset.discard("Facebook")
	print(thisset)
结果：{'Google', 'Runoob', 'Taobao'}

	thisset = set(("Google", "Runoob", "Taobao", "Facebook"))
	x = thisset.pop()
	print(x)
结果：Google
#### 3.计算集合元素个数
	thisset = set(("Google", "Runoob", "Taobao"))
	len(thisset)
结果：3
#### 4.清空集合
	thisset = set(("Google", "Runoob", "Taobao"))
	thisset.clear()
	print(thisset)
结果：set()
#### 5.判断元素是否在集合中存在
	thisset = set(("Google", "Runoob", "Taobao"))
	"Runoob" in thisset
结果：True
#### 6.集合内置方法完整列表
##### (1)add()
	fruits = {"apple", "banana", "cherry"}
	fruits.add("orange") 
	print(fruits)
结果：{'orange', 'apple', 'banana', 'cherry'}
##### (2)clear()
	fruits = {"apple", "banana", "cherry"}
	fruits.clear()
	print(fruits)
结果：set()
##### (3)copy()
	fruits = {"apple", "banana", "cherry"}
	x = fruits.copy()
	print(x)
结果：{'banana', 'cherry', 'apple'}
##### (4)difference()
	
	x = {"apple", "banana", "cherry"}
	y = {"google", "microsoft", "apple"}
	z = x.difference(y) 
	print(z)
结果：{'banana', 'cherry'}
##### (5)difference_update()
	x = {"apple", "banana", "cherry"}
	y = {"google", "microsoft", "apple"}
	x.difference_update(y) 
	print(x)
结果：{'banana', 'cherry'}
##### (6)discard(value)
	fruits = {"apple", "banana", "cherry"}
	fruits.discard("banana") 
	print(fruits)
结果：{'cherry', 'apple'}
##### (7)intersection()
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "apple"}
	z = x.intersection(y) 
	print(z)
结果：{'apple'}
##### (8)intersection_update()
	x = {"apple", "banana", "cherry"} 
	y = {"google", "runoob", "apple"}
	x.intersection_update(y) 
	print(x)
结果：{'apple'}
##### (9)isdisjoint()
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "facebook"}
	z = x.isdisjoint(y) 
	print(z)
结果：True
##### (10)issubset()
	x = {"a", "b", "c"}
	y = {"f", "e", "d", "c", "b", "a"}
	z = x.issubset(y) 
	print(z)
结果：True
##### (11)issuperset()
	x = {"f", "e", "d", "c", "b", "a"}
	y = {"a", "b", "c"}
	z = x.issuperset(y) 
	print(z)
结果：True
##### (12)pop()
	fruits = {"apple", "banana", "cherry"}
	fruits.pop() 
	print(fruits)
结果：{'cherry', 'apple'}
##### (13)remove()
	fruits = {"apple", "banana", "cherry"}
	fruits.remove("banana") 
	print(fruits)
结果：{'cherry', 'apple'}
##### (14)symmetric_difference()
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "apple"}
	z = x.symmetric_difference(y) 
	print(z)
结果：{'google', 'runoob', 'banana', 'cherry'}
##### (15)symmetric_difference_update()	
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "apple"}
	x.symmetric_difference_update(y) 
	print(x)
结果：{'google', 'runoob', 'banana', 'cherry'}
##### (16)union()
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "apple"}
	z = x.union(y) 
	print(z)
结果：{'banana', 'cherry', 'runoob', 'google', 'apple'}
##### (17)update()
	x = {"apple", "banana", "cherry"}
	y = {"google", "runoob", "apple"}
	x.update(y) 
	print(x)
结果：{'banana', 'cherry', 'runoob', 'google', 'apple'}
