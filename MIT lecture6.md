6/16/2019 8:11:42 PM 

# 递归，字典 #

## 测验准备 ##

一张纸和一个在线组件。

打开书/笔记。

不打开互联网，不打开电脑。

开始打印你想带的东西。


今天的步骤有点意思，不按照套路出牌。

lecture5的主要学习点
元组的不可变性。	列表的可变性。		走样，克隆。	可变性方面的影响。

6/17/2019 7:47:49 PM 
## 递归 ##
是以自我相似的方式重复项目的过程

### 卡点1 ###
Algorithmically:a	way	  to	design	solutions	to	problems	by	divide-and-conquer	or	decrease-and-conquer 

这句话中的divide-and-conquer	or	decrease-and-conquer 应该怎样理解呢？可以这样理解：divide-and-conquer分而治之；decrease-and-conquer少而治之。

从算法：解决问题的方法，分而治之或减少而治之。以此来减少问题的难度。
从语义：以函数自称的编程技术。在编程中，目标是没有有限的递归。必须具有1个或多个基础的情况下，很容易解决。必须在一些其他输入上解决相同的问题，目的是简化更大的问题输入

### 迭代算法如此之快 ###
循环的结构导致迭代算法。

可以通过循环每次迭代计算捕获一组状态变量的该更新

## 乘法 - 迭代解 ##
- 乘法a*b和加a到它本身上b次
- 捕获状态所用的方法。
	- 迭代数（i）开始在b处
	- i <-- i-1	and	stop	when 0
		
- 计算的当前值
	- 计算的当前值
	- result ß result + a 

    def mult_iter(a, b):    
	    result = 0 
	    while b > 0: 
	        result+= a 
	        b -= 1    
	    return result
	    	
	print(mult_iter(3,4))

上面这一段是说简单点就是，设定一个乘法，或者说迭代相加几个相同的数。

继续从流程控制的角度来分析这段代码。设定的一个函数中有一个while循环，里面执行两个命令。

## 乘法 - 迭代解 ##
递归步骤

思考对于同一个问题怎样降低一个问题的难度

基本情况

保持降低问题的难度直到到达一个可以直接解决问题的状态。
	when	b	=	1,	a*b	=	a	

## 阶乘 ##

n! = n*(n-1)*(n-2)*(n-3)* … * 1 

- 对于什么n，我知道这个阶乘？

n=1说明		if n ==1: return 1

- 怎样去降低问题的难度？重写的简单的东西，达到基本情况方面

n*(n-1)! 说明 else:      return n*factorial(n-1) 


## 递归功能范围示例 ##

	def fact(n):    
	    if n == 1: 
	        return 1    
	    else: 
	        return n*fact(n-1)
	    
	print(fact(4))

从流程控制的角度来说，只有一个两种情况的if从句。

## 一些观察 ##

- 一个函数每次递归调用创建其**自己的范围/环境**
- 在一个范围内的变量绑定不会被递归调用改变
- 控制流传递回先前的范围，一旦函数调用返回值


## 重复和递归的比较 ##

重复

	def factorial(n):
	    prod=1
	    for i in range(1,n+1):
	        prod*=i
	    return prod
	
	print(factorial(3))

从流程控制的角度来分析，就只有一个fo循环，前面一个初始化数据，后面一个return值


递归

	def factorial(n):
	    if n==1:
	        return 1
	    else:
	        return n*factorial(n-1)
	 
	print((factorial(3)))

从流程控制的角度来分析的话，只有一个有两种情况的if句，每个都会返回一个值或者式子。

- 递归可以更简单，更直观
- 递归可以更有效率从程序员POV
- 递归可以没有效率从计算机POV


## 归纳推理 ##


- 我们怎么知道递归码将会工作？
- mult_iter终止，因为b最初为正，并且每次循环减少1; 因此最终必须小于1
- 使用b> 1调用的mult使用较小版本的b进行递归调用;必须最终达到与b =1调用

	def mult_iter(a,b):
	    result=0
	    while b>0:
	        result+=a
	        b-=1
	    return result
	
	print(mult_iter(2,3))

下面的这段代码真的是像极了，一个故事：从前有座山，山上有座庙，庙里有个老和尚在给小和尚讲故事，讲得是什么呢？从前有座山，山上有座庙，庙里有个老和尚在给小和尚讲故事，讲得是什么呢？从前有座山，山上有座庙，庙里有个老和尚在给小和尚讲故事，讲得是什么呢？···

	def mult(a,b):
	    if b==1:
	        return a
	    else:
	        return a +mult(a,b-1)
	    
	print(mult(2,3))

## 数学归纳 ##

- 为了证明索引的整数声明是对于n的所有值真

明天持续更新中

姓名： 马林

学习内容：lecture6的小部分教程更新中。

总共用时：约2.5小时

适用对象：没有基础的小白预习或基础薄弱的初学者复习

为优化小伙伴的观看体验，简化观看步骤，可以打开这连接观看

## 递归 ##

一般情况，递归定义包括两部分。其中至少有一种**基本情形**可以直接打出某种特定情形的结果；
还至少有一种递归情形定义了该问题在其他情形下的结果，其他情形通常是同样问题的简化版本。

世界上最简单的递归定义就是自然数的阶乘函数

### 阶乘的迭代实现 ###
	def fa(n):
	    result=1
	    while n>1:
	        result =result*n
	        n-=1
	    return result

	print(fa(3))
	


### 阶乘的递归实现 ###

	def fb(n):
	    if n ==1:
	        return n
	    else:
	        return n*fb(n-1)
	    
	print(fb(3))

