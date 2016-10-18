#1.Python文件类型
源代码（以“py'为扩展名）

字节代码
.py源文件编译后生成扩展名为"pyc"的文件
编译方法：
> 1. importpy_compile
> 2. py_compile.compile("hello.py")

优化代码（经过优化的源文件,扩展名为".pyo")
> python -O -m py_compile helllo.py

**以上三种均可直接运行**
#2.Python变量
##变量命名
变量名有字母,数字,下划线组成
不能使用关键字
##变量赋值（变量声明和定义的过程）
    a=1
    id(a)	1440076240
	a=23
	id(a)	1440076592
	b=a
	id(b)	1440076592
和C语言不一样，每个数值占用一块内存，变量重新赋值，会新占用一块内存。不同的变量可以占用同一块内存。
#3.运算符与表达式 
##1.Python运算符包括
###赋值运算符（=  += -= *=  /= %=)
    a=100
    a-=50	50
    a+=50	100
    a*=2	200
    a/=4	50
    a%=3	2
###算数运算符（+ - * / // % >> << | ^ & ~)
     3+3	6
     6-4	2
     5*2	10
     5/2	2.5
     5//2	2	(整除)
     5%2	1	(取余)
	 3**4	81	（指数）
	 4<<2	16	（右移2位）
	 4>>1	1	（左移2位）
	 4|3	7	（按位或）
	 4^4	0	（按位异或）
	 4&5	4	（按位与）
	 ~0		-1	（按位取反）
###关系运算符(< > <= >= != ==)
	1<2		True
	3>4		False
	4<=3	False
	4>=3	True
	3!=4	True 
	3==3	True
###逻辑运算符(and or not)
	1>2 and 2<3		False
	5>2 and 2<3		True
	1>2 or 2<3		True
	1>2 or 2>3		False
	not 1>2			True
#4.数据类型
##数字
###整型(int)
	num1=123
	type(123)	<type 'int'>
	type(num1)	<type 'int'>
###浮点型(float)
	f1=1.685466
	type(f1)			<type 'float'>
	type(1.685466)		<type 'float'>
###复数(complex)
	c=3.14j
	a=2+4j
	type(a)		<type 'complex'>
##序列
序列的两个主要特点是索引操作符和切片操作符
1. 索引操作符可以从序列中抓取一个特定项目
2. 切片操作符可以获取序列的一个切片

    str1='abcde'
    str1[1]		'b'
	str1[1:4]	'bcd'
	str1[::]	'abcde'
	str1[::2]	'ace'
序列的基本操作

- len()				求序列长度
- +					连接2个序列
- *					重复序列元素
- in					判断元素是否在序列中
- max()				返回最大的值
- min()				返回最小的值
- cmp(tuple1, tuple2)	比较2个序列值是否相同

	    str1="abc"
	    len(str1)		3
	    str2="asd"
	    str1+str2		'abcasd'
	    str1*5			'abcabcabcabcabc'
	    'c' in str1		True
	    max(str1)		'c'
	    min(str1)		'a'
	    cmp(str1,str2)	False

