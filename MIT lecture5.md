
翻看了一下MIT的python官网，打开相关的网页要往下拉，否则你可能认为网页出现了问题，一直留在原网页，其实真正的内容是在下面。

6/9/2019 7:06:13 PM 

和做lecture4一样，先直接上PPT吧

# TUPLES，LISTS，ALIASING，MUTABILITY，CLONING 元组，列表，走样，mutablility，可变性，克隆 #

## LAST TIME  ##
- functions
- 分解 - 创建结构
-  抽象 - 压制细节
-  from now on will be using functions a lot

## 今天 ##
-  have seen variable types: int, float, bool,string 
-  introduce new compound data types复合数据类型 ——元组，列表
-  idea of aliasing 别名
-  可变性的想法
-  idea of cloning

## 元组tuples ##
元组和与字符串类型相似，字符串是字符序列，而元组是元素的序列。元组不仅仅可以是字符串序列，它可以是任何元素的序列，比如，整数，小数，字符串等
- 有序的元素序列，可以混合元素类型
- 无法更改元素值，**不可变**。你创建好后是没有办法修改的 
- 用括号表示一个元组，而不是函数的调用

te = () 这代表一个空的元组，长度是0，里面什么也没有
t = (2,"mit",3) 通过使用逗号来分割每一个元素。这个元组包含三个元素，通过变量t来访问，第一个是整数，第二个是字符串，第三个是另一个整数。就像字符串一样，我们可以使用索引元组来查找特定元素

t[0] 说明元组里的第一元素是2 evaluates to 2 
(2,"mit",3) + (5,6) 可以通过加号，将两个元组组合到一块，形成一个更大的元组 evaluates to (2,"mit",3,5,6) 

再一次非常像字符串，元组可以用切片，将元组切开

t[1:2] 
从索引1切到索引2 slice tuple, evaluates to ("mit",) 
这里面的一个逗号，不是一个意外，而是代表一个元素，如果没有逗号的话，它只是一个字符串。所以这里逗号的存在说明这是一个只有一个元素的元组

t[1:3] 
从索引1切到索引3，然后减一，得到具有两个元素的元组slice tuple, evaluates to ("mit",3) 

evaluates to 3 
通常习惯用元素的数目来代表元组的长度len(t)
### PPT上不容易敲出的东西，如果容易理解的话，直接复制粘贴 ###

## 元组 ##
- conveniently used to swap variable values 方便地用于**交换**变量值
x=y
y=x
这是错误的形式

temp = x
x = y 
y = temp
这是对的，因为创建了一个临时的变量

(x, y) = (y, x) 
这也是对的，这就是元组的作用交换变量

- 用于从函数返回多个值

    def quotient_and_remainder(x, y):
	    q = x // y
	    r = x % y
	    return (q, r)
	    
	(quot, rem) = quotient_and_remainder(5,3)
	print(quot)
	print(rem)
因为函数一般是只能返回一个值，但是用元组的话就能返回很多个值。因为元组拥有数列集合

## 操纵TUPLES ##
- 可以迭代元组
刚才有一段时间，由于室友的原因，跑神了几分钟，所以视频中的关于操纵tuples没有听懂，回过神继续把这段视频，加上这张PPT理解完成后，就休息了。

元组非常的有用，因为它是数据的集合

下面这段函数能够收集任何的数据集，可以提取一些非常基础的基本的东西来自你任何数据集的信息

元组的条件是它必须是一个确定的元组

aTuple:(( ),( ),( ))
这里的外括号说明了这是一个元组，而元组里的这三个元素实际上都是元组。以及这些内部元组对象中的每一个，实际上包含两个与元素，第一个元素是整数，第二个元素是字符串。这些都是先决条件，这个函数假设是一个元组，在实际行动之前，

    `def get_data(aTuple):
	    """
	    aTuple, tuple of tuples (int, string)
	    Extracts all integers from aTuple and sets 
	    them as elements in a new tuple. 
	    Extracts all unique strings from from aTuple 
	    and sets them as elements in a new tuple.
	    Returns a tuple of the minimum integer, the
	    maximum integer, and the number of unique strings
	    """
	    nums = ()    # empty tuple
	    words = ()
	    for t in aTuple:
	        # concatenating with a singleton tuple
	        nums = nums + (t[0],)   
	        # only add words haven't added before
	        if t[1] not in words:   
	            words = words + (t[1],)
	    min_n = min(nums)
	    max_n = max(nums)
	    unique_words = len(words)
	    return (min_n, max_n, unique_words)`

