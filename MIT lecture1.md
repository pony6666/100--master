## bindings视频中的一个卡点 ##

    `usa_gold=46
	uk_gold=27
	romania_gold=1
	
	total_gold=uk_gold+usa_gold+romania_gold
	print(total_gold)
	
	romania_gold+=1
	total_gold=uk_gold+usa_gold+romania_gold
	print(total_gold)`

上面得到的是74和75,而在视频中由于是74和75的形式是74.75所以，自己理解成有小数，但是程序写出来后，一跑，才明白是怎么回事。

## 新型对象——字符串 ##

所学的内容，分支，重复，制作

浮点数和整数是十进制数

字符串可以是字母，数字，特殊字符还有空间，字符串必须得用引号括起来


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

output

    `###output

	x=1
	print(x)
	x_str=str(x)
	###将x变成字符串的形式
	print("my fav num is",x,".","x=",x)
	print("my fav num is " , x_str +"."+"x="+x_str)
	print("my fav number is "+x_str+"."+"x="+x_str)
	`
用时0.7小时
6/2/2019 9:23:52 PM 

6/3/2019 7:54:18 PM 

MIT中的lecture2继续做，转了一圈还是直接看ppt吧，这样的速度稍微快一点。

input（" ")
- 打印引号中的任何内容
- 用户输入内容并点击输入
- 将该值绑定到变量

input()里面无论是什么都会变成一个字符串

刚才本打算下载一下资料，可是下载后，没发现课件和代码，然后发现有一栏是专门的课件和代码的不过得在浏览器上看，不过代码可以直接复制粘贴


最后决定这门课的学习方法是，哔哩哔哩视频，然后是官网的代码。


    `####################
	## EXAMPLE: input
	####################python用input的默认情况是字符串，这就是输入的工作原理
	text = input("Type anything：")			#text是一个变量文本
	print(5*text)
	num = int(input("Type a number： "))	#输入的这个数字可以规定给类型
	print(5*num)`

单个的等号是赋值符号，而要判断是不是向等得用双等号

逻辑运算对于布尔值
not a说明True 如果a是错误的话。False 如果a是正确的话。

a and b 说明 True 如果两者都是正确的话

a or b 说明 True 如果其中一个或者两者都是正确

用if语句可以控制程序的走向，可以是选择一件事。可以是选择一件事或者另外一件事。我们也可以有多个选择,用到elif条件。上面这三种情况是都得到一个决定点才能用到。

概念：控制流，决定点


    `####################
	## EXAMPLE: conditionals/branching 
	####################
	x = float(input("Enter a number for x: "))
	y = float(input("Enter a number for y: "))
	if x == y:
	    print("x and y are equal")
	    if y != 0:    #这里面的是一个镶嵌语句
	        print("therefore, x / y is", x/y)
	elif x < y:
	    print("x is smaller")
	elif x > y:
	    print("y is smaller")
	print("thanks!")`


用时1h

6/4/2019 10:57:04 PM 
刚才在折腾自己的github库，把这几天的训练提交一下，并且推向终端，用时大概0.2小时。

在结合今天中午单独看lecture2的后半部分视频（大概0.5小时），跑一下今天的代码

根据回忆首先我想搞懂的是while循环和for循环的区别，并且搞清楚break函数的用法。

好继续重新看视频搞清楚上面的两个问题。

在看群里发的视频的时候，如果是字幕后面如果是白色挡住字体的话，暂停一下，即可解决，看不清字幕的问题。

### 怎样在VS code 同时删除多行的第一个符号 ###
按住alt，用鼠标左键点击，可以出现多个光标，输入的代码可以在光标处同时增加。


    `####################

	## EXAMPLE: while loops 
	## Try expanding this code to show a sad face if you go right
	## twice and flip the table any more times than that. 
	## Hint: use a counter
	####################
	#n = input("You are in the Lost Forest\n****************\n****************\n :)\n****************\n****************\nGo left or right? ")
	#while n == "right" or n == "Right":
	#    n = input("You are in the Lost Forest\n****************\n******       ***\n  (╯°□°）╯︵ ┻━┻\n****************\n****************\nGo left or right? ")
	#print("\nYou got out of the Lost Forest!\n\o/")`

尝试了一下无限循环，感觉有种冲破束缚的感觉，真实感觉到计算机真听话。

好吧，时间有点不够，上面两个问题没有解决，剩下的八分钟视频明天在好好看看，

今天总时间0.2+0.5+0.8=1.5小时
6/4/2019 11:51:03 PM 

6/5/2019 7:57:25 PM 

今天看《把时间当作朋友》有的章节，学编程学到流程控制的时候，会知道这样一个知识，除了“顺序”外，只用“分支”和“循环”就能都完成任何流程——初学者都会好奇，这是如何证明的的呢？在这个结论当然是经过严谨的证明才能广泛接受的，但究竟有多少初学者可以看懂证明过程呢？在这种时候，不是“反问为什么“，而是“暂时不去问为什么”可能更为划算。

所以MIT的第二节课时关于流程控制的，可以说是非常重要了。

break语句的用武之地：你可能希望早一点推出，可能不想浏览所有的序列，或者你的心中有一个条件想早一点退出，比如对于while循环，你可能想在它变成False之前退出循环

break语句

    `mysum = 0
	for i in range(5, 11, 2):
	    mysum += i
	    if mysum == 5:
	        break
	        mysum += 1
	print(mysum)`

下面为自己翻译过来的一张ppt上的
for循环和while循环的区别

for循环
1. 知道循环的次数
2. 可以通过break尽早地结束
3. 用一个计数器
4. while循环可以替代for循环

while循环
1. 不知道循环的次数
2. 也可以通过break尽早地结束
3. can use a counter but must intialize before loop and increment it inside loop可以使用计数器但必须在循环之前初始化并在循环内增加它			###？这一点不是特别理解
4. 可能不能用for循环来写while循环

两段关于for和while循环的代码

    `for n in range(5):
        print(n)

    `n = 0
	while n < 5:
	    print(n)
	    n = n+1`

### 卡点：在while循环当中为什么得初始化计数器，怎样初始化计数器 ###

lecture2，主演是讲流程控制，分支和重复和顺序可以组成任何的流程，其中循环部分的for循环和while循环的比较。前面也讲到了字符串，字符串的相加，字符串的重复，也可以直接定义一个变量为字符串。也有讲到output和input的相关代码。

6/5/2019 9:09:20 PM 
用时大概1小时



