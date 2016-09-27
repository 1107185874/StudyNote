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
#流程控制

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

#函数
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
