# Python 类的继承 # 

lecture 8 讲得内容

1. 通过类的数据抽象表达
2. 坐标的例子
3. 分数的例子

lecture 9 即将要讲的内容

1. 更多关于类的东西
	- getters and setters
	- 信息隐藏
	- 类变量

2. 承受

## 类的实施和用，它们的区别 ##

从两个不同的角度编写代码

**实施**类实现新的对象类型

- **定义**一个类
- 定义一个类的**属性**（对象是什么）
- 定义方法（怎样用这个类）


在代码中**使用**新的对象类型

- 创建对象类型的**实例**
- 与它们**合作**

对象类的类定义

- 类的名字是它的类型

  class Coordinate(object) 

- class一般是定义的
	- 在定义类时使用self来引用某个实例
	
	  (self.x – self.y)**2
	- self是类定义中方法的参数

- class定义了所有实例中通用的数据和方法


一个类的实例

- 实例是一个特殊的对象
  coord = Coordinate(1,2) 

- 数据属性值因实例而异

  c1 = Coordinate(1,2) 		c2 = Coordinate(3,4) 

- c1和c2具有不同的数据属性值c1.x和c2.x，因为它们是不同的对象

instance具有类的结构

## 为什么要使用OOP和类别的对象？ ##

- 模仿现实生活
- 将不同对象组成相同类型的部分
0岁的小猫，1岁的小猫，2岁的小猫，它们的样子是不一样

## 对象组有属性（RECAP） ##

-  **数据属性**
	-  你如何用数据表示你的对象？
	-  **它是什么**
	-  对于一个坐标：x值和y值
	-  对于一个动物：年龄，名字

