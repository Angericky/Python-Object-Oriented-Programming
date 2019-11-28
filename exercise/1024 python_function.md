

```python
names= ['a','b','c','d']
a = list(enumerate(names))
a
```




    [(0, 'a'), (1, 'b'), (2, 'c'), (3, 'd')]




```python
a=list(range(0,10))
b=list()
for item in a:
    b.append(item*item)   # 在b后面追加元素
    
print(a)
print(b)
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
    


```python
b=[item*item for item in range(0,10)]  #只需要执行一次语句
b
```




    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]




```python
b=[item for item in range(0,100)if item % 3== 0]   #这个表达的语法很强，一句话可以干这么多事情
print(b)
```

    [0, 3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69, 72, 75, 78, 81, 84, 87, 90, 93, 96, 99]
    


```python
# 传统的方法上
coordinate = []           
for x in range (0,10):
    for y in range(0,10):
        coordinate.append((x,y))
print(coordinate)
    
```

    [(0, 0), (0, 1), (0, 2), (0, 3), (0, 4), (0, 5), (0, 6), (0, 7), (0, 8), (0, 9), (1, 0), (1, 1), (1, 2), (1, 3), (1, 4), (1, 5), (1, 6), (1, 7), (1, 8), (1, 9), (2, 0), (2, 1), (2, 2), (2, 3), (2, 4), (2, 5), (2, 6), (2, 7), (2, 8), (2, 9), (3, 0), (3, 1), (3, 2), (3, 3), (3, 4), (3, 5), (3, 6), (3, 7), (3, 8), (3, 9), (4, 0), (4, 1), (4, 2), (4, 3), (4, 4), (4, 5), (4, 6), (4, 7), (4, 8), (4, 9), (5, 0), (5, 1), (5, 2), (5, 3), (5, 4), (5, 5), (5, 6), (5, 7), (5, 8), (5, 9), (6, 0), (6, 1), (6, 2), (6, 3), (6, 4), (6, 5), (6, 6), (6, 7), (6, 8), (6, 9), (7, 0), (7, 1), (7, 2), (7, 3), (7, 4), (7, 5), (7, 6), (7, 7), (7, 8), (7, 9), (8, 0), (8, 1), (8, 2), (8, 3), (8, 4), (8, 5), (8, 6), (8, 7), (8, 8), (8, 9), (9, 0), (9, 1), (9, 2), (9, 3), (9, 4), (9, 5), (9, 6), (9, 7), (9, 8), (9, 9)]
    


```python
# python 上可以改为
coordinate =[(x,y) for x in range(0,10)for y in range(0,10)]
print (coordinate)
```

    [(0, 0), (0, 1), (0, 2), (0, 3), (0, 4), (0, 5), (0, 6), (0, 7), (0, 8), (0, 9), (1, 0), (1, 1), (1, 2), (1, 3), (1, 4), (1, 5), (1, 6), (1, 7), (1, 8), (1, 9), (2, 0), (2, 1), (2, 2), (2, 3), (2, 4), (2, 5), (2, 6), (2, 7), (2, 8), (2, 9), (3, 0), (3, 1), (3, 2), (3, 3), (3, 4), (3, 5), (3, 6), (3, 7), (3, 8), (3, 9), (4, 0), (4, 1), (4, 2), (4, 3), (4, 4), (4, 5), (4, 6), (4, 7), (4, 8), (4, 9), (5, 0), (5, 1), (5, 2), (5, 3), (5, 4), (5, 5), (5, 6), (5, 7), (5, 8), (5, 9), (6, 0), (6, 1), (6, 2), (6, 3), (6, 4), (6, 5), (6, 6), (6, 7), (6, 8), (6, 9), (7, 0), (7, 1), (7, 2), (7, 3), (7, 4), (7, 5), (7, 6), (7, 7), (7, 8), (7, 9), (8, 0), (8, 1), (8, 2), (8, 3), (8, 4), (8, 5), (8, 6), (8, 7), (8, 8), (8, 9), (9, 0), (9, 1), (9, 2), (9, 3), (9, 4), (9, 5), (9, 6), (9, 7), (9, 8), (9, 9)]
    


```python
girls = ['alice','berniec','claire']
boys = ['chris','aohn','bob']
result = [boy + '+' + girl for boy in boys for girl in girls if boy[0]== girl[0]]
print (result)
```

    ['chris+claire', 'aohn+alice', 'bob+berniec']
    


```python
squares = {i:i** 2 for i in range(0,10)}   # i**2 是指i的平方     这里的创建的是字典
print (squares) 
```

    {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64, 9: 81}
    


```python
squares[5]     # 查询字典
```




    25




```python
a= [1,2,3]
b=a
a= None
b