首先创建两个空的元组，nums和words
然后有一个for循环，将迭代元组中的每一个元素，直接迭代的是元组的对象，而不是迭代索引
每一次迭代，我们执行的是下面这一段，每次我们都要创建一个新的对象，并将其重新分配到变量中。每一次循环中我们都要看看之前的nums是什么，之前的words是什么，这将使用单列元组增加

例子代码

    def get_data(aTuple):
	    """
	    aTuple, tuple of tuples (int, string)
	    Extracts all integers from aTuple and sets 
	    them as elements in a new tuple. 
	    Extracts all unique strings from from aTuple 
	    and sets them as elements in a new tuple.
	    Returns a tuple of the minimum integer, the
	    maximum integer, and the number of unique strings
	    """
	    nums = ()    # empty tuple
	    words = ()
	    for t in aTuple:
	        # concatenating with a singleton tuple
	        nums = nums + (t[0],)   
	        # only add words haven't added before
	        if t[1] not in words:   
	            words = words + (t[1],)
	    min_n = min(nums)
	    max_n = max(nums)
	    unique_words = len(words)
	    return (min_n, max_n, unique_words)
	
	# apply to any data you want!
	tswift = ((2014,"Katy"),
	          (2014, "Harry"),
	          (2012,"Jake"), 
	          (2010,"Taylor"), 
	          (2008,"Joe"))    
	(min_year, max_year, num_people) = get_data(tswift)
	print("From", min_year, "to", max_year, \
	        "Taylor Swift wrote songs about", num_people, "people!")

结束
6/9/2019 9:36:23 PM 刨去中间的，总共大概用时1.3小时，弄了视频的3/8的内容

6/10/2019 7:52:52 PM  
继续lecture5的学习，首先先回顾一下leture5的前半部分
刚才本打算调整一下字体的大小，但是折腾了一会，发现不行但是时间已经过去0.3小时了，所以暂且先放到这，先看今天的学习要紧。
6/10/2019 8:13:33 PM 

大致回顾了一下昨天学习的元组，一个混合元素类型对象，作用可以是交换变量，也可以返回多个数值，和字符相同的是可以也可以进行切割。

好，继续往下学习。

老师再三强调元组是不可变的。现在看一个非常相似的数据结构，称为列表。除了元组是不可变的，列表将成为一个可变的对象。

列表也是包含了任何类型的元素或任何类型的对象，用来表示一个清单，用方括号来代替代替括号，不同之处在于列表是一个可变的对象

打开方括号，你可以拥有不同类型的元素和对象甚至列表清单。列表里面也可以是有列表

a_list = [] 说明是一个空的列表
L = [2, 'a', 4, [1,2]] 
i = 2 
L[i-1]  evaluates to ‘a’ since L[1]='a' above

决定放弃课程发的视频，直接看看bilibili上的，因为一，发的视频中有的字幕是看不清的，而哔哩哔哩可以看请。原因二，哔哩哔哩也可以直接听音频。原因三，哔哩哔可以通过左右键来调进度，而发的视频必须得经过鼠标。所以如果再电脑上看哔哩哔哩的话，可以直接再网页上看。

接下来会着重介绍一下，**列表的可变性**

## 改变列表的元素 ##
L = [2, 1, 3] 
L[1] = 5 
L is now [2, 5, 3], note this is the same object L