###字符串
	str1='123'
	type(str1)	<type 'str'>
	str2="123"
	type(str2)	<type 'str'>
	字符串有'时，可以用"格式
	字符串有"时,可以用\"转义
	""" 或 '''可以友好显示 
###元组
通过圆括号中用逗号分割的项目定义，被定义的元组的值不会改变，即元素值不能改变。

    t=("hello", 30, "hehe")
    t[0]		'hello'
	t1=()		空元组
	t2=(1)		t2实际为int
	t2=(1,)		包含一个元素的元组
	t[0]=123	Error
	name,age,str1=t
	name		'hello'
	age			30
	str1		'hehe'
	a,b,c=1,2,3	或者	a,b,c=(1,2,3)
	a			1
	b			2
	c			3
###列表
用[]表示列表，以，分隔元素，元素可变

####列表的操作
#####1.取值
#####2.切片和索引
- list[]
#####3.添加
- list.appen()
#####4.删除
- del(list[])
- list.remove(list[])
#####5.修改		
- list[]=x
#####6.查找		
- var in list

    	lista=['a',24,'hehe']
    	lista[0]='b]
		lista		['b',24,'hehe']
    	lista.appen("123")
    	lista		['b',24,'hehe','123']
    	lista.remove(lista[3])
    	lista		['b',24,'hehe']
    	del(lista[2])
    	lista		['b',24']

##字典
字典是python中的映射类型（哈希表），字典对象是可变的，但是字典的键必须使用不可变对象，键值可以使用不同类型。
###创建
####1.{}
	dic1={'name':'z','age':22}
	dic1['name']		'z'
	dic1['age']		22
	name='t'
	dic2={name:'z','age':22}
	name			't'		//name是一个变量，键值可以是变量或字符串
	age				Error
	dic2			{'t':'z','age':22}
####2.使用工厂方法dict()
	fdict=dict(['x',1],['y,2])	使用字典生成字典，效率低
####3.内建方法：fromkeys()
- 字典中的元素具有相同的值，默认为None

    	dict1={}.fromkeys(('x','y'),-1)

###遍历
	for k in dic1:
		print(k)	
	
	//遍历键
	for k in dic1:
	    dic1[k]

	//遍历键值
###更新
- 内建的update()方法	可以将整个字典的内容拷贝到另一个字典中
- 增加键值对	dict1['zzz']='hello'
- 修改键值	dict1['zzz']='world'
- 删除键值对
	- del dict1['a']		删除键值为'a'的元素
	- dict1.pop('a')		删除并返回键为'a'的元素
	- dict1.clear()		删除字典所有元素
	- del	dict1			删除整个字典

#5.流程控制

##逻辑运算符
###and
	True  and  True		True
	Ture  and  False	False
	False and  False	False
###or
	True  and  True		True
	Ture  and  False	True
	False and  False	False
###not
	not  True			False
	not  False			True

##if else
逻辑值包含两个值：

- True:表示非空的量，所有非零数
- False：表示0，None，空的量等

		if expression:
		    statement(s)
		else:
		    statement(s)
		//四个空格缩进

		if expression:
		    statement(s)
		elif:
		    statement(s)
		else:
		    statement(s)

##(switch)
> Python中并没有switch,可以用字典实现

	def add(x,y):
		return x+y

	def  sub(x,y):
		return x-y
	
	def  mul(x,y):
		return x*y
	
	def  div(x,y):
		return x/y

	operator={"+":add,"-":sub,"*":mul,"/":div}
	def f(x,o,y):
		print(operator.get(o)(x,y))
	f(3,"+",2)
	5

	result={
			"+":x+y,
			"-":x-y,
			"*":x*y,
			"/":x/y
		}
	print(result.get(operator))

##for循环
	for  iterating_var  in  sequence:
		    	statements(s)
	如果一个序列包含一个表达式列表，它是第一个执行。

	for  x  in  range(100)
		print(x)
	else:
		print("ending")
	/*for循环正常结束时(执行到末尾），会执行else
	  遇到break，Ctrl+C等非正常结束时，不运行else
	*/

- range(i,j[,步进值])
	- i为初始数值,不选默认为0
	- j位终止数值，但不包含在范围内
	- 步进值不选，默认为1
- break  跳出循环
- continue  跳出本次循环
- pass  不执行任何语句，起站位作用
- exit()  跳出程序

##遍历
###for遍历序列
###序列本身的偏移指数(索引)
	s="hello"
	for  x  in  range(len(s))
		print(s[x])
###遍历字典
	for  x  in  d:
		print(d[x])//遍历键
	for  k,v  in  d.items():
		print(k)//遍历键
		print(v)//遍历键值

##while
	while  expression:
		statement(s)

#6.函数
	def  函数名(参数列表):
		函数体
		//可以没有参数
	调用函数一般形式:
		函数名(参数表)

##形参
在定义函数时，函数后面的变量名称叫做"形式参数"(形参)

##实参
在调用函数时，函数后面的变量名称叫做"实际参数"(实参)

>实参和形参应该对应

##缺省参数
	def 函数名(variale1,variable2=value)
		函数体

##变量的作用域

###局部变量 
只能在程序的特定部分使用的变量

###全局变量
整个程序都可以使用的变量
>重名的变量，局部变量会屏蔽全局变量
>可以将局部变量加global强制声明为全局变量，但在函数体外必须被调用

##返回值

	def 函数名():
		函数体
		return 返回值

返回值可以是任何类型,返回之后的代码不会执行,没有返回值，函数返回None

##多类型传值
	def f(name="name", age=0)
		print("name=%s",name)
		print("age=%d",age)
	t=(30,'z')
	f(*t)	name:30	age:'z'
	d={'age':30, 'name':'z'} 
	f(name='z',age=30)
	name='z'	age=30
	f(age=30,name='z')
	name='z'	age=30
	f(**d)
	name='z'	age=30
	d['age']=31
	f(**d)
	name='z'	age=31
	d1={'a':30,'n':'z'}
	f(**d1)		error
	f(d1['n'],f['a'])
	name='z'	age=31

##处理多余参数
	def  f(x, *args):
		print x
		print args
	f(1)
	1
	()
	f(1,2,3)
	1
	(2,3)
	f(x=4)
	4
	()
	f(x=4,y=5)	error

	def  f(x,*args,**wargs)
		print  x
		print	args
		print	wargs
	f(1)
	1
	()
	{}
	f(1,2,3,4,5)
	1
	(2,3,4,5)
	{}
	f(x=1)
	1
	()
	{}
	f(x=1,y=2)
	1
	()
	{'y':2}
	f(1,2,3,4,5,x=10,y=20,z=30)	error
	f(1,2,3,4,5,y=20,z=30)
	1
	(2,3,4,5)
	{'y':20,'z':30}

##lambda
>lambda函数是一种快速定义单行的最小函数。

	def  f(x,y)
		return x*y
	f(2,3)
	6
	g = lambda  x,y:x*y
	g(2,3)
	6

- 可以让代码更加精简
- 不需要考虑命名的问题
- 让代码更容易理解

lambda  参数：函数，返回一个对象

###reduce
逐次操作List里面的每项，接收参数2个，最后返回的为一个结果
	l=range(1,6)
	def  f(x,y)
		return x*y
	reduce(f,l)
	120

	f = lambda x,y:x*y
	reduce(f,l)
	120

	reduce(lambda x,y:x*y , l)
	120

##内置函数
- abs()	绝对值
- min()	最小值
- max()	最大值
- len()	序列长度
- divmod()	求商和模
- pow()	
- round()

- callable()		测试函数是否可被调用
- isinstance()	测试对象是什么类型

- cmp()			比较两个字符串
- range()		快速生成一个序列
- xrange()		

- type()			测试对象类型
- tuple()		转换成元组
- list()			转换成列表
- str()			转换成字符串
- int()			转换成int
- float()		转换成flaot
- complex()		转换成complex

###string函数
1. str.capitalize()	字符串首字母大写

		s="hello,world"
		s.capitalize()

2. str.replace()	字符串替换

		s.replace("hello","good")
		'good world'
		s
		'hello world'//没有修改字符串
		s.replace('o','x',2)
		'hellx,wxrld'

3. str.split()	切割

		ip="192.168.1.1"
		ip.split('.')
		['192','168','1','1']
		ip.split('.',2)
		['192','168',1.1']

导入模块的方式:

		import string
		string.replace(s, 'hello','good')

###序列处理函数
1. len()
2. max()
3. min()
4. filter()
5. zip()
6. map()
7. reduce()


		def  f(x):
			if x > 5:
				return True
	
		l=range(10)
		filter(f,l)
		[6,7,8,9]
	
		name=['a','b','c']
		age[2,3,4]
		tel=['133','112','111']
		zip(name,age,tel)
		[('a',2,'133'),('b',3,'112'),('c',4,'111')]
		map(None,name,age,tel)
		[('a',2,'133'),('b',3,'112'),('c',4,'111')]
		test=[1,2]
		zip(name,age,tel,test)
		[('a',2,'133',1),('b',3,'112',2)]
		map(None,name,age,tel,test)
		[('a',2,'133',1),('b',3,'112',2),('c',3,'111',None)]
		a=[1,2,3]
		b=[4,5,6]
		def mf(x,y):
			return x*y
		map(mf,a,b)
		[4,10,18]

#7.模块

> 当脚本被导入运行时，就称为模块。模块名与脚本的文件名相同。

> 模块导入时，会产生.pyc编译文件，方便下次导入
	new.py中：
	import  cal.py
	print( cal.add(1,2) )

	#python new.py
	3

##7.1 \_\_name\_\_

	在ncal.py中
	加入print( __name__ )
	python cal.py
	main
	python new.py
	cal

防止调用模块时，模块的内容反复执行

	if  __name__ == "__main__"
		模块调用的内容

	在cal.py中加入
	if  __name__ == "__main__"
		add(1,2)
	在new.py中加入
	add(2,3)

	#python cal.py
	3
	#python new.py
	5

##7.2模块导入顺序

> 先找当前目录，再找系统目录

#8.包
> python的模块可以按目录组织为包


**创建一个包的步骤：**

1. 建立一个名字为包名字的文件夹
2. 在该文件夹下创建一个__ init __.py文件（内容可以为空）
3. 根据需要在该文件夹下存放脚本文件，已编译扩展文件及子包

	在test文件夹下加入__ init __.py
	import cal

	import cal as c
	c.add(1,2)
	3

	from cal import add
	add(1,4)
	5

#9.正则表达式

> 正则表达式模式会被编译成一系列的字节码，然后由用C编写的匹配引擎执行

> 使用时，需要import re

	import  re
	s = r'abc'
	re.findall(s,"aaaaaaaaaaaaa")
	[]
	re.findall(s,"abcaaaaaaaaaaa")
	['abc']
	re.findall(s,"abcaaabcaaaaaaa")
	['abc','abc']

##字符匹配

###普通字符
> 大多数字母和字符一般都会和自身匹配

###元字符

- []

>指定一个字符集，可以匹配其中任意一个字符

	st = "top tip twp tep"
	res = r"t[io]p"
	re.findall(res,st)
	['top','tip']

> 元字符在字符集中不起作用

	r = "t[abc$]"
	re.findall(r,'ta')
	['ta']
	re.findall(r,'tax')
	['ta']
	re.findall(r,'t$')
	['t$']
	
	r = "t[abc^]"
	re.findall(r,t^']
	['t^']
	r = "t[^abc]"	##[^...]------不匹配字符集
	re.findall(r,"ta tb tc td")
	['td']

	r = r"x[0123456789]x"
	re.findall(r,'x1x,x2x')
	['x1x','x2x']

	[0123456789]等价于[0-9]
	[a-z]小写字母
	[A-Z]大写字母
	[a-zA-Z0-9]字母或数字

- ^

> 匹配行首

	s = "hello world"
	r = r"^hello"
	re.findall(r,s)
	['hello']
	s = "world world"
	re.findall(r,s)
	[]

- $

> 匹配行尾

	s = "world,hello boy"
	r = r"boy$"
	re.findall(r,s)
	['boy']

- \

	- \d		匹配任何十进制数：相当于类[0-9]
	- \D		匹配任何非数字字符：相当于[^0-9]
	- \s		匹配任何空白字符：相当于[\t\n\r\f\v]
	- \S		匹配任何非空白字符：相当于[^\t\n\r\f\v]
	- \w		匹配任何字母数字字符：相当于[a-zA-Z0-9]
	- \W		匹配任何非字母数字字符：相当于[^a-zA-Z0-9]

> 后面加不同的字符表示不同特殊意义，也可以用于取消所有的元字符

- *

> 指定前一个字符（字符集）可以被匹配零次或更多次

- +

> 指定前一个字符（字符集）可以被匹配一次或多次

- ?

> 匹配一次或零次

	r=r"ab+?"
	re.findall(r,"abbb")
	['ab']		//加在重复次数后面表示非贪婪模式
	r=r"ab+"
	re.findall(r,"abbb")
	['abbb']	//贪婪模式

- {}

> 匹配指定次数

	{m,n}	至少重复m次，最多重复n次
	{ ,n}	最多重复n次
	{m, }	最少重复m次

- .

- |

- ()

##操作
	
###re.compile()接受可选的标志参数

	r1 = r"\d{3,4}-?\d{8}
	p_tel = re.compile(r1)
	< _sre.SRE_Pattern object at 0x .... >
	
	p_tel.findall('010-12345678')
	['010-12345678']

	hello_re = re.compile(r'hello',re.I)	//re.I	不区分大小写
	csvt_re.findall('hello')
	['hello']
	csvt_re.findall('HeLlo')
	['HeLlo']

###match()

> 决定RE是否在字符串刚开始的位置匹配

###search()

> 扫描字符串，找到这个RE匹配的位置


**没有匹配到，match()和search（）将会返回None，成功匹配，会返回一个'MatchObject‘实例**

###findall()

> 找到RE匹配的所有子串，并把它们作为一个列表返回

###finditer()

> 找到RE匹配的所有子串，并把它们作为一个迭代器返回

###MatchObject实例方法

group()		返回被RE匹配的字符串

start()		返回匹配开始的位置

end()		返回匹配结束的位置

span()		返回一个元组包含匹配（开始，结束）的位置

##顶级函数

###sub()/subn()
	
	s = "heee hee hehe python"
	rs = r'he+'
	re.sub(rs,'hello',s)
	'hello hello hello python'

	re.subn(rs,'hello',s)
	('hello hello hello python', 3)

###split()

	ip = "123+456-789*000"
	re.split(r'[\+\-\*]',s)
	['123','456','789','000']

**dir(re)可以看到正则表达式的方法和内置属性，可通过help()查具体使用方法**

##RE属性
- S		使.匹配包括换行在内的所有字符
- I		是匹配大小写敏感
- L		做本地化识别匹配.法语等
- M		多行匹配，影响^和$
- X		能够使用REs的verbose状态，使之被组织得更清晰易懂

		r1 = r"baidu.com"
		re.findall(r1,'baidu.com')
		['baidu.com']
		re.findall(r1,'baiduacom')
		['baiduacom']
		re.findall(r1,'baidu\ncom')
		[]
		re.findall(r1,'baidu\ncom',re.S)
		['baidu\ncom']
	
		s = """
			hello world
			world hello
			hello hello
			world world
		"""
		r = r"^world"
		re.findall(r,s,re.M)
		['world','world']

		tel = r"""
			\d{3,4}
			-?
			\d{8}
			"""
		re.findall(tel,'010-12345678')
		[]
		re.findall(tel,'010-12345678',re.X)
		['010-12345678']

##分组
	
> 当有分组存在时，findall会优先返回分组数据

	email = r"\w{3}@\w+(\.com|\.cn)"
	re.match(email,'zzz@qq.com')
	< _sre.SRE_Match object at 0x... >
	re.match(email,'zzz@qq.org')
	//None
	
	re.findall(email,'zzz@qq.com')
	['.com']

	s = """
		adas asdasd hello src=world yes sffsd
		adadasd src=123 yes sf
		hello src=python yes hehe
		"""
	r1 = r"hello src=.+ yes"
	re.findall(r1,s)
	['hello src=world yes','hello src=python yes']
	r2 = r"hello src=(.+) yes"
	re.findall(r2,s)
	['world','python']

#*爬虫*
	
	import re
	import urllib.request
	
	def getHtml(url):
	    page = urllib.request.urlopen(url)
	    html = page.read()
	    return html
	
	
	def getImg(html):
	    html = html.decode('utf-8')
	    reg = 'src=".*?(http://.*?\.jpg)" size'
	    imgre = re.compile(reg)
	    imglist = re.findall(imgre,html)
	    x=0
	    print(imglist)
	    for imgurl in imglist:
	        urllib.request.urlretrieve(imgurl, '%s.jpg' % x)
	        x+=1
	
	
	Imghtml = getHtml("http://tieba.baidu.com/p/4758953819")
	getImg(Imghtml)
	**正则表达式没写好，只能匹配四张**

#10.内存

##浅拷贝

> 对引用的拷贝

	a = [1,2,3,'a','b','c']
	b=a
	b
	[1,2,3,'a','b','c']
	id(a)
	1403...
	id(b)
	1403...
	a.append('d')
	a
	[1,2,3,'a','b','c','d']
	b
	[1,2,3,'a','b','c','d']
	b.append(4)
	b
	[1,2,3,'a','b','c','d',4]
	a
	[1,2,3,'a','b','c','d',4]

##深拷贝

> 对对象的资源拷贝

	import copy
	a = [1,2,3,['a','b','c']]
	a
	[1,2,3,['a','b','c']]
	b=a
	b
	[1,2,3,['a','b','c']]
	c = copy.copy(a)
	c
	[1,2,3,['a','b','c']]
	id(a)
	1403....36
	id(b)
	1403....36
	id(c)
	1403....28
	a.append('d')
	a
	[1,2,3,['a','b','c'],'d']
	b
	[1,2,3,['a','b','c'],'d']
	c
	[1,2,3,['a','b','c']]
	id(a[0])
	15270712
	id(c[0])
	15270712
	
	id(a[3])
	140379339758264
	id(c[3])
	140379339758264
	a[3].append('d')
	a
	[1,2,3,['a','b','c','d'],'d']
	b
	[1,2,3,['a','b','c','d'],'d']
	c
	[1,2,3,['a','b','c','d']]

	-----------------------------
	d = copy.deepcopy(a)
	a
	[1,2,3,['a','b','c','d'],'d']
	d
	[1,2,3,['a','b','c','d'],'d']
	id(a)
	14...36
	id(d)
	14...80
	id(a[0])
	15..72
	id(d[0])
	15..72
	id(a[3])
	14...64
	id(d[3])
	14...08
	a.append('e')
	a
	[1,2,3,['a','b','c','d'],'d','e']
	d
	[1,2,3,['a','b','c','d'],'d']
	a[3].append('x')
	a
	[1,2,3,['a','b','c','d','x'],'d','e']
	d
	[1,2,3,['a','b','c','d'],'d']

#11.文件与目录

##文件读写

> python进行文件读写的函数是open或file

> file_handler = open(filename, mode)

mode(默认只读)

- r		只读
- r+		读写
- w		写入，先删除原文件，再重新写入，如果文件没有则创建
- w+		读写，先删除原文件，再重新写入，如果文件没有则创建（可以写入输出）
- a		写入，在文件末尾追加新的内容，文件不存在，则创建
- a+		读写，在文件末尾追加新的内容，文件不存在，则创建
- b		打开二进制文件，可以与r,w,a,+结合使用
- U		支持所有的换行符号，"\r" "\n" "\r\n"

###read()

	f1 = open('test.txt')
	f1.read()
	f1.close()

###write()

	f2 = open('new.txt', "w")
	f2.write('hello')
	f2.close()

##文件对象方法

###read()

> String = FileObject.read([size])

- 读取文件的所有内容，并复制给一个字符串
- size:读出文件的钱size个字节，并输出给字符串，此时文件的指针指向size处

		test.txt
		hello
		python
		hello
	
		f1 = open('test.txt')
		s1 = f1.read()
		f1.close()
		s1
		hello\npython\nhello
	
		for i in open('test.txt'):
			print(i)
	
		hello
	
		python
	
		hello

###readline()

> String = FileObject.readline([size])

- 每次读取文件的一行
- size:是指每行每次读取size字节，直到行的末尾 

		f1 = open('test.txt')
		f1.readline()
		hello
		f1.readline()
		python
		f1.readline()
		hello
		f1.readline()
		''
		f1.close()

###readlines()

> List = FileObject.readlines([size])

- 读取多行，返回一个列表
- size:每次读入size个字节，然后继续按size读，不是每次读入行的size个字节

		f1 = open('test.txt')
		f1.readlines()
		['hello','python','hello']

###next()

> FileObject.next()

- 返回当前行，并将文件的指针指到下一行

		f1.next()
		'hello'
		f1.next()
		//文件指针到达文件尾，调用next会停止，报错

###write()

> FileObject.Write(string)

- 写入前是否清除原文件数据，取决于打开模式

###writelines()

> FileObject.writelines(List)

- 多行写
- 效率比write高，速度更快

		l = ['one\n','two\n','three\n']
		f1 = open ('test.txt', 'w')
		f1.writelines(l)
		f1.close()
	
		test.txt
		one
		two
		three

###seek()

> FileObject.seek(偏移量, 选项)

选项

- 0		文件头
- 1		文件当前位置
- 2		文件尾

###flush()

> FileObject.flush()

- 提交更新

##OS模块

> 目录操作需要调用os模块

	import os
	os.mkdir("test")

###mkdir

> mkdir(path[,mode=0777])

###makedirs

> makedirs(name,mode=511)

###rmdir

> rmdir(path)

###removedirs

> removedirs(path)

###listdir

> listdir(path)

###getcwd

> getcwd()

###chdir

> chdir(path)

###walk

> walk(top, topdown=True, onerror=None)

#12.异常

##异常抛出

	> try
	> 	...//可能会抛出异常
	> except 异常类型， 参数
	>   ...//处理
	> finally
	>   ...//处理

	try:
		open('abc.txt')
		print(hello)
	except IOError, msgio:
		print("打开失败!")
	except NameError, msgn:
		print("变量未定义!")

###raise抛出异常

> raise 异常类型(异常信息)
		
###常见异常

- AssertionError		assert语句失败
- AttributeError		试图访问一个对象没有的属性
- IOError			输入输出异常，基本是无法打开文件
- ImportError		无法引入模块或者包，基本是路径问题
- IndentationError	语法错误，代码没有正确的对齐
- IndexError			下标索引超出序列边界
- KeyError			试图访问字典里不存在的键
- KeyboardInterrupt	Ctrl+C被按下
- NameError			使用一个还未赋予对象的变量
- SyntaxError		Python代码逻辑语法错误，不能执行
- TypeError			传入的对象类型与要求不符
- UnboundLocalError	试图访问一个还未设置的全局变量
- ValueError			传入一个不被期望的值

#13面向对象

##类和对象

> 类是对事物的抽象

> 对象是类的一个实例

##python类定义

> 类名的首字母要大写

> 类的方法中至少有一个参数self

	class  类名：
			成员变量
			成员函数

> 创建对象的过程称之为实例化；当一个对象被创建后，包含三个特性：对象的句柄，属性和方法

> 对象的属性对应类中的成员变量，对象的方法对应类中的成员函数

	对象名 = 类名()

##类的属性

##类的方法