```




    [1, 2, 3]




```python
b = None

```


```python
x= 1
del x
x
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-14-c5db7de16c09> in <module>
          1 x= 1
          2 del x
    ----> 3 x
    

    NameError: name 'x' is not defined



```python
a=[1,3,4]
b=a
del a     # python 的 del 不是释放内存
b
```




    [1, 3, 4]




```python
exec ('print (" hell0, world")')
```

     hell0, world
    


```python
scope = {}
exec ('y=1', scope)    #  把y的值存在变量的作用域下面，scope字典下面
y
scope['y']
```




    1




```python
%whos
```

    Variable     Type    Data/Info
    ------------------------------
    b            list    n=3
    boys         list    n=3
    coordinate   list    n=100
    girls        list    n=3
    item         int     9
    names        list    n=4
    result       list    n=3
    scope        dict    n=2
    squares      dict    n=10
    y            int     9
    


```python
print(scope)
```

    {'__builtins__': {'__name__': 'builtins', '__doc__': "Built-in functions, exceptions, and other objects.\n\nNoteworthy: None is the `nil' object; Ellipsis represents `...' in slices.", '__package__': '', '__loader__': <class '_frozen_importlib.BuiltinImporter'>, '__spec__': ModuleSpec(name='builtins', loader=<class '_frozen_importlib.BuiltinImporter'>), '__build_class__': <built-in function __build_class__>, '__import__': <built-in function __import__>, 'abs': <built-in function abs>, 'all': <built-in function all>, 'any': <built-in function any>, 'ascii': <built-in function ascii>, 'bin': <built-in function bin>, 'breakpoint': <built-in function breakpoint>, 'callable': <built-in function callable>, 'chr': <built-in function chr>, 'compile': <built-in function compile>, 'delattr': <built-in function delattr>, 'dir': <built-in function dir>, 'divmod': <built-in function divmod>, 'eval': <built-in function eval>, 'exec': <built-in function exec>, 'format': <built-in function format>, 'getattr': <built-in function getattr>, 'globals': <built-in function globals>, 'hasattr': <built-in function hasattr>, 'hash': <built-in function hash>, 'hex': <built-in function hex>, 'id': <built-in function id>, 'input': <bound method Kernel.raw_input of <ipykernel.ipkernel.IPythonKernel object at 0x00000211D915AC88>>, 'isinstance': <built-in function isinstance>, 'issubclass': <built-in function issubclass>, 'iter': <built-in function iter>, 'len': <built-in function len>, 'locals': <built-in function locals>, 'max': <built-in function max>, 'min': <built-in function min>, 'next': <built-in function next>, 'oct': <built-in function oct>, 'ord': <built-in function ord>, 'pow': <built-in function pow>, 'print': <built-in function print>, 'repr': <built-in function repr>, 'round': <built-in function round>, 'setattr': <built-in function setattr>, 'sorted': <built-in function sorted>, 'sum': <built-in function sum>, 'vars': <built-in function vars>, 'None': None, 'Ellipsis': Ellipsis, 'NotImplemented': NotImplemented, 'False': False, 'True': True, 'bool': <class 'bool'>, 'memoryview': <class 'memoryview'>, 'bytearray': <class 'bytearray'>, 'bytes': <class 'bytes'>, 'classmethod': <class 'classmethod'>, 'complex': <class 'complex'>, 'dict': <class 'dict'>, 'enumerate': <class 'enumerate'>, 'filter': <class 'filter'>, 'float': <class 'float'>, 'frozenset': <class 'frozenset'>, 'property': <class 'property'>, 'int': <class 'int'>, 'list': <class 'list'>, 'map': <class 'map'>, 'object': <class 'object'>, 'range': <class 'range'>, 'reversed': <class 'reversed'>, 'set': <class 'set'>, 'slice': <class 'slice'>, 'staticmethod': <class 'staticmethod'>, 'str': <class 'str'>, 'super': <class 'super'>, 'tuple': <class 'tuple'>, 'type': <class 'type'>, 'zip': <class 'zip'>, '__debug__': True, 'BaseException': <class 'BaseException'>, 'Exception': <class 'Exception'>, 'TypeError': <class 'TypeError'>, 'StopAsyncIteration': <class 'StopAsyncIteration'>, 'StopIteration': <class 'StopIteration'>, 'GeneratorExit': <class 'GeneratorExit'>, 'SystemExit': <class 'SystemExit'>, 'KeyboardInterrupt': <class 'KeyboardInterrupt'>, 'ImportError': <class 'ImportError'>, 'ModuleNotFoundError': <class 'ModuleNotFoundError'>, 'OSError': <class 'OSError'>, 'EnvironmentError': <class 'OSError'>, 'IOError': <class 'OSError'>, 'WindowsError': <class 'OSError'>, 'EOFError': <class 'EOFError'>, 'RuntimeError': <class 'RuntimeError'>, 'RecursionError': <class 'RecursionError'>, 'NotImplementedError': <class 'NotImplementedError'>, 'NameError': <class 'NameError'>, 'UnboundLocalError': <class 'UnboundLocalError'>, 'AttributeError': <class 'AttributeError'>, 'SyntaxError': <class 'SyntaxError'>, 'IndentationError': <class 'IndentationError'>, 'TabError': <class 'TabError'>, 'LookupError': <class 'LookupError'>, 'IndexError': <class 'IndexError'>, 'KeyError': <class 'KeyError'>, 'ValueError': <class 'ValueError'>, 'UnicodeError': <class 'UnicodeError'>, 'UnicodeEncodeError': <class 'UnicodeEncodeError'>, 'UnicodeDecodeError': <class 'UnicodeDecodeError'>, 'UnicodeTranslateError': <class 'UnicodeTranslateError'>, 'AssertionError': <class 'AssertionError'>, 'ArithmeticError': <class 'ArithmeticError'>, 'FloatingPointError': <class 'FloatingPointError'>, 'OverflowError': <class 'OverflowError'>, 'ZeroDivisionError': <class 'ZeroDivisionError'>, 'SystemError': <class 'SystemError'>, 'ReferenceError': <class 'ReferenceError'>, 'MemoryError': <class 'MemoryError'>, 'BufferError': <class 'BufferError'>, 'Warning': <class 'Warning'>, 'UserWarning': <class 'UserWarning'>, 'DeprecationWarning': <class 'DeprecationWarning'>, 'PendingDeprecationWarning': <class 'PendingDeprecationWarning'>, 'SyntaxWarning': <class 'SyntaxWarning'>, 'RuntimeWarning': <class 'RuntimeWarning'>, 'FutureWarning': <class 'FutureWarning'>, 'ImportWarning': <class 'ImportWarning'>, 'UnicodeWarning': <class 'UnicodeWarning'>, 'BytesWarning': <class 'BytesWarning'>, 'ResourceWarning': <class 'ResourceWarning'>, 'ConnectionError': <class 'ConnectionError'>, 'BlockingIOError': <class 'BlockingIOError'>, 'BrokenPipeError': <class 'BrokenPipeError'>, 'ChildProcessError': <class 'ChildProcessError'>, 'ConnectionAbortedError': <class 'ConnectionAbortedError'>, 'ConnectionRefusedError': <class 'ConnectionRefusedError'>, 'ConnectionResetError': <class 'ConnectionResetError'>, 'FileExistsError': <class 'FileExistsError'>, 'FileNotFoundError': <class 'FileNotFoundError'>, 'IsADirectoryError': <class 'IsADirectoryError'>, 'NotADirectoryError': <class 'NotADirectoryError'>, 'InterruptedError': <class 'InterruptedError'>, 'PermissionError': <class 'PermissionError'>, 'ProcessLookupError': <class 'ProcessLookupError'>, 'TimeoutError': <class 'TimeoutError'>, 'open': <built-in function open>, 'copyright': Copyright (c) 2001-2019 Python Software Foundation.
    All Rights Reserved.
    
    Copyright (c) 2000 BeOpen.com.
    All Rights Reserved.
    
    Copyright (c) 1995-2001 Corporation for National Research Initiatives.
    All Rights Reserved.
    
    Copyright (c) 1991-1995 Stichting Mathematisch Centrum, Amsterdam.
    All Rights Reserved., 'credits':     Thanks to CWI, CNRI, BeOpen.com, Zope Corporation and a cast of thousands
        for supporting Python development.  See www.python.org for more information., 'license': Type license() to see the full license text, 'help': Type help() for interactive help, or help(object) for help about object., '__IPYTHON__': True, 'display': <function display at 0x00000211D758CB70>, 'get_ipython': <bound method InteractiveShell.get_ipython of <ipykernel.zmqshell.ZMQInteractiveShell object at 0x00000211D915ADA0>>}, 'y': 1}
    


