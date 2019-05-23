
## day1时长3hours ##

### 卡点1 ###
Sublime 文本编辑器的作用是什么，怎么用，和VS code的关系是什么？
Sublime 和VS code的功能大体相同
sublime优点
适合主流前端开发编辑器
文本功能强大
可安装大量插件，来满足定制化需求

vscode优点
最重要的是不要钱
插件也很多
占用内存低，启动速度，打开速度相对比较快

所以现在目前起步阶段，就先放一放sublime

### 卡点2 ###
如何设置交互式环境
1 下载vscode的扩展“Python”
已经安装
2 查看一下这个扩展的官方说明，

### 卡点3 ###
怎样设置一个较为舒服的电脑亮度？
找了一圈，最后发现还是，自己根据自己的感觉，在键盘上调节亮度比较合适

## day2所用时间是2hours ##

### 进步点1 ###

运算符号//斜双杠代表的是除后剩下的整数。而%是代表除后剩下的余数。

### 卡点1 ###
    `c=1+5g
	 print(type(c))`
这个代码显示错误

最后发现只有c=1+5j,等号只有是j才能运行成功

### 练习的代码 #
    `a = 321
     b = 123
     print(a + b)
     print(a - b)
     print(a * b)
     print(a / b)
     print(a // b)
     print(a % b)
     print(a ** b)`


    `a = int(input('a = '))
	b = int(input('b = '))
	print('%d + %d = %d' % (a, b, a + b))
	print('%d - %d = %d' % (a, b, a - b))
	print('%d * %d = %d' % (a, b, a * b))
	print('%d / %d = %f' % (a, b, a / b))
	print('%d // %d = %d' % (a, b, a // b))
	print('%d %% %d = %d' % (a, b, a % b))
	print('%d ** %d = %d' % (a, b, a ** b))`

    `a = 100
	b = 12.345
	c = 1 + 5j
	d = 'hello, world'
	e = True
	print(type(a))
	print(type(b))
	print(type(c))
	print(type(d))
	print(type(e))`

    `a=5

	b=10
	c=3
	d=4
	e=5
	a+=b
	a-=c
	a*=d
	a*=e
	
	print('a=',a)
	print('b=',b)
	print('d=',d)
	print('e=',e)
	flag1=3>2
	flag2=2<1
	falg3=flag1 and flag2
	flag4=flag1 or flag2
	flag5=not flag1
	print("flag1=",flag1)
	print("flag2=",flag2)
	print("flag3=",flag3)
	print("flag4=",flag4)
	print("flag5=",flag5)
	print(flag1 is True)
	print(flag2 is not False)`

温度单位的转换

    f=float(input('请输入华氏温度:'))
	c=(f-32)/1.8
	print('%.1f华氏度=%.1f摄氏度'%(f,c))

### 卡点2 ###

在计算圆的面积和周长的时候，出现math错误。猜测可能是没有安装math库。
最后发现是，自己应该输入math.fi，但是自己却输入了math.py,造成了程序的运行错误
    import math 
	radius=float(input('请输入圆的半径：'))
	perimeter=2*math.pi*radius
	area=math.pi*radius*radius
	print('周长:%.2f'%perimeter)
	print('面积：%.2f'%area)

计算年是不是瑞年
    year=int(input('请舒服年份:'))
	is_leap=(year%4==0 and year %100!=0 or year %400==0)
	print(is_leap)

### day2总结 时长0.2hour ###

语言的元素
第一个代码，使用变量保存数据并进行算术运算
第二个代码，使用input函数输入，就是可以键盘输入随意数字。使用int()进行类型转换，就是可以输入的数字得转化成整数。用占位符格式化输出的字符串
第三个代码，使用type()检查变量类型

## day3 ##

分支结构的应用场景

比如我们设计一个游戏，游戏的第一关的通关条件是玩家获得1000分，那么咋完成本剧游戏的时候，我嗯要根据玩家得到的分数决定究竟是进入第二关还是好书玩家：游戏结束。这里就会产生两个分支，而且这两个分支只有一个会呗执行，这就是程序的分支结构。

