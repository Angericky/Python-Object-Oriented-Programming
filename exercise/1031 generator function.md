

```python
cache = dict()
def fib_cached(i):
    global cache
    if i in (0,1):
        return 1
    else:
        result = cache.get(i)
        if result is None:
            result = fib_cached(i-1)+fib_cached(i-2)
            cache[i]=result
        return result
```


```python
%timeit fib_cached(33)
```

    348 ns ± 8.43 ns per loop (mean ± std. dev. of 7 runs, 1000000 loops each)
    


```python
from functools import Iru_cache

@Iru_cache(maxsize=None)
def Fib(i):
    if i == 1 or i ==0:
        return 1
    else:
        return Fib(i-1)+Fib(i-2)
```


    ---------------------------------------------------------------------------

    ImportError                               Traceback (most recent call last)

    <ipython-input-7-8f96ae0a468d> in <module>
    ----> 1 from functools import Iru_cache
          2 
          3 @Iru_cache(maxsize=None)
          4 def Fib(i):
          5     if i == 1 or i ==0:
    

    ImportError: cannot import name 'Iru_cache' from 'functools' (C:\anaconda\lib\functools.py)



```python
def hanoi(n,source,target,temp):
    if n==1 :
        print('{}->{}'.format(source,target))
    else:
        hanoi(n-1,source,temp,target)
        print('{}->{}'.format(source,target))
        hanoi(n-1,temp,target,source)
        
hanoi(3,'A','C','B')
```

    A->C
    A->B
    C->B
    A->C
    B->A
    B->C
    A->C
    


```python
# 生成器
for i in range(0,10):
    print(i,end='')
    
print('***')
a = list(range(0,10))
for item in a:
    print(item,end='')
```

    0123456789***
    0123456789


```python
def fib(n):
    result = [0,1]
    second_last =0
    last =1
    for i in range(n-2):
        second_last,last=last,second_last+last
        result.append(last)
        
    return result
print (fib(50))
```

    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368, 75025, 121393, 196418, 317811, 514229, 832040, 1346269, 2178309, 3524578, 5702887, 9227465, 14930352, 24157817, 39088169, 63245986, 102334155, 165580141, 267914296, 433494437, 701408733, 1134903170, 1836311903, 2971215073, 4807526976, 7778742049]
    


```python
def fib_gen(n):

    second_last =0
    last =1
    yield 0
    yield 1
    for i in range(n-2):
        second_last,last=last,second_last+last
        yield last
        
for i in fib_gen(10):
    print(i,end=' ')
```

    0 1 1 2 3 5 8 13 21 34 


```python
nested = [[1,2],[3,4],[5,6]]
def flatten(nested):
    result= list()
    for sublist in nested:
        for item in sublist:
            result.append(item)
    return result

flatten_list =flatten(nested)
print (flatten_list)    
```

    [1, 2, 3, 4, 5, 6]
    


```python
# try, except
nested = [[1,2],[3,4],[5],6]
def flatten(nested):
    result= list()
    for sublist in nested:
        try:
        
            for item in sublist:
                result.append(item)
        except TypeError:
            result.append(sublist)
            
    return result

flatten_list =flatten(nested)
print (flatten_list) 
```

    [1, 2, 3, 4, 5, 6]
    


```python
# 生成器，yield, try, except
nested = [[1,2],[3,4],[5],6]
def flatten(nested):
   
    for sublist in nested:
        try:
        
            for item in sublist:
                yield item
        except TypeError:
            yield sublist
            
    

flatten_list =flatten(nested)
#print (flatten_list) 
for item in flatten_list:
    print(item,end=' ')
```

    1 2 3 4 5 6 


```python
# 生成器，yield, try, except,有字符串


def flatten(nested): 
    try:
        
        try: nested +''
        except TypeError: pass
        else : raise TypeError #如果是字符串的话
            
        for sublist in nested :
            try:
                for item in flatten(sublist):
                    yield item
            except TypeError:
                yield sublist
                
    except TypeError:
        yield nested
        
            
            
    
nested = ['hello',[1,[2,3,4]],[3,4],[5],6]
for item in flatten(nested):
    print(item,end=' ')
```

    hello 1 2 3 4 3 4 5 6 


```python
def func(x):
    return x.isalnum()

seq = ['hello','41','x41','?','***','####']
list(filter(func,seq))
```




    ['hello', '41', 'x41']




```python
list(filter(lambda x: x.isalnum(), seq)) # 不在其他地方用，就直接用lanmbda函数
```




    ['hello', '41', 'x41']




```python
[ x for x in seq if x.isalnum()] #更简单一点可以
```




    ['hello', '41', 'x41']




```python
import functools
list(map(str,range(10)))
```




    ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']




```python
[str(i) for i in range(10)]
```




    ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']




```python
from functools import reduce
numbers = [1,2,5,6,7,8, ]
reduce (lambda x,y : x+y,numbers)   # 用reduce函数求和
```




    29




```python
from time import sleep

def init_bar (bar, length=80):
    bar = list()
    for i in range(length):
        bar.append(' ')
    return bar

def clear_bar(bar):
    for i in range(len(bar)):
        bar [i] = ' '

def init_ants(bar_length = 80):
    ants = list()
    ants.append (('position':0, 'direction' : 1))
    ants.append(('position':bar_length-1,'direction':-1))
    return ants

def update_bar (bar,ants):
    # 未完待续
    
    
```