```python
vars()
eval('1+2+3')
```




    6




```python
expr = input ('please input an expression: ')
print (eval(expr))      # 必须是用表达式表达
```

    please input an expression: hannah
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-22-20c60cd8241b> in <module>
          1 expr = input ('please input an expression: ')
    ----> 2 print (eval(expr))
    

    <string> in <module>
    

    NameError: name 'hannah' is not defined



```python
def hello (name):     #定义函数
    'say hello to somebody whose name is defined by name.'
    print ('hello,' + name + '!')
```


```python
hello?
```


```python
hello('yg')
```

    hello,yg!
    


```python
callable(hello)
```




    True




```python
print(hello('yg'))    #H函数没有返回值
```

    hello,yg!
    None
    


```python
def print_banner(text,width):   
    symbol = '#'
    print(symbol * width)
    print (text.center(width-2).center(width, symbol))
    print(symbol* width)
print_banner('hello', 30)
```

    ##############################
    #           hello            #
    ##############################
    


```python
fibs = [1,1]
for i in range (0,9):
    fibs.append(fibs[-2]+fibs[-1])
print (fibs)
```

    [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
    


```python
print (fibs[5])
```

    8
    


```python
def fibs(num):
    result =[1,1]
    for i in range (num - 2):
        result.append(result[-2]+result[-1])
    return result

num = int(input('how many fibonacci numbers do you want?'))
print (fibs(num))
```

    how many fibonacci numbers do you want?9
    [1, 1, 2, 3, 5, 8, 13, 21, 34]
    


```python
def fib(index):
    result =[1,1]
    for i in range (index - 2):
        result.append(result[-2]+result[-1])
    return result[-1]

num = int(input('how many steps?'))
print ('total number of different ways: {}'.format(fib(num)))
```

    how many steps?6
    total number of different ways: 8
    


```python
def fib(index):
    item_before_last, last_item = 1,1
    item
    for i in range (index - 2):
        item_before_last,last_item= last_item,item_before_last +last_item
    return last_item

num = int(input('how many steps?'))
print ('total number of different ways: {}'.format(fib(num +1)))
```

    how many steps?6
    total number of different ways: 13
    


```python
setup_ants_positions()
while not is_bar_empty():
    update_bar()
    show_bar()
    wait()
    update_ants_positions()

```


```python
def change_it(a):   
    a=a*2
    
x =2
change_it(x)   #这种方式是改变不了x的值的
print(x)
```

    2
    


```python
def change_it(a):   
    a[0]= 'Hello'
    
x =['hello','hi']
change_it(x)   #这里改变的是x所指向的值，所以，x会变
print(x)
```

    ['Hello', 'hi']
    


```python
def change_it(a):   
    a= ['Hello', 'hi']
   # a[0]= 'Hello'
    
x =['hello','hi']
change_it(x)   #这里噶变的是a，不是x
print(x)
```

    ['hello', 'hi']
    


```python
def hello(greeting, name):
    print ('{},{}'.format(greeting, name))
    
hello ('hi','world')
hello ('world','hi')
```

    hi,world
    world,hi
    


```python
hello (greeting = 'hi',name='wolrd')
```

    hi,wolrd
    


```python
def hello(greeting='hello', name='world'):   # 赋缺省值
    print ('{},{}'.format(greeting, name))
    
hello()
hello('hi')
hello("hi,yg")
hello(name='yg')
```

    hello,world
    hi,world
    hi,yg,world
    hello,yg
    


```python
def interval(start, end=None, step=1):
    if end is None:
        start ,end =0,start
    result = []
    i = start
    while i < end:
        result.append(i)
        i += step
    return result

print (interval(8))
print (interval(2,8))
print (interval(2,8,2))
```

    [0, 1, 2, 3, 4, 5, 6, 7]
    [2, 3, 4, 5, 6, 7]
    [2, 4, 6]
    


```python
def sum(*params):
    result =0
    for item in params:
        result += item
    return result
assert (sum(1,2,3,4)==10)
print('test ok')
```

    test ok
    


```python
def print_sum(*params,label='sum'):
    result =0
    for item in params:
        result += item
  
    print(label, result)

print_sum(1,2,3,4,label='和')
```

    和 10
    


```python

```


```python
def multiplier (factor):
    def multiplierByFactor(number):
        return number * factor
    return multiplierByFactor

double = multiplier(2)
print(double(5))

triple = multiplier(3)
print(triple(6))

multiplier(3)(6)
```

    10
    18
    




    18


