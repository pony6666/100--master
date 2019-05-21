
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