在比如，分支结构可以是用在人生的选择上，到了大三你是准备考研还是准备简历准备工作，还是其他，这也会产生一个分支是吧

> if语句的使用

### 卡点1 ###
在敲输入代码（用于身份验证），输入进去显示，if语句有问题
显示的问题是，SyntaxError:invalid character in identifier.语法错误，标识符中的无效字符。
最后没有找到问题，把错误行又输入一遍，成功。

后来找到原因是，在输入符号的时候没有及时切换的英文，用中文的符号输入当然是错误的
    '''
	身份验证
	'''
	
	username=input('请输入用户名:')
	password=input('请输入口令:')
	if username=='linge' and password=='6666':
	    print('身份验证成功')
	else:
	    print('身份验证失败')


----------
40分钟已经过去

    '''构造更多的分支
	分段函数'''
	x = float(input('x='))
	if x>1:
	    y=3*x-5
	elif x>=-1:
	    y=x+2
	else:
	    y-5*x+3
	print('f( %.2f)=%.2f'%(x,y))

### 进步点1 ###
   
单等号和双等号有什么区别

返回到day2看后，双等号‘==’才是等于的意思，单个等号‘=’是赋值运算符的意思

英制单位和公制单位的互换
    value=float(input('请输入长度：'))
	unit=input('请输入单位：')
	if unit=='in'or unit=='英寸':
	    print('%f英寸=%f厘米'%(value,value*2.54))
	elif unit=='cm' or unit == '厘米':
	    print('%f厘米=%f英寸'%(value,value*2.54))
	else:
	    print('请舒服有限的单位')
**反思** 
通过这几次的输入细致观察发现，当有中文字符的时候，在输入的 时候注意，中英文的切换，因为指令的输入都是英文的，如果，没有及时回到英文的化，会报语法错误

投掷骨子决定做什么
    from random import randint

	face=randint(1,6)
	if face ==1:
	    result='唱首歌'
	elif face==2:
	    result='跳支舞'
	elif face==3:
	    result='学毛叫'
	elif face==4:
	    result='学狗叫'
	elif face ==5:
	    result='念绕口令'
	else :
	    result='讲冷笑话'
	print(result)

百分制成绩转等级制成绩
90分以上是a
80~89是b
70~79是c
60~69是d
60以下都是e
    score=float(input('请输入成绩：'))
	if score>=90:
	    grade='a'
	elif score>=80:
	    grade='b'
	elif score>=70:
	    grade='c'
	elif score>=60:
	    grade='d'
	else:
	    grade='e'
	print('对应的等级是：',grade)

输入三条边长如果能构成三角形就就就计算周长的面积
判断输入的边长能不能构成三角形
如果能则计算除三角形的周长和面积
    import math

	a = float(input('a = '))
	b = float(input('b = '))
	c = float(input('c = '))
	if a + b > c and a + c > b and b + c > a:
	    print('周长: %f' % (a + b + c))
	    p = (a + b + c) / 2
	    area = math.sqrt(p * (p - a) * (p - b) * (p - c))
	    print('面积: %f' % (area))
	else:
	    print('不能构成三角形')

输入月收入和五险一金计算个人所得税
    salary=float(input('本月收入：'))
	insurance=float(input('五险一金：'))
	diff =salary-insurance-3500
	if diff<=0:
	    rate=0
	    deduction=0
	elif diff<1500:
	    rate=0.03
	    deduction=0
	elif diff<4500:
	    rate =0.1
	    deduction1=105
	elif diff<9000:
	    rate=0.2
	    deduction=555
	elif diff<35000:
	    rate=0.25
	    deduction=2755
	elif diff<80000:
	    rate=0.35
	    deduction=5505
	else:
	    rate=0.45
	    deduction=13505
	tax=abs(diff*rate-deduction)
	print('个人所得随：￥%.2f'%tax)
	print('实际到手收入：￥%.2f'%(diff+3500-tax))

