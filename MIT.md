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




