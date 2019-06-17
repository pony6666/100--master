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


姓名： 马林

学习内容：lecture6的小部分教程更新中。

总共用时：约2.5小时

适用对象：没有基础的小白预习或基础薄弱的初学者复习