**day3总结**
今天主要是if语句的使用，用来解决出现分支的情况，可以是两种情况的判断三个边能不能组成一个三角形，如果能出来周长和面积。也可以是三个分支的分段函数和单位的转化。可以是五种情况的成绩等级认定。可以是六种情况的摇色子。可以是八种情况的个人所得税计算。

完成day3用时2个小时

看一下网上的有没有克隆成功
经过检验是没有问题的，在把原来的复制过来

## day4用3.3个小时 ##
5.21今天学习循环结构，同时用到分支结构和循环结构的应用场景，例如，用程序控制机器人踢足球，如果持球还没进入射门范围内，那么我们就要一直发出让机器人向球门方向奔跑的指令。

for-in循环

如果知道循环执行的次数或者对一个容器进行迭代，用for-in循环

### 进步点1 ###

在某些对象中会包含对其他对象的引用，这样的对象被称为“容器”

因此，我们可以把容器视作用于组织各种元素的数据结构，如list，dict，str

用for循环实现1~100求和

    `sum=0
	for x in range (101):
	    sum+=x
	print(sum)`
### 进步点2 ###

MarkdownPad中的输入代码的操作时怎么回事？找没有找到，想到一个办法就是自己实践一下，比较一下，按一下代码符号和按两下代码符号的区别，在加上按TAB键和不按TAB键的区别。

直接按一下

    sum=0
for x in range (101):
    sum +=x
print(sum)

按两下
    `sum=0
for x in range (101):
    sum +=x
print(sum)`	

按一下然后除了第一行剩余的全选后按TAB键
    sum=0
	for x in range (101):
	    sum +=x
	print(sum)

按两下然后除了第一行剩余的全选按TAB键
    `sum=0
	for x in range (101):
	sum +=x
	print(sum)`



经过检验发现，复制粘贴过来是都不合格
第一种情况是只有第一行是代码的样式
第二种情况是都是代码的样式，但是，在一行内。
嗲三种情况是是文本的样式
第四种情况是都是代码的样式，但是都在一行内

结论就是，按两下code的按钮是正确的操作，按不按Tab键影响不是很大。

### 卡点1 ###
不知道为什么在GitHub desk上没有显示变化，所以也就无法推到网上？
尝试一下在网上在自己的GitHub在克隆一个到本地，

5/21/2019 10:19:17 AM 
发现可以通过上面的按钮来记录时间，从而可以精确地计算每一次所用的时间

先在再回过头来，自学今天的循环结构

用for循环实现1~100的偶数求和
    `sum=0
	for x in range (2,101,2): ##开始，结束，步长
	    sum +=x
	print(sum)`

while循环

如果不知道具体循环次数的循环结构，用while循环，while循环通过一个能产生或转换bool值的表达式来控制循环，表达式的值为True循环继续，表达式的值为False循环结束。

一个猜数字的小游戏
    `import random

	answer=random.randint(1,100)
	counter=0
	while True:
	    counter+=1
	    number=int(input('请输入：'))
	    if number<answer:
	        print('大一点')
	    elif number>answer:
	        print('小一点')
	    else:
	        print('恭喜你才对了')
	        break
	print('你总共才对了%d次'%counter)
	if counter>7:
	    print('你脑子有点不够用')`
> 上面的代码中使用了break关键字来提前终止循环，需要注意的是break只能终止它所在的那个循环，另一个关键字是continue，它可以用来放弃本次循环后续的代码直接让循环进入下一轮

九九乘法表
    `for i in range(1,10):
    	for j in range (1,i+1):
        	print('%d*%d=%d' % (i,j,i*j),end='\t')
    	print()`

输入两个正整数，计算最大公约数和最小公倍数
    `x=int(input('x= '))
	y=int(input('y= '))
	if x >y:
	    x,y=y,x
	for factor in range (x,0,-1):
	    if x %factor==0 and y%factor==0:##就是x和y除以同一个数后，余数为零是，这个数就是最大公约数
	        print('%d和%d最大公约数是%d'%(x,y,factor))
	        print('%d和%d的最小公倍数是%d'%(x,y,x*y//factor))##最小公倍数是两数相乘后再除以他们的最大公约数
	        break`
