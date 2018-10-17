# 2018-10-15
- pass<br>
	pass语句为占位符，为了防止程序报错：如若想定义一个函数，但是暂时还用不到，想之后再写，可以这样：
	```python
	def sample(n_samples):
    pass
    ```
    这样是为了防止定义了一个空函数导致的程序报错。
- 复数<br>
	python中支持复数的运算，格式为a + bj或者complex(a,b);
- 随机数<br>
	python中随机的使用可以说比C中简单许多：
	```python
	choice(Seq) #从序列Seq中随机挑选一个元素
	randrange(Start,Stop,Step) #Step缺省值为1，start包含在范围内，stop不包含在范围内
	random() #随机生成实数属于[0,1);
	uniform(x,y) #随机生成实数属于[x,y];
	```
- 字符串运算<br>
	习惯了C中复杂的字符串操作，python的字符串操作简单到流泪啊～   
	通过+就可以连接，甚至还可以\*n(n为实数)来重复输出字符串;   
	用in和not in来判断字符串中是否含有某个字符；   
	在字符串前加r或R使其成为原始字符串（没有转义字符）。
- 格式化字符串<br>
	这部分非常类似C，不过字符串尾要加%，如
	```python
	print "My name is %s and weight is %d kg!" % ('Zara', 21) 
	```
- 列表List（序列）<br>
	有点像C中的数组，但其元素甚至不需要有相同的数据类型； <br>  
	+、\*、in等用法和字符串相同；它可以进行迭代，如：<br>
	```python
	for x in [2,5,7];
	print x;
	```
	结果为2，5，7。<br>
	列表的截取与输出类似，如对列表L，我们有：<br>
	```python
	L[2] #第3个元素
	L[-2] #倒数第2个元素
	L[1:] #从第2个元素到结尾
	```
	对列表，还有如下常用的方法：<br>
	```python
	list.append(obj) #在列表末尾添加新的元素
	list.count(obj) #统计某个元素在列表中出现的次数
	list.extend(seq) #在列表末尾一次性加入另一个序列
	list.index(obj) #从列表中找出某个值第一个匹配项的位置
	list.insert(index,obj) #将对象插入列表中index位置
	list.pop(index) #移除列表中的一个元素(缺省值为-1，即移除最后一个元素)，并且返回该元素的值
	list.remove(obj) #移除列表中某个值的第一个匹配项
	list.reverse() #反转列表
	list.sort(cmp,key,reverse) #缺省值为None、None、False
	```
# 2018-10-16
- 元组tuple<br>
	元组相当于不能修改的列表。定义列表用方括号，定义元组则用圆括号。虽说元组不能修改，但是元组可以连接起来；元组的元素不允许删除，我们可以用*del*语句删除整个元组。进阶，可以用切片的方式更新元组:
	```python
	>>> temp=(1, 2, 4, 5)    
	>>> temp=temp[:2]+(3,)+temp[2:]    
	>>> temp    
	(1, 2, 3, 4, 5)    
	```
- 字典Dictionary(Hash数组)<br>
	类似C++中的Map，元素为“键-值”对，键值对之间用“，”隔开，用花括号{}包住，就构成了字典。<br>
	键一般是唯一的，如果重复最后的一个键值对会替换前面的（前面的键值对会消失），如：
	```python
	>>>dict = {'a': 1, 'b': 2, 'b': '3'};
	>>> dict['b']
	'3'
	>>> dict
	{'a': 1, 'b': '3'}
	```
	值可以取任何数据类型，既可以是标准的对象，也可以是用户定义的；但键不行，键必须是不可变的，如字符串，数字或元组。<br>
	访问字典里的值，只需要在方括号内放入该值的键：
	```python
	dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}; 
	print "dict['Name']: ", dict['Name'];
	print "dict['Age']: ", dict['Age'];
	```
	输出为：
	```python
	dict['Name']:  Zara
	dict['Age']:  7
	```
	添加新的键值对到字典和修改已有的键值对均可采用直接赋值的方法：dict[key]=value<br>
	删除字典或其中的键值对，只需采用del语句即可：
	```python
	del dict['Name']; # 删除键是'Name'的条目
	dict.clear();     # 清空词典所有条目
	del dict ;        # 删除词典
	```
	与list和tuple一样，字典可以用*len(dict)*来获得字典大小（键的数量）；但字典没有*in*函数，要判断其中元素需要使用*dict.has_key(key)*方法。<br>
	字典里还有许多与上面很不同的方法：
	```python
	dict.fromkeys(seq, val)		#创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值
	dict.keys()		#以列表返回一个字典所有的键
	dict.values()		#以列表返回字典中的所有值
	dict.update(dict2)		#把字典dict2的键/值对更新（添加）到dict里
	pop(key[,default])		#删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。
	```
# 2018-10-17
- 函数<br>
	python的函数与C大同小异，以*def*开头，*return*结束；<br>
	函数内容以“：”开头，并且缩进；<br>
	函数可以同时返回多个值，但其实是返回一个tuple。
	函数参数可以设置缺省值，要注意必选参数在前，默认参数在后，否则Python的解释器会报错。<br>
	可以不按顺序提供部分默认参数。当不按顺序提供部分默认参数时，需要把参数名写上。<br>
	如调用*enroll('Adam', 'M', city='Tianjin')*<br>
- 匿名函数<br>
	使用关键字*lambda*来定义匿名函数：
	>f=lambda arg1,...,argn:expression(arg1,...,argn)   

- 类型<br>
	python中类型和C中大不相同：变量是没有类型的，只是充当一个“指针”的作用，而对象才有类型。<br>
	strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。<br>
	对于不可变类型，作为参数传入函数中对其本身并没有任何影响;比如在 fun(a)内部修改 a 的值，只是修改另一个复制的对象，不会影响 a 本身。<br>
	而可变类型传入函数中则类似C中的引用，是将对象真正的传入函数中，修改后函数外部的对象也会相应改变。<br>
- 切片<br>
	对L[a:b],取出从L[a]到L[b-1]的所有元素；若a为0，a还可以省略；若省略b即b=len(L)+1.<br>
	若要等间隔s取点，则可以写L[a:b:s];若要完全复制L还可以写L[:].<br>