## 在列表上进行迭代 ##
-  compute the sum of elements of a list 
-  common pattern, iterate over list elements常见模式，迭代列表元素

    def sum_elem_method2(L):
	total = 0 
	for i in range(len(L)): 
	total += L[i] 
	print total
	print(sum_elem_method1([1,2,3,4]))
    
    def sum_elem_method2(L):
    total = 0 
    for i in L: 
        total += i 
    return total
	print(sum_elem_method2([1,2,3,4]))
上面两段代码是一样的
- 注意 print(sum_elem_method2([1,2,3,4]))    • range(n) goes from 0 to n-1

## 对列表的操作-加 ##
- add elements to end of list with L.append(element) 
- mutates the list! L = [2,1,3]  	L.append(5)  L is now [2,1,3,5]
- L.append(element) 中的逗号是什么意思
lists are Python objects, everything in Python is an object 
objects have data 
对象有方法和功能
access this information by object_name.do_something()  

- to combine lists together use concatenation, + operator, to give you a new list 
- mutate list with L.extend(some_list)

L1 = [2,1,3] 
L2 = [4,5,6]
L3 = L1 + L2
L3 is [2,1,3,4,5,6] L1, L2 unchanged 

L1.extend([0,6])  mutated L1 to [2,1,3,0,6] 


## 关于列表的操作删除 ##
- delete element at a specific index with del(L[index]) 
- remove element at end of list with L.pop(), returns the removed element 
- remove a specific element with L.remove(element) 

L = [2,1,3,6,3,7,0] # do below in order 
L.remove(2) mutates L = [1,3,6,3,7,0]  	looks for the element and removes it 
L.remove(3) mutates L = [1,6,3,7,0]  		 if element occurs multiple times, removes first occurrence
del(L[1])  mutates L = [1,3,7,0] 
L.pop()  returns 0 and mutates L = [1,3,7]		remove element at end of list with L.pop(), returns the removed element 

6/10/2019 9:31:34 PM 洗个澡回来继续做6/10/2019 9:56:56 PM 

## 将列表转化成字符串并且返回 ##
就像我们将整数转化成小数一样，我们也可以将字符串转化成列表，用lisr(s),将字符串中的每一个字符都转化成列表中的元素
L=[9,6,0,3] 
sorted(L)  returns sorted list, does not mutate L 这里的列表L没有发生改变
L.sort()  mutates L=[0,3,6,9] 						这里的L发生了改变
L.reverse()  mutates L=[9,6,3,0]					

## 突变，混乱，克隆 ##
这三个名词也都是关于列表的

## 一个类比 ##
 attributes of a person ◦ singer, rich 
 he is known by many names 
 all nicknames point to the same person 
• add new attribute to one nickname … 
• … all his nicknames refer to old attributes AND all new ones

Justin Bieber   singer rich troublemaker
The Bieb 		singer rich troublemaker
JBeebs 			singer rich troublemaker 

## 别称 ##
 hot is an alias for warm – changing one changes the other! 

    `a = 1
	b = a
	print(a)
	print(b)
	
	warm = ['red', 'yellow', 'orange']
	hot = warm
	hot.append('pink')
	print(hot)
	print(warm)`

## 克隆一份列表 ##
 create a new list and** copy every element** using chill = cool[:]

    ##########################
	### EXAMPLE: cloning
	##########################
	cool = ['blue', 'green', 'grey']
	chill = cool[:]
	chill.append('black')
	print(chill)
	print(cool)

## 分类列表 ##
- 调用sort（）会改变列表，不返回任何内容
- 调用sorted（）不会改变列表，必须将结果赋给变量
总结下来，就是sort()变，而sorted()不变

    ##########################
	### EXAMPLE: sorting with/without mutation
	##########################
	warm = ['red', 'yellow', 'orange']
	sortedwarm = warm.sort()#调用sort（）会改变列表，不返回任何内容
	print(warm)
	print(sortedwarm)
	
	cool = ['grey', 'green', 'blue']
	sortedcool = sorted(cool)#调用sorted（）不会改变列表，必须将结果赋给变量
	print(cool)
	print(sortedcool)