### 进步点 ###
双斜号是什么意思，是整除的意思

最后一个练习，也是一个理解稍微困难的练习，关键是要和脑子中已经有的做斗争，打印三角形的图案
    `row=int (input('请输入行数：'))
	for i in range (row):
	    for _ in range(i+1): #这里的_应该表示是空格的意思
	        print('*',end='')
	    print()
	
	for i in range (row ):
	    for j in range (row):
	        if j <row -i-1:
	            print(' ',end='')       ###注意有一个引号是空格
	        else:
	            print('*',end='')
	    print()
	
	for i in range(row):
	    for _ in range (row-i -1):
	        print(' ',end='')
	    for _ in range (2*i +1):
	        print('*',end='')
	    print()`
### 进步点 ###
row是什么意思，根据上面的意思是一个你自己输入的任意的整数

### 注意点 ###

这个和你以前的思维习惯不一样
range(101)可以产生一个0到100的整数序列
range(1,100)可以产生一个1到99的整数序列
range(1,100,2)可以产生一个1到99的奇数序列，其中2是步长，即数值序列的增量

5/21/2019 12:00:55 PM 

## day5 ##
5/21/2019 2:45:38 PM 

### 进步点 ###
上午做的打印三角形，其中的print()函数里的end="是什么意思。
在官网上找一下，end的默认意思是换行，但是这里的定义是代表的是不用换行。否则按照默认模式打出来的点是竖的，不是横的。

5/21/2019 3:05:24 PM 

day5的练习内容是总结与训练

第一个练习清单是寻找水仙花数
打开连接后是水仙花数的定义，水仙花数是指一个三位数，它的每个位上的数字的3次幂之和等于它本身（例如，1^3+5^3+3^3=153)
三位的水仙花数总共有4个：153，370，371，407

如果让我写代码表示的话，空白，看一下前4天的代码找找灵感。

第一是怎样设定只能三位数进行检测呢？
看到九九乘法表，发现可以用range来规定范围（100，1000），range(1000)可以产生一个100到999的整数列

第二个怎样创造一个if条件呢？
需要用到定义中的公式，可是个位十位百位上的数字，怎么表示呢？
怎样把这个三位数每个数字分别截开呢？这里用到什么函数呢？继续看前4天的找灵感
找一圈最后一个问题没解决，只能看一下示例代码，

### 进步点 ###
双斜杠//是整除的意思，%是模的意思，那num%10 是什么意思呢？

5/21/2019 3:45:51 PM 
休息
5/21/2019 4:12:39 PM 

参考day2中，num%10是num除以10后的余数
    `for num in range(100,1000):
	    low=num%10          #个位数是三位数除以10后的余数，如987/10的余数是9
	    mid=num//10%10      #十位数是三位数整除10后得到的数98，在除以10后的余数8
	    high=num//100		#百位数数三位数整除100后得到的数，如987整除100得到的数是9
	    if num ==low**3+mid**3+high **3:
	        print(num)`

5/21/2019 4:23:41 PM 
第二个练习是也是寻找数，这个数是完全数
查找一下完全数的定义，
完美数是除自身外其他所有因子的和正好等于这个数本身的数。
如6的约数有1，2，3，6，真因子是1，2，3。

概念弄明白后，开始构思

第一，没有范围的限制，是所有的数，那么直接对数进行判断，如果符合式子的话就print出来。它的所有因子除了本身应该怎么表示出来呢？
推论有错误，也是有范围的，可以自己的定义一个范围，不然的话数是无限的，会一直运行下去。

    `import time
	import math
	
	start=time.clock()
	for num in range(1,10000):
	    sum=0
	    for factor in range (1,int(math.sqrt(num))+1):
	        if num %factor==0:
	            sum+=factor
	            if factor>1 and num / factor != factor:
	                sum +=num /factor
	    if sum == num:
	        print(num)
	end=time.clock()
	print("执行时间：",(end-start),"秒")`
