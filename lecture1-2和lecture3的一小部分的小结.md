 

今天从三点半开始，先是搞定了护眼模式的设定。

然后是，相关操作的运行。

最后是看笑来老师的书。

在Part3.E中，提炼了一下。

issue:自学一门手艺的时候需要不需要事无巨细地全面了解相关的知识。

conclution:全面是掌握一门手艺的基本。

reason：从逻辑上推论是，学习得更全面，练习的更全面，使用得更全面，在使用技能去创造的时候也会更加全面。

怎样才能全面：
1.多几本书，让知识拼图更加完整。
2.教。写教程，写学习笔记。

最后决定在学习MIT Python课程的前5节课，写一个教程出来。

不得不说，写教程真的是很消耗精力。

暂时的想法，先对目前所学习的对象进行梳理。

对象的类型定义了程序可以对它们执行的操作
比如说，马林是一个人，我可以走路说话···
比如说，我的宠物是一只猫，它可以上树，捉老鼠···

对象是
标量，不能细分，比如，int整数,float小数,bool布尔值···
非标量，可以访问内部结构

组合**对象**和**运算符**以形成表达式。而组成的这个表达式也只有一个值，只有一个类型。



顺便弄懂了，有一节课中的利用guesse,然后开方后不是想象中的整数的原因。


 

# MIT Python的相关笔记和扩展 #

# 对象 #

## 对象1——字符串 ##
字符串是一个字符的序列。

字符串可以是字母，数字，特殊字符还有空格，字符串必须得用引号括起来。

### 对于对象1——字符串的操作 ###

字符串的拼接和重复。
`###stings字符串

	hi='hello there'
	name='malin'
	###加号是一个赋值符号
	
	greet=hi+name
	print(greet)
	
	###加号不会隐形式添加，任何空格
	
	greeting=hi +" "+name
	print(greeting)
	###上面就是字符串之间的串联
	
	###下面是和字符串相关的星型运算符
	
	silly=hi +(" "+name)*3
	print(silly)
	###星号可以代表字符串和数字之间的乘法，重复那个字符串很多次`


字符串的标识，4种标识方式，单引号，双引号，三个单引号，三个双引号。

只要字符串中有斜杠的，就需要注意，可以查看官方网站，进行相关的操作。

1 连接和重复
字符串可以用 + 进行**连接**（粘到一起），也可以用 * 进行**重复**。

2 观看较长字符串的操作
相邻的两个或多个 **字符串字面值 **（引号引起来的字符）将会自动连接到一起.——这对于较长的字符串可以有一个避免看乱的作用。

3 索引（通过下标进行访问）
第一个字符串的索引是0，而不是1.因为0无所谓正负，所以从右边开始数的话，第一索引是-1。

4 切片 
注意切片的开始总是被包括在结果中，而结束不被包括。这样做的原因是可以使得 s[:i] + s[i:] 总是等于 s
- 可以使用[start：stop：step]切割字符串
- 如果给出两个数字，[start：stop]，默认步骤= 1
- 你也可以省略数字，只留下冒号 s = "abcdefgh"  s[::] 弄出的是 evaluates to "abcdefgh", same as s[0:len(s):1] 
- 字符串是不可变的，无法修改
	s = "hello" 
	而s[0] = 'y' 是不允许的
	但s = 'y'+s[1:len(s)] 是允许的，s被绑定到新的对象

5.字符串的长度、
	s = "abc" len(s)输出的结果是3

6.可以使用for循环对字符串中的字符进行遍历，而range只能迭代数字



7.猜测和检查算法
下面试猜测一个正数的立方根
	cube = 8
	for guess in range(cube+1):
	    if guess**3 == cube:
	        print("Cube root of", cube, "is", guess)

进阶版——猜测考虑进负数，break 语句，提前结束for循环
    cube = -27
	for guess in range(abs(cube)+1):
	    # passed all potential cube roots
	    if guess**3 >= abs(cube):
	        # no need to keep searching
	        break
	if guess**3 != abs(cube):
	    print(cube, 'is not a perfect cube')
	else:
	    if cube < 0:
	        guess = -guess
	        
	    print('Cube root of ' + str(cube) + ' is ' + str(guess))

8.近似解算法




#运算符#
1 赋值符号
单个等号，把变量和值绑到一块的原因？1，可以重复使用变量 2，以后更容易更改代码

2 print

3 input
    text=input ("anything:")
	print(text*5)