## 列表的列表的列表 ##
- 可以有嵌套列表
- side effects still possible after mutation

    ##########################
	### EXAMPLE: lists of lists of lists...
	##########################
	warm = ['yellow', 'orange']
	hot = ['red']
	brightcolors = [warm]
	brightcolors.append(hot)
	
	print(brightcolors)
	hot.append('pink')
	print(hot)
	print(brightcolors)
- 避免在迭代列表时改变列表
- 
代码只有运行后，才能感受到它真正的作用。

时间不够了，留个小尾巴，明天做

姓名： 马林
学习内容：lecture5后大半部分
总共用时：约2.4小时
目前lecture5总共用时;约3.7小时
思维记录：下面的文件中是自己学习时的头脑中思维的变化过程。自己比较喜欢记录自己的学习时头脑中的想的过程，以此来监控自己的大脑，一方面，方便自己理清思路，另一方面，方便自己沉浸式学习，避免大脑偷懒，不查找答案解决问题。

6/10/2019 11:09:38 PM 
 
6/11/2019 这天是花了大概0.3个小时，回顾了昨天的内容。

6/12/2019 7:58:37 PM 
今天，继续学习lecture5的最后内容。

想法：如果这MIT Python课看完后，可以写一个小的教程。当作梳理，也可以帮助别人。

克隆的作用就是，原对象可以保持不变，可以减少副作用给的影响。

sort函数的作用是对原数列进行排列

## 变异和迭代在Python Tutor中试试这个 ##


- avoid mutating a list as you are iterating over it 

    ################################
	### EXAMPLE: mutating a list while iterating over it
	################################
	def remove_dups(L1, L2):
	    for e in L1:
	        if e in L2:
	            L1.remove(e)
	      
	def remove_dups_new(L1, L2):
	    L1_copy = L1[:]
	    for e in L1_copy:
	        if e in L2:
	            L1.remove(e)
	
	L1 = [1, 2, 3, 4]
	L2 = [1, 2, 5, 6]
	remove_dups(L1, L2)
	print(L1, L2)
	
	L1 = [1, 2, 3, 4]
	L2 = [1, 2, 5, 6]
	remove_dups_new(L1, L2)
	print(L1, L2)

## 上面两段程序运行起来L1 is [2,3,4] not [3,4] Why?  ##
- Python uses an internal counter to keep track of index it is in the loop 
-  mutating changes the list length but Python doesn’t update the counter 
-   loop never sees element 2.这句话翻译过来就是循环永远不会看到元素2。里面的这段话不是特别理解？

接着做练习题吧

练习1
    L1=["馒头","咸菜"]
	L2=["大鱼","大肉"]
	brunch=L1
	L1.append("白开水")
	brunch.extend(L2)
	print(L1)
	print(L2)

练习2
    l1=['re']
	l2=['mi']
	l3=['do']
	l4=l1+l2
	l3.extend(l4)
	l3.sort()
	del(l3[0])
	l3.append(['fa','la'])
	print(l3)

练习3
我个人认为是关于索引和数字的容易弄混的区别判断。
    l=["life","answer",42,0]
	for thing in l:
	    if thing==0:
	        l[thing]="universe"
	    elif thing==42:
	        l[1]="everything"
	print(l)

练习4
各人认为主要是对于元组的形式（圆括号逗号）和字符串的形式的考察，它们的性质的考察
def always_sunny(t1,t2):
sun=("sunny","sun")
first= t1[0]+t2[0]
return(sun[0],first)
print(always_sunny('clody','clod',))

明天在好好看看练习4
6/12/2019 10:03:46 PM 

姓名： 马林
学习内容：lecture5后大半部分
总共用时：约1.5小时
思维记录：下面的文件中是自己学习时的头脑中思维的变化过程。自己比较喜欢记录自己的学习时头脑中的想的过程，以此来监控自己的大脑，一方面，方便自己理清思路，另一方面，方便自己沉浸式学习，避免大脑偷懒，不查找答案解决问题。





