6/6/2019 4:48:32 PM 

开始今天的学习

今老师又说，请先下载幻灯片和代码

首先是回顾一下lecture2所讲的内容，字符串作为新的对象类型，然后是两个新概念 ，引入了分支，比如elif,else。然后是两种循环，loop和while循环。

这节课是更多地讨论字符串，更多对字符串和字符串对象的操作

三个对于字符串的算法
1. 猜测和检查算法
2. 近似解算法
3. 二分法算法

字符串可以是字母，数字，空格，特殊符号等字符组成的串。
而len()函数可以计算出字符串的长度

6/6/2019 6:02:29 PM 

6/6/2019 6:50:25 PM 

获取一个字符串的子串
slice对于字符串，我们称之为切片


### 需要注意的点 ###
字符串的第一个位置表示不是1而是0

字符串是不变的

for循环有一个循环变量，它是var，var可以是你想要的任何东西

### 卡点，根据MIT课程的代码输不出 ###
后来发现是自己没有多输入print()函数

包括想要看到切过字符串后的子字符串，没有赋值到一个新的变量，然后在打印出子字符串

for循环可以迭代任何值序列，而不仅仅是数字，也可以是字符串

    `s="abcdefghi"
	for char in s:
	    if char =='i' or char=='u':
	        print("there is an i or u")`
这里面的char是一个循环变量

大概用时小时
6/6/2019 8:03:57 PM 


6/7/2019 8:51:47 AM 

对于前天两种循环之间的比较的一个问题
### while循环中的计数器的表示方法 ###

下面这段代码是啦啦队的口号代码
    `an_letters = "aefhilmnorsxAEFHILMNORSX"
	word = input("I will cheer for you! Enter a word: ")
	times = int(input("Enthusiasm level (1-10): "))
	
	i = 0
	while i < len(word):
	    char = word[i]
	    if char in an_letters:
	        print("Give me an " + char + "! " + char)
	    else:
	        print("Give me a  " + char + "! " + char)
	    i += 1
	print("What does that spell?")
	for i in range(times):
	    print(word, "!!!")`
上面的一段关于while循环的代码就是首先创建一个计数器，然后对其初始化
i=0说明它将从0开始，通过索引i将等于0，1，2，3，4···
char=word[i] 它会让输入的单词的字母等于char
for i in range(times):print(word, "!!!")他只是说明一个循环次数，打印出word和三个感叹号

下面的一段代码是对上面的代码的简化，用for 循环代替while循环，减少了三行代码
### 在讲while循环转变成for循环的过程中，显示invalid character in identifier ###
后来搜索，发现可能里面夹杂有中文的空格，tab,或非文字字符
    `an_letters = "aefhilmnorsxAEFHILMNORSX"
	word = input("I will cheer for you! Enter a word: ")
	times = int(input("Enthusiasm level (1-10): "))
	
	for char in word:
	    if char in an_letters:
	        print("Give me an " + char + "! " + char)
	    else:
	        print("Give me a  " + char + "! " + char)
	print("What does that spell?")
	for i in range(times):
	    print(word, "!!!")`

现在看一下自己的工具箱里已经有了什么
整数，小数，布尔值，一些字符串操作，数学运算，条件和分支，还有for和while循环

下面是三种不同的算法，猜测和检查算法，近似算法，二分法算法
## 第一个算法是猜测和检查 ##
下面试猜测一个正数的立方根
    `cube = 8
	for guess in range(cube+1):
	    if guess**3 == cube:
	        print("Cube root of", cube, "is", guess)`

进阶版——猜测考虑进负数，break 语句，提前结束for循环
    `cube = -27
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
	        
	    print('Cube root of ' + str(cube) + ' is ' + str(guess))`

## 第二个算法，近似解 ##

### 卡点，如何在Spyder中同时编辑多行 ###
选中多行后：　Ctrl + 1: 注释/反注释

### 9不是一个完美的立方体吗 ###

有时候可能不在乎9是不是一个完美的立方体，只告诉我比较接近的一个答案

近似解从猜测开始并以一些小值递增

APPROXIMATE SOLUTIONS 
 good enough solution
 start with a guess and increment by some small value 
 keep guessing if |guess3-cube| >= epsilon for some small epsilon里面的epsilon的存在是为了提供一个更好的解决方案
 decreasing increment size  slower program 精度越大的话，当然所需要的时间也就会多一些
 increasing epsilon  less accurate answer 如果这增加了epsilon，你就会牺牲精度，从而更快的得到结果

    `cube = 27
	epsilon = 0.1
	guess = 0.0
	increment = 0.01
	num_guesses = 0
	# look for close enough answer and make sure
	# didn't accidentally skip the close enough bound
	while abs(guess**3 - cube) >= epsilon and guess <= cube:
	    guess += increment
	    num_guesses += 1
	print('num_guesses =', num_guesses)
	if abs(guess**3 - cube) >= epsilon:
	    print('Failed on cube root of', cube, "with these parameters.")
	else:
	    print(guess, 'is close to the cube root of', cube)`
