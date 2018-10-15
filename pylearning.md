# 2018-10-15
- pass
	pass语句为占位符，为了防止程序报错：如若想定义一个函数，但是暂时还用不到，想之后再写，可以这样：
	```python
	def sample(n_samples):
    pass
    ```
    这样是为了防止定义了一个空函数导致的程序报错。
- 复数
	python中支持复数的运算，格式为a + bj或者complex(a,b);
- 随机数
	python中随机的使用可以说比C中简单许多：
	```python
	choice(Seq) #从序列Seq中随机挑选一个元素
	randrange(Start,Stop,Step) #Step缺省值为1，start包含在范围内，stop不包含在范围内
	random() #随机生成实数属于[0,1);
	uniform(x,y) #随机生成实数属于[x,y];
	```
- 字符串运算
	习惯了C中复杂的字符串操作，python的字符串操作简单到流泪啊～
	通过+就可以连接，甚至还可以$\ast$n(n为实数)来重复输出字符串；
	用in和not in来判断字符串中是否含有某个字符；
	在字符串前加r或R使其成为原始字符串（没有转义字符）。
- 格式化字符串
	这部分非常类似C，不过字符串尾要加%，如
	```python
	print "My name is %s and weight is %d kg!" % ('Zara', 21) 
	```
- 列表（序列）
	有点像C中的数组，但其元素甚至不需要有相同的数据类型；
	+、$\ast$、in等用法和字符串相同；它可以进行迭代，如：
	```python
	for x in [2,5,7];
	print x;
	```
	结果为2，5，7。
	列表的截取与输出类似，如对列表L，我们有：
	```python
	L[2] #第3个元素
	L[-2] #倒数第2个元素
	L[1:] #从第2个元素到结尾
	```
	对列表，还有如下常用的方法：
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