### 卡点用时约0.3小时 ###
上段函数的卡点的是sqrt,在官方网站找一下。

5/21/2019 5:19:51 PM 

5/21/2019 5:56:01 PM 
math.sqrt(x)返回x的平方根。但是，看一眼那个if条件句依然不是特别明白什么意思。再读一遍好像明白了，
比如是num=2时，factor是在range(1,2.4)，如果2比上1，2的余数是0的，那么1，2就是它的因子，1是它的真因子
比如是num=3时，factor是在range(1,3.7)，如果3比上1，2，3的余数是0的，那么1，2，3就是它的因子，1，2是它的真因子
比如是num=6时，factor是在range(1,3.4)，如果6比上1，2，3的余数是0的，那么1，2，3就是它的因子，1，2，3是它的真因子
····

找它的因子有一个特点是基本是因子分布于一个数开方后的左边，比如9开方后是3，除了本身9，3就是它的最大的约数了。

5/21/2019 6:16:31 PM 

5/23/2019 9:41:50 AM 
开始day5的第三个训练——百钱百鸡的问题，首先明白概念——鸡翁一值钱五，鸡母一值钱三，鸡雏三值钱一。百钱买百鸡，问鸡翁、鸡母、鸡雏各几何？

详解

一只公鸡5块，而100块买鸡，公鸡数量只能小于20

设母鸡x只，公鸡y只，小鸡100-x-y只。
所以3x+5y+（100-x-y)/3=100
化简9x+15y+(100-x-y)=300

有四种情况符合要求
![百鸡百钱](http://https://baike.baidu.com/pic/百鸡百钱/5857320/0/0b14ad19460e8d5642a9ad7b?fr=lemma&ct=single#aid=0&pic=0b14ad19460e8d5642a9ad7b)

知道大概情况后，关键是怎样把它用代码实现呢？看看前4天的代码找找灵感，看到求最大公约数，最小公倍数后尝试写一下

自己尝试后的代码
    `import x
	import y
	import math
	z =100-x-y
	
	for x in range(0,20):
	    if 9*x+15*y+(100-x-y)==300:
	        print('公鸡%d,母鸡%d,小鸡%d'%（x,y,z))
	        break`

正确的代码
    `for x in range(0,20):
	    for y in range(0,33):
	        z=100-x-y           #注意空格号的位置
	        if 5*x+3*y+z/3==100:
	            print('公鸡：%d只,母鸡：%d只,小鸡：%d只'%(x,y,z))`

我的错误点
第一不需要break因为这个数是有限的
第二不需要import y只需要for y in range(0,20)就行了
第三，注意层次感

5/23/2019 10:30:28 AM 用时0.8h

生成“斐波拉切数列”。首先，概念，斐波那契数列：1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ...
如果设F(n）为该数列的第n项（n∈N*），那么这句话可以写成如下形式：:F(n)=F(n-1)+F(n-2)

从第二项开始，后面的数是这个数前两个数的和。

最后需要print出1，1，2，3，5，8，13，21，34...
### 卡点1：怎样利用循环结构输出这么多的数 ###


### 卡点2：两个变量应该怎样相加得到一个结果 ###
5/23/2019 11:02:28 AM 

想不出来，参考一下代码
    `a=0
	b=1
	for _ in range(20):
	    (a,b)=(b,a+b)
	    print(a,end=' ')		##end=' '代表它不用换行，直接空一格就行了`
### 进步点 ###
参考完代码后，其中的for _ in range是什么意思
5/23/2019 11:11:59 AM  
百度后它的意思：_ 是个占位符，循环中不关心具体的元素内容，就是简单的“让它循环这么多次”。
for _ in range(20):让它循环20次

解决卡点2，(a,b)=(b,a+b)

day5练习清单的最后一项

Graps赌博游戏，搜索不到它的定义，直接看代码，没有代码，所以先放这吧






















