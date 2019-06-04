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

### 卡点1 ###
不知道为什么在GitHub desk上没有显示变化，所以也就无法推到网上？
尝试一下在网上在自己的GitHub在克隆一个到本地，