通过在函数体内调用函数，从而实现函数。

函数也可以当作自然的流程控制。

## 递归——斐波那契数列 ##

### 卡点计算兔子的繁殖情况 ###

最后，通过实践发现，通过纸和笔画图最能帮助理解问题，未成熟的画空圆，成熟的画实体圆。

说白了，如果只是通过观察数字的规律也能理解，只不过兔子问题将它与实际生活结合在一起。


	def fib(n):
	    if n==0 or n==1:
	        return 1
	    else:
	        return fib(n-1)+fib(n-2)
	    
	def testFib(n):
	    for i in range(n+1):
	        print('fib of',i,'=',fib(i))
	        
	testFib(5)

# ### 对于第一个定义中过于母兔的繁殖情况，与阶乘函数递归定义的不同点 ### #

- 它有两种基本情形，而不是一种。只要需要，我们可以有任意多种基本情形
- 在递归情形中，有连个递归调用，而不是一个。只要需要，可以有任意多个调用。

在编写上面的代码的过程是最容易的一个环节，而找到某种抽象方式表示问题的借，常常是编程过程中最困难的部分


## 递归——回文 ##

递归也可以应用于与数值无关的问题中，比如可以检查一个字符串在顺读和反读是否一致。

	def isPalindrome(s):
	
	    def toChars(s):
	        s = s.lower()
	        ans = ''  				##是将字母用空格隔开
	        for c in s:
	            if c in 'abcdefghijklmnopqrstuvwxyz':
	                ans = ans + c   ##是将字母用空格隔开
	        return ans
	
	    def isPal(s):
	        if len(s) <= 1:
	            return True
	        else:
	            return s[0] == s[-1] and isPal(s[1:-1])		##是从左到右进行求值，代码先检查字符串的第一个字母和最后一个字母是否相同，如果相同则去掉这两个字母后的字符串是否是回文
	
	    return isPal(toChars(s))

递归使用了一个很重要的思想——分治策略，将一个困难的问题分解成一组子问题逐个解决

## 字典 ##

字典的类型的对象与列表很相似，区别在于字典使用键对其中的值进行引用，可以将字典看作一个键/值对的集合。比如说，将学生的姓名和分值联系到一块。

形式——大括号

	def lyrics_to_frequencies(lyrics):
	    myDict = {}
	    for word in lyrics:
	        if word in myDict:
	            myDict[word] += 1
	        else:
	            myDict[word] = 1
	    return myDict
	    
	    
	she_loves_you = ['she', 'loves', 'you', 'yeah', 'yeah', 
	'yeah','she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	'she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	
	'you', 'think', "you've", 'lost', 'your', 'love',
	'well', 'i', 'saw', 'her', 'yesterday-yi-yay',
	"it's", 'you', "she's", 'thinking', 'of',
	'and', 'she', 'told', 'me', 'what', 'to', 'say-yi-yay',
	
	'she', 'says', 'she', 'loves', 'you',
	'and', 'you', 'know', 'that', "can't", 'be', 'bad',
	'yes', 'she', 'loves', 'you',
	'and', 'you', 'know', 'you', 'should', 'be', 'glad',
	
	'she', 'said', 'you', 'hurt', 'her', 'so',
	'she', 'almost', 'lost', 'her', 'mind',
	'and', 'now', 'she', 'says', 'she', 'knows',
	"you're", 'not', 'the', 'hurting', 'kind',
	
	'she', 'says', 'she', 'loves', 'you',
	'and', 'you', 'know', 'that', "can't", 'be', 'bad',
	'yes', 'she', 'loves', 'you',
	'and', 'you', 'know', 'you', 'should', 'be', 'glad',
	
	'oo', 'she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	'she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	'with', 'a', 'love', 'like', 'that',
	'you', 'know', 'you', 'should', 'be', 'glad',
	
	'you', 'know', "it's", 'up', 'to', 'you',
	'i', 'think', "it's", 'only', 'fair',
	'pride', 'can', 'hurt', 'you', 'too',
	'pologize', 'to', 'her',
	
	'Because', 'she', 'loves', 'you',
	'and', 'you', 'know', 'that', "can't", 'be', 'bad',
	'Yes', 'she', 'loves', 'you',
	'and', 'you', 'know', 'you', 'should', 'be', 'glad',
	
	'oo', 'she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	'she', 'loves', 'you', 'yeah', 'yeah', 'yeah',
	'with', 'a', 'love', 'like', 'that',
	'you', 'know', 'you', 'should', 'be', 'glad',
	'with', 'a', 'love', 'like', 'that',
	'you', 'know', 'you', 'should', 'be', 'glad',
	'with', 'a', 'love', 'like', 'that',
	'you', 'know', 'you', 'should', 'be', 'glad',
	'yeah', 'yeah', 'yeah',
	'yeah', 'yeah', 'yeah', 'yeah'
	]
	
	beatles = lyrics_to_frequencies(she_loves_you)
	
	print(beatles)

上面定义中代码块，主要是一个for循环，里面镶嵌有一个if句

如果加山一个判断最高频率的代码

	def most_common_words(freqs):
	    values = freqs.values()
	    best = max(freqs.values())
	    words = []
	    for k in freqs:
	        if freqs[k] == best:
	            words.append(k)
	    return (words, best)
	
	print(most_common_words(beatles))

这段代码，主要也是一个for循环，将频率最高的单词添到空的单词列表中。前面都是一些初始化的东西