上面几行都是关于初始化变量的，我们想找cube立方体，从guess=0.0开始找，以0.01的增量开始，而num_guesses的存在就是为了好玩，跟踪猜测是数量
里面的while循环如果不加guess <=cube的话，则可鞥跳过那个结果是会出现无限循环的可能

最后的9分钟时=是关于二分搜索算法
6/7/2019 10:52:48 AM 

6/7/2019 2:28:40 PM 
## 二分搜索算法 ##
哇塞，在课堂上参与一个游戏，居然可以奖励一个google眼镜，最后这个男孩虽然失败了，但是仍然获得了这个奖品。

这个游戏，自己在gitbub开源的一个课程上，前段时间自己刚做过，[http://https://github.com/jackfrued/Python-100-Days/tree/master/Day01-15](http://https://github.com/jackfrued/Python-100-Days/tree/master/Day01-15)

这个游戏的代码，附上，有需要的同学可以自己在计算机上玩玩哦

    `"""
	猜数字游戏
	计算机出一个1~100之间的随机数由人来猜
	计算机根据人猜的数字分别给出提示大一点/小一点/猜对了
	"""
	
	import random
	
	answer = random.randint(1, 100)
	counter = 0
	while True:
	    counter += 1
	    number = int(input('请输入: '))
	    if number < answer:
	        print('大一点')
	    elif number > answer:
	        print('小一点')
	    else:
	        print('恭喜你猜对了!')
	        break
	print('你总共猜了%d次' % counter)
	if counter > 7:
	    print('你的智商余额明显不足')`
guess converges on the order of log2N steps 
猜测收敛于log2N步骤的顺序

不知不觉发现自己正在看英文字幕，但是并没有影响理解

这个游戏主要是对分搜索bisection search

    `cube = 27
	#cube = 8120601
	# won't work with x < 1 because initial upper bound is less than ans
	#cube = 0.25
	epsilon = 0.01
	num_guesses = 0
	low = 0
	high = cube
	#上面继续是一些初始化变量
	guess = (high + low)/2.0
	while abs(guess**3 - cube) >= epsilon:
	    if guess**3 < cube:
	        # look only in upper half search space
	        low = guess
	    else:
	        # look only in lower half search space
	        high = guess
	    # next guess is halfway in search space
	    guess = (high + low)/2.0
	    num_guesses += 1
	print('num_guesses =', num_guesses)
	print(guess, 'is close to the cube root of', cube)`

其中的if guess**3<cube: low =guess,这段话是自己结合那个游戏才能立即清楚的，一开始low是0，后来，如果猜小了的话，那么low就变成你猜的那个数字，以此，缩小猜的范围。

里面又出现了guess=（high+low)/2.0,这说明继续猜guess
6/7/2019 3:32:21 PM 

继续做一下他们的练习题
    `s1="mit u rock"
	s2="i rule mit"
	if len(s1)==len(s2):
	    for char1 in s1:
	        for char2 in s2:
	            if char1==char2:
	                print("common letter")
	                break`
注意点

- s1的第一个字母m在和其他的字符串比较的时候，其中也会空格键比较，因为空格也是一个字符串
- s1的第一个字母m在比较到s2的第八个字符的时候，会break，不用继续比较字符i和t
- 然后继续s1中的第二个字母i，依次往下比较，最后会打印7次
上面的练习题对于用到控制流中的分支和循环

下面将会用到切片
    `s="6.00 is 6.0001 and 6.0002"
	new_str=" "
	new_str+=s[-1]
	new_str+=s[0]            
	new_str+=s[4::30]
	new_str+=s[13:10:-1]
	print(new_str)`
new_str+=s[-1]说明新的字符串是2
new_str+=s[0] 说明新的字符串是26
new_str+=s[4::30]说明新的字符串是26加一个空格，因为正着数，从0开始，第四个是空格，默认停止位置是字符串最后一个字符，步长是30
new_str+=s[13:10:-1]说明新的字符串是是从索引13这个位置开始，往前10这个位置结束，0001 数过后第10个位置是0，第11和12这三个位置也是0，第13这个位置是1，步长是-1说明是往后数，所以分析下来这个切片就是100，加上前面的就是26 100
6/7/2019 4:14:46 PM 
lecture3的后半部分总共用时3.5小时，也包括0.6个小时的练习题

姓名： 马林
学习内容：lecture3.String Manipulation, Guess and Check, Approximations 的后半部分，练习题
学习时间段：6/7/2019 8:51:47 AM到6/7/2019 10:52:48 AM
         6/7/2019 2:28:40 PM 到6/7/2019 4:14:46 PM 
总共用时：约3.5小时，也包括0.6个小时的练习题
下面的文件中是自己学习时的头脑中思维的变。自己比较喜欢记录自己的学习时头脑中的想的过程，以此来监控自己的大脑，一方面，方便自己理清思路，另一方面，方便自己沉浸式学习，避免大脑偷懒，不查找答案解决问题。

 

