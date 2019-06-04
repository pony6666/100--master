
## day1 ##

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

## day2 ##

### 进步点1 ###

运算符号//斜双杠代表的是除后剩下的整数。而%是代表除后剩下的余数。

### 卡点1 ###
    `c=1+5g
	 print(type(c))`
这个代码显示错误

最后发现只有c=1+5j,等号只有是j才能运行成功

### 练习的代码 ###
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

## day3当时做了以后忘了保存，暂时先继续day4 ##


## day4 ##
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





