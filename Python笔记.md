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

    1. len()				求序列长度
    2. +					连接2个序列
    3. *					重复序列元素
    4. in					判断元素是否在序列中
    5. max()				返回最大的值
    6. min()				返回最小的值
    7. cmp(tuple1, tuple2)	比较2个序列值是否相同
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

    列表的操作
    取值
    	切片和索引
    	list[]
    添加
    	list.appen()
    删除
    	del(list[])
    	list.remove(list[])
    修改
    	list[]=x
    查找
    	var in list
##字典