Gradle 构建工具
	用groovy语言写的 groovy最终被编译成字节码文件（.class） 然后运行在jVM  java虚拟机上
	
	groovy的一些基本语法
		注释和java一样 支持 // 和 /* */
		语句不需要分号结尾
		支持动态类型 定义变量的时候可以不指定类型 可以使用def关键字  def关键字也不是必须的
				eg: def var1 = 1
					def var2 = 'hello world';
		函数的类型也可以不指定
		函数的返回值也可以是无类型的 无类型定义的返回值函数 必须使用def关键字 最后一句代码的返回值就是笨函数的返回值 return
		
		
	groovy的数据类型
		java基本数据类型
				在Groovy代码中其实对应的是它们的包装数据类型。比如int对应为Integer，boolean对应为Boolean
		java的容器类有三种
		
				list：链表 底层对应java的list接口 一般用arraylist实现之
						变量定义：List变量由[]定义，比如  
						def aList = [5,'string',true] //List由[]定义，其元素可以是任何对象  
						变量存取：可以直接通过索引存取，而且不用担心索引越界。如果索引超过当前链表长度，List会自动  
						往该索引添加元素  
						assert aList[1] == 'string'  
						assert aList[5] == null //第6个元素为空  
						aList[100] = 100 //设置第101个元素的值为10  
						assert aList[100] == 100  
						那么，aList到现在为止有多少个元素呢？  
						println aList.size  ===>结果是101  


				map：键值对 
						变量定义：Map变量由[:]定义，比如  
						def aMap = ['key1':'value1','key2':true]  
						Map由[:]定义，注意其中的冒号。冒号左边是key，右边是Value。key必须是字符串，value可以是任何对象。另外，key可以用''或""包起来，也可以不用引号包起来。比如  
						def aNewMap = [key1:"value",key2:true]//其中的key1和key2默认被  
						处理成字符串"key1"和"key2"  
						不过Key要是不使用引号包起来的话，也会带来一定混淆，比如  
						def key1="wowo"  
						def aConfusedMap=[key1:"who am i?"]  
						aConfuseMap中的key1到底是"key1"还是变量key1的值“wowo”？显然，答案是字符串"key1"。如果要是"wowo"的话，则aConfusedMap的定义必须设置成：  
						def aConfusedMap=[(key1):"who am i?"]  
						Map中元素的存取更加方便，它支持多种方法：  
						println aMap.keyName    <==这种表达方法好像key就是aMap的一个成员变量一样  
						println aMap['keyName'] <==这种表达方法更传统一点  
						aMap.anotherkey = "i am map"  <==为map添加新元素 
										
		

				Range：范围list的一种拓展
					def aRange = 1..5 <==Range类型的变量 由begin值+两个点+end值表示  
                      左边这个aRange包含1,2,3,4,5这5个值  
						如果不想包含最后一个元素，则  
						def aRangeWithoutEnd = 1..<5  <==包含1,2,3,4这4个元素  
						println aRange.from  
						println aRange.to  
			
		闭包
			英文名closure 
				deg aClosure = {
					String param1，int param2 ->
					return param1 +int 
				}
				
			调用闭包的方式:
						aClosure.call("dddddd",100);
						aClosure("dddddd",100);
						
						
			如果闭包没定义参数的话，则隐含有一个参数，这个参数名字叫it，和this的作用类似。it代表闭包的参数。

						比如：  
						def greeting = { "Hello, $it!" }  
						assert greeting('Patrick') == 'Hello, Patrick!'  
						等同于：  
						def greeting = { it -> "Hello, $it!"}  
						assert greeting('Patrick') == 'Hello, Patrick!'  
						但是，如果在闭包定义时，采用下面这种写法，则表示闭包没有参数！  
						def noParamClosure = { -> true }  
						这个时候，我们就不能给noParamClosure传参数了！  
						noParamClosure ("test")  <==报错喔！  
						
						
						
						
						
						
						