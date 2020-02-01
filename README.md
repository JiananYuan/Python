# Python

![](http://ipcounter.ihcr.top/)

1. print("hello, python")   # 这是一个注释

2. 无需限定类型，嵌入输出时逗号隔开

		university = "Shenzhen University"
		stuNum = "30000"
		
		print("the", university, "has", stuNum);

另一种输出方式：

		my_name = "Andy Yuan"
		
		print(f"my name is {my_name}")

----

	print("Mary had a little lamb.")
	print("Its fleece was white as {}.".format('snow'))
	print('.' * 10)  # what'd that do?
	
	a = "C"
	b = "h"
	c = "i"
	d = "n"
	e = "a"
	
	print(a + b + c, end = ' ')
	print(d + e)

3.格式化输出：

	formatter = "{} {} {} {}"
	
	print(formatter.format(1,2,3,4))
	
	print(formatter.format("Andy","Nempt","Oliver","Olivia"))

4.获取输入字符串

 age = input()

交互设计：


	age = int(input("how old are you "))
	
	print(f"After 20 years, you'll be {age + 20} years old!")

5.参数、解包和变量

	from sys import argv
	
	script = argv[0]
	first = argv[1]
	second = argv[2]
	third = argv[3]
	
	print("The Script is called: ",script)
	print("The first argument is: ",first)
	print("The second argument is: ",second)
	print("The third argument is: ",third)

6.人机交互示例

	from sys import argv
	
	script = argv[0]
	user_name = argv[1]
	
	prompt = '>'
	
	print(f"Hi, {user_name}, I'm the {script} script.")
	print(f"Do you like me, {user_name}?")
	
	likes = input(prompt)

7.文件读取：
	
	from sys import argv
	
	script = argv[0]
	filename = argv[1]
	
	txt = open(filename)
	
	print(f"here's your file {filename}: ")
	print(txt.read())

8.文件综合操作：

交互记事本：

	from sys import argv

	script = argv[0]
	filename = argv[1]
	
	print(f"we are going to erase {filename}.")
	print("If you don't want that, hit Ctrl-C(^C).")
	print("If you do want that, hit RETURN ")
	
	input("?")
	
	print("opening file...")
	target = open(filename,'w')
	
	print("Truncating the file. Goodbye!")
	
	target.truncate()
	
	print("Now I'm going to ask you for 3 lines")
	
	line1 = input("line 1: ")
	line2 = input("line 2: ")
	line3 = input("line 3: ")
	
	print("I'm going to write these to the file.")
	
	target.write(line1)
	target.write("\n")
	target.write(line2)
	target.write("\n")
	target.write(line3)
	target.write("\n")
	
	print("And finally, we close it!")
	target.close()

拷贝文件：

	from sys import argv
	from os.path import exists
	
	script = argv[0]
	fromPath = argv[1]
	toPath = argv[2]
	
	print(f"Copying from {fromPath} to {toPath}...")
	
	inFile = open(fromPath)
	inData = inFile.read()
	
	print(f"The input file is {len(inData)} bytes long")
	
	print(f"Does the output file exist? {exists(toPath)}")
	
	outFile = open(toPath,'w')
	outFile.write(inData)
	
	outFile.close()
	inFile.close()

8.函数示例：

	def print_two(*args):
	    arg1, arg2 = args;
	    print(f"arg1 : {arg1}, arg2 : {arg2}")
	
	def print_two_again(arg1,arg2):
	    print(f"arg1 : {arg1}, arg2 : {arg2}")
	
	def print_one(arg1):
	    print(f"arg1 : {arg1}")
	
	def print_none():
	    print("I got none'.")
	
	print_two("Andy","Jae")
	print_two("Andy","Jae")
	print_one("First!")
	print_none()

9.列表：

	a = [1,2,3,4,5]
	b = ['a','b','c','d','e']
	c = [1,'aa',2,'bb',3]
	
	for number in a:
	    print(number,end = ' ')
	
	print()
	
	for item in c:
	    print(item,end = ' ')
	
	print()
	
	copy = []
	
	for item in b:
	    copy.append(item)
	
	print(copy)

又一个例子：

	ten_things = "apple banana cat dog ele fruit goge hit item jack"

	stuff = ten_things.split()
	more_things = ["kit","lemon","man","nose","oil","pack","quit","run","speak","tick"]
	
	while len(stuff) != 15:
	    next_one = more_things.pop()
	    stuff.append(next_one)
	
	print(stuff)
	
	print(stuff[1])
	print(stuff[-1])
	print(stuff.pop())
	print(' '.join(stuff))
	print('#'.join(stuff[3:5]))

10.字典：

字典，列表，元组，集合是python常用数据结构

迭代器：

	import sys
	a = [1,2,3,4]
	it = iter(a)
	
	while True:
	    try:
	        print(next(it))
	    except StopIteration:
	        sys.exit()

典型数据结构使用实例：

List1：

	a = [66.25, 333, 333, 1, 1234.5]
	print(a.count(333),a.count(66.25),a.count('x'))
	
	a.insert(2,-1)
	a.append(333)
	print(a)
	
	print(a.index(333))
	a.remove(333)
	print(a)
	a.reverse()
	print(a)
	a.sort()
	print(a)

List2：（列表推导式）

	vec = [2,4,6]
	new_vec = [3*x for x in vec if x >= 4]
	print(new_vec)

List3：

	# 矩阵转置
	a = []
	b = [
	    [1,2,3,4],
	    ['a','b','c','d'],
	    ['+','-','*','/'],
	]
	
	for i in range(4):
	    tmp = []
	    for row in b:
	        tmp.append(row[i])
	    a.append(tmp)
	
	print(a)

Set:

	a = {"abc","def","ghi","abc"}
	print(a)
	
	print('abc' in a)
	
	b = set('abcabc')
	print(b)
	c = set('abcd')
	print(c)
	
	print(c-b, b|c, b&c, b^c) # 集合相对补，并集，交集，对称差

字典：

	tel = {'jack':4098, 'sape': 4139}
	print(tel)
	print(tel['jack'])
	del tel['jack']
	# print(tel['jack'])
	print(tel)
	print(tel.keys())
	print(tel.values())






11.面向对象

1. 构造函数

		class Song(object):
		    def __init__(self,lyrics):
		        self.lyrics = lyrics
		
		    def sing_me_a_song(self):
		        for line in self.lyrics:
		            print(line)
		
		happy_bday = Song(["1","2","3"])
		
		happy_bday.sing_me_a_song()

2. 继承

	class Parent(object):
    def override(self):
        print("Parent Override()")

    def implicit(self):
        print("Parent implicit")

    def altered(self):
        print("Parent altered()")

class Child(Parent):
    def override(self):
        print("Child override()")

    def altered(self):
        print("Child, before")
        super(Child, self).altered()
        print("Child, after")

	dad = Parent()
	son = Child()
	
	dad.implicit()
	son.implicit()
	
	dad.override()
	son.override()
	
	dad.altered()
	son.altered()

3.组合

	
    def override(self):
        print("Other override")

    def implicit(self):
        print("Other implicit")

    def altered(self):
        print("Other altered")

	
    def __init__(self):
        self.other = Other()

    def implicit(self):
        self.other.implicit()

    def override(self):
        print("override")

    def altered(self):
        print("before")
        self.other.altered()
        print("after")

	son = Child()
	
	son.implicit()
	son.override()
	son.altered()

4.访问设置：

	class Site:
	    def __init__(self,name,url):
	        self.name = name
	        self.url = url
	
	    def who(self):
	        print("name: ",self.name)
	        print("url: ",self.url)
	
	    def __foo(self):
	        print("It's private")
	
	    def foo(self):
	        print("It's public")
	
	x = Site("JNY","github.plus")
	x.who()
	x.foo()
	x.__foo()

5.运算符重载：

	class Vector:
	    def __init__(self,a,b):
	        self.a = a
	        self.b = b
	
	    def __str__(self):
	        return "Vector (%d, %d)" % (self.a, self.b)
	
	    def __add__(self, other):
	        return Vector(self.a + other.a, self.b + other.b)
	
	a = Vector(2,10)
	b = Vector(5,-2)
	print(a+b)

12.格式化输出：

	>>> for x in range(1, 11):
	...     print(repr(x).rjust(2), repr(x*x).rjust(3), end=' ')
	...     # 注意前一行 'end' 的使用
	...     print(repr(x*x*x).rjust(4))
	...
	 1   1    1
	 2   4    8
	 3   9   27
	 4  16   64
	 5  25  125
	 6  36  216
	 7  49  343
	 8  64  512
	 9  81  729
	10 100 1000
	
	>>> for x in range(1, 11):
	...     print('{0:2d} {1:3d} {2:4d}'.format(x, x*x, x*x*x))
	...
	 1   1    1
	 2   4    8
	 3   9   27
	 4  16   64
	 5  25  125
	 6  36  216
	 7  49  343
	 8  64  512
	 9  81  729
	10 100 1000

pickle模块：

写入：

	import pickle
	data = {
	    'a': [1, 2.0, 3, 4+6j],
	         'b': ('string', u'Unicode string'),
	         'c': None
	}
	
	b = [1,2,3]
	b.append(b)
	
	out = open("OBS.pkl",'wb')
	pickle.dump(data,out)
	
	pickle.dump(b,out,-1)
	
	out.close()

读出：

	import pprint, pickle
	
	inn = open('OBS.pkl','rb')
	
	data1 = pickle.load(inn)
	pprint.pprint(data1)
	
	data2 = pickle.load(inn)
	pprint.pprint(data2)
	
	inn.close()

13.异常处理：

	while True:
	    try:
	        x = int(input())
	        break
	    except ValueError:
	        print("输入的不是数字")

1. try-except-else 语句：

		import sys
		for arg in sys.argv[1:]:
		    try:
		        f = open(arg,'r')
		    except IOError:
		        print('cannot open',arg)
		    else:
		        print(arg,'has',len(f.readlines()),'lines')
		        f.close()

2. try-except-else-finally语句

3. 抛出异常：

		x = 10
		if x > 5:
		    raise Exception('x 不能大于5. x值为：{}'.format(x))

4. 自定义异常：

		class MyError(Exception):
		    def __init__(self,value):
		        self.value = value
		    def __str__(self):
		        return repr(self.value)
		
		try:
		    raise MyError(2*2)
		except MyError as e:
		    print(e.value)

5. with预定义清理行为

		with open("txt.txt") as f:
		    for line in f:
		        print(line, end="")


14.一些标准库：

文件通配符：

	>>> import glob
	>>> glob.glob('*.py')
	['primes.py', 'random.py', 'quote.py']

字符串正则匹配：

	>>> import re
	>>> re.findall(r'\bf[a-z]*', 'which foot or hand fell fastest')
	['foot', 'fell', 'fastest']
	>>> re.sub(r'(\b[a-z]+) \1', r'\1', 'cat in the the hat')
	'cat in the hat'

简单功能：

	>>> 'tea for too'.replace('too', 'two')
	'tea for two'

生成随机值：

	>>> import random
	>>> random.choice(['apple', 'pear', 'banana'])
	'apple'
	>>> random.sample(range(100), 10)   # sampling without replacement
	[30, 83, 16, 4, 8, 81, 41, 50, 18, 33]
	>>> random.random()    # random float
	0.17970987693706186
	>>> random.randrange(6)    # random integer chosen from range(6)
	4

日期和时间：

	>>> # dates are easily constructed and formatted
	>>> from datetime import date
	>>> now = date.today()
	>>> now
	datetime.date(2003, 12, 2)
	>>> now.strftime("%m-%d-%y. %d %b %Y is a %A on the %d day of %B.")
	'12-02-03. 02 Dec 2003 is a Tuesday on the 02 day of December.'
	
	>>> # dates support calendar arithmetic
	>>> birthday = date(1964, 7, 31)
	>>> age = now - birthday
	>>> age.days
	14368

