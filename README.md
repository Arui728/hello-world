# hello-world
Python 3.7.4 (tags/v3.7.4:e09359112e, Jul  8 2019, 20:13:57) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license()" for more information.
>>> def f(x):
	return x * x

>>> r = map(f,[1,2,3,4,5,6,7,8,9])
>>> list(r)
[1, 4, 9, 16, 25, 36, 49, 64, 81]
>>> L = []
>>> for n in [1,2,3,4,5,6,7,8,9]:
	L.append(f(n))
print(L)
SyntaxError: invalid syntax
>>> for n in [1,2,3,4,5,6,7,8,9]:
	L.append(f(n))
	print(L)

	
[1]
[1, 4]
[1, 4, 9]
[1, 4, 9, 16]
[1, 4, 9, 16, 25]
[1, 4, 9, 16, 25, 36]
[1, 4, 9, 16, 25, 36, 49]
[1, 4, 9, 16, 25, 36, 49, 64]
[1, 4, 9, 16, 25, 36, 49, 64, 81]
>>> list(map(str,[1,2,3,4,5,6,7,8,9]))
['1', '2', '3', '4', '5', '6', '7', '8', '9']
>>> from functools import reduce
>>> def add(x,y):
	return x+y

>>> reduce(add,[1,3,5,7,9])
25
>>> from functools import reduce
>>> def fn(x,y):
	return x * 10 + y

>>> reduce(fn,[1,3,5,7,9])
13579
>>> from functools import reduce
>>> def fn(x,y):
	return x*10+y

>>> def char2num(s):
	digits = {'0':0,'1':1,'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9}
	return digits[s]

>>> return (fn,map(char2num,'13579'))
SyntaxError: 'return' outside function
>>> reduce (fn,map(char2num,'13579'))
13579
>>> from functools import reduce
>>> DIGITS = {'0':0,'1':1,'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9}
>>> def str2int(s):
	def fn(x,y):
		return x*10+y
	def char2num(s):
		return DIGITS[s]
	return reduce(fn,map(char2num,s))

>>> def normalize(name):
	return name[:1].upper()+name[1:].lower()

>>> L1 = ['adam','LISA','barT']
>>> L2 = list(map(normalize,L1)]
SyntaxError: invalid syntax
>>> L2 = list(map(normalize,L1))
>>> print(L2)
['Adam', 'Lisa', 'Bart']
>>> def prod(L):
	return reduce(lambda x,y:x*y,L)

>>> print(prod([3,5,7,9]))
945
>>> DIGITS = {'0':0,'1':1,'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9}
>>> def str2float(s):
	def char2num(s):
		return DIGITS(s)
	return reduce(map(char2num,s))

>>> print(str2float(\'123.456\')
      
SyntaxError: unexpected character after line continuation character
>>> print(str2float('123.456'))
Traceback (most recent call last):
  File "<pyshell#61>", line 1, in <module>
    print(str2float('123.456'))
  File "<pyshell#57>", line 4, in str2float
    return reduce(map(char2num,s))
TypeError: reduce expected at least 2 arguments, got 1
>>> def str2float(s):
	def char2num(c):
		DIGITS = {'0':0,'1':1,'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9}
		return DIGITS(c)
	s_split = s.split('.')
	pro_num = reduce(lambda x,y:x*10+y,map(char2num,s_split[0]))
	sub_num = reduce((lambda x,y:x*0.1+y)*0.1,map(char2num,s_split[1][::-1]))
	return pro_num+sub_num

>>> 