4 关于数字的运算符>,<,==,!=,加减乘除幂商

5 对于布尔值的运算符and,or

    a=15
    b=16
    print(a>b)

    m=False
    n=True
    both=m and n
    print(both)


### 流程控制属不属于运算符 ？###
流程控制不属于运算符


今天看笑来老师的《自学是门手艺》中的Part3.E中，提炼了一下。

issue:自学一门手艺的时候需要不需要事无巨细地全面了解相关的知识？

conclution:全面是掌握一门手艺的基本。

reason：从逻辑上推论是，学习得更全面，练习的更全面，使用得更全面，在使用技能去创造的时候也会更加全面。

怎样才能全面：
1.多几本书，让知识拼图更加完整。
2.教。写教程，写学习笔记。

最后决定先暂放一下lecture6的学习，把MIT Python课程的前5节课，写一个小的教程出来。



### 流程控制1——分支 ###
分支有三种情况
1.
if <condition>:
	<expression>
	<expression>
	···
2.
if <condition>:
	<expression>
	<expression>
	···
else: 
	<expression> 
	<expression> 
	...

3.
if <condition>:
	<expression>
	<expression>
	···
elif: 
	<expression> 
	<expression> 
	...
else: 
	<expression> 
	<expression> 
	...


- 上面的<condition> has a value True or False 
- 如果<condition>是True,执行<expression>

分支的示例代码

    x = float(input("Enter a number for x: "))
	y = float(input("Enter a number for y: ")) 

	if x == y: 
		print("x and y are equal") 
		if y != 0: 
			print("therefore, x / y is", x/y) 
	elif x < y: 
		print("x is smaller") 
	else: 
		print("y is smaller") 
	print("thanks!")

6/14/2019 9:35:32 AM 
6/14/2019 2:51:44 PM 
需要注意的是上面的表示数值相等的是双等号。

### 流程控制2——循环 ###

循环有两种类型while循环和for循环

1.while循环
while <condition>: 
	<expression> 
	<expression> 
	... 

- 上面的<condition> 也是返回一个布尔值
- 如果 <condition>是真的，执行while代码块中的所有步骤
- 再次检查<condition>
- 重复直到<condition>为False

while循环的一个例子

    n = input("You're in the Lost Forest. Go left or right? ") 
	while n == "right": 
	    n = input("You're in the Lost Forest. Go left or right? ") 
	print("You got out of the Lost Forest!")


2.for循环
for <variable> in range(<some_num>): 
	<expression> 
	<expression> 
	...

- 每次循环时，<variable>取值
- 第一次，<variable>从最小值开始
- 下次，<variable>获得prev值+ 1
- 以此类推

for循环中的range(start,stop,step) 
- 默认值为start = 0和step = 1且可选
- 循环直到stop-1停止

for循环的一个例子

    mysum = 0 
	for i in range(7, 10): 
	    mysum += i 
	print(mysum)

	mysum = 0 
	for i in range(5, 11, 2): 
	    mysum += i 
	print(mysum)

3.while和for循环中的break语句
- 立即退出它所在的循环
- 跳过代码块中的剩余表达式
- 只退出最里面的循环！

break循环的一个例子

    mysum = 0 
	for i in range(5, 11, 2): 
	    mysum += i 
	    if mysum == 5: 
	        break 
	        mysum += 1 
	print(mysum)

mysum += i 
if mysum == 5: 
	break 
这三行是最里面的循环，所以都得退出。
mysum += 1
这是代码块中剩下的，所以也退出

对流程控制中的两种循环的比较

for循环
1. 知道循环的次数
2. 可以通过break尽早地结束
3. 用一个计数器
4. while循环可以替代for循环

while循环
1. 不知道循环的次数
2. 也可以通过break尽早地结束
3. can use a counter but must intialize before loop and increment it inside loop可以使用计数器但必须在循环之前初始化并在循环内增加它			###？这一点不是特别理解（看MIT lecture3，可以找到答案）
4. 可能不能用for循环来写while循环

区别点1 for训话是知道循环次数的，而while不知道循环次数
区别点2 while循环的使用范围要更大点
区别点3 for循环必须得使用计数器，而while循环可以使用计数器不过得初始化

相同点1 都可以通过break语句尽早地结束
相同点2 都可以用一个计数器
 

姓名： 马林
学习内容：lecture3的小部分扩充的小教程完成。
总共用时：约0.5小时

 