- **程序属性**（行为/操作/**方法**）
	- 有人如何与对象互动？
	- **它能做什么**
	- 对于坐标：找到两者之间的距离
	- 对于动物：发出声音

## 怎样去定义一个类 ##

*插入图片第8张幻灯片*

## GETTER和SETTER方法 ##

getter 和 setter 应该在类外使用来访问数据属性

*插入图片第9张幻灯片*

## 实例和数据表符号（RECAP) ##

- **实例化**创建对象的实例		a = Animal(3) 
- **点表示法**用来访问属性（数据和方法）虽然用getter 和 setter 来访问数据属性更好

a.age 
- 访问数据的属性
- 允许，但是不推荐

a.get_age()
- 访问的方法
- 最好用getters 和 setters

## 信息隐藏 ##

- 类定义的作者可能会更改数据属性变量名称

	class Animal(object): 
		def __init__(self, age): 
			self.years = age 
		def get_age(self): 
			return self.years 

用years来代替年龄的数据属性

- 如果你正在**访问数据类型**，类外面的和**更改**后的类的数据类型，可能会出错
- 在类之外，用getter 和 setter 方法而不是 a.get_age()，更不是 a.age
	- 好的类型
	- 易于维护代码
	- 防止错误

## Python 不是特别擅长信息隐藏 ##

- 允许您从类定义外面**访问数据** print(a.age) 
- 允许你从类定义外面**写数据** a.age = 'infinite' 
- 允许您从类定义外面为实例**创建数据属性** a.size = "tiny"
- 做这些都不是好风格！

## 默认参数 ##

父类

	class Animal(object):
	    def __init__(self, age):
	        self.age = age
	        self.name = None
	    def get_age(self):
	        return self.age
	    def get_name(self):
	        return self.name
	    def set_age(self, newage):
	        self.age = newage
	    def set_name(self, newname=""):
	        self.name = newname
	    def __str__(self):
	        return "animal:"+str(self.name)+":"+str(self.age)
	        
	print("\n---- animal tests ----")
	a = Animal(4)
	print(a)
	print(a.get_age())
	a.set_name("fluffy")
	print(a)
	a.set_name()
	print(a)

打印出的结果是

---- animal tests ----
- animal:None:4
- 4
- animal:fluffy:4
- animal::4



- 第一个打印出的是animal:None:4。为什么？因为a = Animal(4)，说明年龄是4，但是没有设定名字，所以就是默认值None。打印的是返回的值return "animal:"+str(self.name)+":"+str(self.age)


- 第二个打印出的是4.是因为打印函数里面是a.get_age()，说明是只想得到变量a的年龄


- 第三个打印出的是animal:fluffy:4。和第一个打印出的结果是名字不一样，是因为设置了变量a的名字a.set_name("fluffy")，剩下的保持不变


- 第四个打印出的是animal::4。和第一个第三个打印出的结果不一样的还是名字，还是对变量a进行了设置，剩下的保持不变



- 如果没有给出实际参数，则使用形式参数的默认参数

	def set_name(self, newname=""): 
		self.name = newname 

- 这里使用的默认参数
- 
	a = Animal(3) 
	a.set_name() 
	print(a.get_name()) 
这个打印出来的是空的

- 传入的参数在这里使用
- 
	a = Animal(3) 
	a.set_name("fluffy") 
	print(a.get_name())
这个打印的是fluffy


子类

	class Cat(Animal):          ###对动物的子类猫，进行新的函数的定义和父类函数的覆盖
	    def speak(self):		#
	        print("meow")
	    def __str__(self):
	        return "cat:"+str(self.name)+":"+str(self.age)
    
	print("\n---- cat tests ----")
	c = Cat(5)
	c.set_name("fluffy")
	print(c)
	c.speak()
	print(c.get_age())
	#a.speak() # error because there is no speak method for Animal class

打印出来的结果是

---- cat tests ----

- cat:fluffy:5
- meow
- 5

__init__ is not missing, uses the Animal version动物的子类猫中的默认值用的是父类动物的





姓名： 马林

学习内容：lecture 9 一半内容

打卡天数：第29天

总共用时：约2.5h

6/30/2019 8:50:22 AM  

## 继承 ##
- 父类
- 子类
	- 继承父类所有的数据和行动
	- 增加更多的信息
	- 增加更多的行为
	- 覆盖父类的行为

1. 父类 			  动物
2. 子类 			人 猫 兔子
3. 子类的子类		学生

你可以拥有多个级别的子类

## 用哪种方法 ##

- 子类可以具有与父类同名的方法
- 对于类的实例，在当前类定义中查找方法名称
- 如果找不到，请在层次结构中查找方法名称（在父级中，然后是祖父级，等等）
- 在您使用该方法名称找到的层次结构中使用第一种方法

## 动物的子类人 ##

	class Person(Animal):                   #人是动物的子类
	    def __init__(self, name, age):      
	        Animal.__init__(self, age)      #召唤动物构造
	        self.set_name(name)             #召唤动物的方法
	        self.friends = []               #增加一个新的数据属性
	    def get_friends(self):              #下面的是新方法
	        return self.friends
	    def speak(self):
	        print("hello")
	    def add_friend(self, fname):
	        if fname not in self.friends:
	            self.friends.append(fname)
	    def age_diff(self, other):
	        diff = self.age - other.age
	        print(abs(diff), "year difference")
	    def __str__(self):                  #覆盖父类动物的__str__方法
	        return "person:"+str(self.name)+":"+str(self.age)
	
	print("\n---- person tests ----")
	p1 = Person("jack", 30)
	p2 = Person("jill", 25)
	print(p1.get_name())
	print(p1.get_age())
	print(p2.get_name())
	print(p2.get_age())
	print(p1)
	p1.speak()
	p1.age_diff(p2) 

相关的解释在代码中


子类的子类——动物的子类人的子类的学生

当然下面这段代码也得接在上面代码后面

	import random               #从随机数种引进方法
	
	class Student(Person):      #继承的是动物和人的属性
	    def __init__(self, name, age, major=None):
	        Person.__init__(self, name, age)
	        self.major = major  #增加新的数
	    def __str__(self):
	        return "student:"+str(self.name)+":"+str(self.age)+":"+str(self.major)
	    def change_major(self, major):
	        self.major = major
	    def speak(self):
	        r = random.random()	#random()方法返回的是小数[0,1)
	        if r < 0.25:
	            print("i have homework")
	        elif 0.25 <= r < 0.5:
	            print("i need sleep")
	        elif 0.5 <= r < 0.75:
	            print("i should eat")
	        else:
	            print("i am watching tv")
	
	print("\n---- student tests ----")
	s1 = Student('alice', 20, "CS")
	s2 = Student('beth', 18)
	print(s1)
	print(s2)
	print(s1.get_name(),"says:", end=" ")
	s1.speak()
	print(s2.get_name(),"says:", end=" ")
	s2.speak()

打印出的结果是

---- student tests ----



- student:alice:20:CS


- student:beth:18:None


- alice says: i need sleep


- beth says: i am watching tv

当然每次打印出说的话会有不同

## 类变量和兔子分类 ##

类变量及其值在类的所有实例之间共享

	class Rabbit(Animal):
	    # a class variable, tag, shared across all instances
	    tag = 1                     #tag是一个类变量，用于为每个新兔子实例提供唯一ID的标记
	    def __init__(self, age, parent1=None, parent2=None):
	        Animal.__init__(self, age)
	        self.parent1 = parent1
	        self.parent2 = parent2
	        self.rid = Rabbit.tag   #实例变量用来访问类变量
	        Rabbit.tag += 1         #递增类变量会为可能引用它的所有实例更改它
	    def get_rid(self):
	        # zfill used to add leading zeroes 001 instead of 1
	        return str(self.rid).zfill(3)   #方法中关于在字符串的开始的表示方式是001而不是1
	    def get_parent1(self):              #getter方法使兔子类的特异化
	        return self.parent1             #当然也继承它的父类的get_name和get_age
	    def get_parent2(self):
	        return self.parent2
	    def __add__(self, other):           #
	        # returning object of same type as this class
	        return Rabbit(0, self, other)	#recall Rabbit’s __init__(self, age, parent1=None, parent2=None)这里的0是年龄，self是一个父，other是一个母
	    def __eq__(self, other):			#如果他们有相同的两个父母，则决定两只兔子是平等的
	        # compare the ids of self and other's parents
	        # don't care about the order of the parents
	        # the backslash tells python I want to break up my line
	        parents_same = self.parent1.rid == other.parent1.rid \		#这里用到了布尔值
	                       and self.parent2.rid == other.parent2.rid	#因为ids是唯一的，所以比较的是父母的ids
	        parents_opposite = self.parent2.rid == other.parent1.rid \
	                           and self.parent1.rid == other.parent2.rid
	        return parents_same or parents_opposite
	    def __str__(self):
	        return "rabbit:"+ self.get_rid()
	
	print("\n---- rabbit tests ----")
	print("---- testing creating rabbits ----")
	r1 = Rabbit(3)
	r2 = Rabbit(4)
	r3 = Rabbit(5)
	print("r1:", r1)
	print("r2:", r2)
	print("r3:", r3)
	print("r1 parent1:", r1.get_parent1())
	print("r1 parent2:", r1.get_parent2())
	
	print("---- testing rabbit addition ----")
	r4 = r1+r2   # r1.__add__(r2)
	print("r1:", r1)
	print("r2:", r2)
	print("r4:", r4)
	print("r4 parent1:", r4.get_parent1())
	print("r4 parent2:", r4.get_parent2())
	
	print("---- testing rabbit equality ----")
	r5 = r3+r4
	r6 = r4+r3
	print("r3:", r3)
	print("r4:", r4)
	print("r5:", r5)
	print("r6:", r6)
	print("r5 parent1:", r5.get_parent1())
	print("r5 parent2:", r5.get_parent2())
	print("r6 parent1:", r6.get_parent1())
	print("r6 parent2:", r6.get_parent2())
	print("r5 and r6 have same parents?", r5 == r6)
	print("r4 and r6 have same parents?", r4 == r6)

上面的代码不要被数量给下住了，其实把这代码跑一下还是非常容易理解的。

结合代码的运行还是比较容易理解的，因为只有一行行代码是非常抽象的，输入什么出来什么才，才有一个实在的感受。

## 面向对象的程序设计 ##
- 创建自己的**数据集合**
- **组织**信息
- **分解**工作
- 以**一致**的方式访问信息
- 添加复杂的**层次**
- 像函数一样，类是编程中**分解**和**抽象**的机制


姓名： 马林

学习内容：lecture 9 更新完成

打卡天数：第30天

总共用时：约2.5h






