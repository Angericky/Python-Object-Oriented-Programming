
直接赋值,默认浅拷贝传递对象的引用而已,原始列表改变，被赋值的b也会做相同的改变

```python
a=list(range(1,4))
b=a
print('a:',a)
print('b:',b)

```

    a: [1, 2, 3]
    b: <built-in method copy of list object at 0x0000020910648908>
    
浅拷贝copy：
对象本身被拷贝了，但没有拷贝子对象，共用同一个可变list对象

```python
a=list(range(1,4))
b=a.copy()
a.append(4)     # append改变的不是子对象，对象本身被拷贝了

print('a:',a)
print('b:',b)
```

    a: [1, 2, 3, 4]
    b: [1, 2, 3]
    


```python
a=[1,2,3,[4,5]]
a[3][0]
```



```python
b=a.copy()
print('a:',a)
print('b:',b)
a[3][0]=4.1
print('a:',a)
print('b:',b)
a[0]=0
print('a:',a)
print('b:',b)
```

    a: [1, 2, 3, [4, 5]]
    b: [1, 2, 3, [4, 5]]
    a: [1, 2, 3, [4.1, 5]]
    b: [1, 2, 3, [4.1, 5]]
    a: [0, 2, 3, [4.1, 5]]
    b: [1, 2, 3, [4.1, 5]]
    

深拷贝deepcopy：包含对象里面的自对象的拷贝，所以原始对象的改变不会造成深拷贝里任何子元素的改变

```python
'''
虽然b是copy a 列表，但是由于a潜逃了一个新的list，所以b 拷贝a时，也拷贝了新的list。
所以，当a当中新的list值变了时，b里面的也会变。
如果不想b随着a变化，那就引用deepcopy，如下'''

import copy
a=[1,2,3,[4,5]]
b=copy.deepcopy(a)
print('a:',a)
print('b:',b)

```

    a: [1, 2, 3, [4, 5]]
    b: [1, 2, 3, [4, 5]]
    


```python
a[3][0]=5.8
print('a:',a)
print('b:',b)
```

    a: [1, 2, 3, [5.8, 5]]
    b: [1, 2, 3, [4, 5]]
    

元素计数

```python
a=[3,5,7,8,4,5,]
a.count(3)
```

    1


index()找某个数据在list中的索引

```python
len(a)
a.index(3)
```

    0


index(elem, position)从某个位置开始找某个数据在list中的索引

```python
a.index(3,1)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-10-b658ca1e0861> in <module>
    ----> 1 a.index(3,1)
    

    ValueError: 3 is not in list



```python
a.index(5,1) #从第一个位置索引5
```

    1



insert(elem, position)在某个位置插入元素

```python
a.insert(2,'*')
print(a)
```

    [3, 5, '*', 7, 8, 4, 5]
    


```python
a.index(5,0)
```

    1


remove(elem)删除第一次出现的某个元素
不在list里会报错 ValueError: list.remove(x): x not in list

```python
a.remove(3) #只能删掉一个值
print(a)
```

    [5, '*', 7, 8, 4, 5]
    

append(elem)追加一个元素

```python
a=[1,2,3]
a.append(4) #可以加一个元素
a
```


    [1, 2, 3, 4]



pop()删除最后一个元素

```python
a.pop() #删一个元素
a
```




    [1, 2, 3]




```python
# 假象输入一个表达式，（3*（4+5）），用stack来检查
expression = input('qingshuru')
my_stack=list()
left_quotes=['{','[','(']
right_quotes=['}',']',')']

for ch in expression:
    if ch in left_quotes:
        my_stack.append(ch)
    elif ch in right_quotes:
        if my_stack == []:
            print('not match')
        else:
            left_ch = my_stack.pop()
            if (left_quotes.index(left_ch)!=right_quotes.index(ch)):
                print('not match')
                break
        
if my_stack != []:
    print ('not match')
else:
    print('match')
         
```
    qingshuru 3*(4+5)
    match


```python
expression = input('qingshuru')
my_stack=list()
left_quotes=['{','[','(']
right_quotes=['}',']',')']

for ch in expression:
    if ch in left_quotes:
        my_stack.append(ch)
    elif ch in right_quotes:
        if my_stack==[]:
            print('not match')
        else:
            left_ch = my_stack.pop()
            if (left_quotes.index(left_ch)!=right_quotes.index(ch)):
                print('not match')
                break
        
if my_stack!=[]:
    print ('not match')
else:
    print('match')
```

    qingshuru3(4)
    match
    


```python
a=[1,2,3]
b=[4,5,6]
print(a+b)

```

    [1, 2, 3, 4, 5, 6]
    


```python
a=a+b
print(a)
```

    [1, 2, 3, 4, 5, 6]
    


```python
a+=b
print(a)
```

    [1, 2, 3, 4, 5, 6, 4, 5, 6]
    


```python
a='hello'
b='world'
print(a+b)
```

    helloworld
    


```python
a+=b
print(a)
```

    helloworld
    


```python
a=[1,2,3]
a.append([4,5,6])
a
```




    [1, 2, 3, [4, 5, 6]]


extend(list) 扩展list

```python
a=[1,2,3]
a.extend([4,5,6])
a
```




    [1, 2, 3, 4, 5, 6]



reverse() 翻转列表本身，并重新赋值原列表

```python
a= list(range(0,6))
print(a)
a.reverse()
print('a after reverse():', a)
```

    [0, 1, 2, 3, 4, 5]
    a after reverse(): [5, 4, 3, 2, 1, 0]
    


```python
b=a.reverse() # 解释不清楚，会出现歧义
print(b)

```

    None
    


```python
a=[1,2,3,4,5]
b=a.copy()
b.reverse()
print(b)
```

    [5, 4, 3, 2, 1]
    


```python
import random
for i in range(0,20):
    value = random.randint(1,6)
    print(value,end=' ')

```

    6 6 2 1 2 6 2 2 5 5 2 3 4 6 1 1 2 1 5 3 


```python
import random
a= list()
for i in range(0,20):
    #value = random.randint(1,6)
    a.append(random.randint(1,6))
    
print(a)
```

    [1, 4, 5, 3, 3, 4, 4, 5, 5, 1, 6, 1, 1, 1, 6, 2, 1, 5, 4, 6]
    

sort() 对列表本身排序，并重新赋值原列表

```python
a.sort()
print(a)
```

    [1, 1, 1, 1, 1, 1, 2, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6]
    

sorted(list) 对列表排序，赋给另一个变量

```python
b=sorted(a)
b
```




    [1, 1, 1, 1, 1, 1, 2, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6]




```python
a
```




    [1, 1, 1, 1, 1, 1, 2, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6]




```python
import random
a= [None]*20
for i in range(0,20):
    #value = random.randint(1,6)
    a[i]=(random.randint(1,6))
    
print(a)
```

    [5, 3, 3, 3, 1, 4, 3, 5, 3, 6, 5, 6, 5, 2, 4, 4, 2, 4, 1, 4]
    

%%timeit能够计算for-loop的单次用时

```python
%%timeit  #计算用时
a=[None]*100
for i in range(0,100):
    a[i]=i
```

    7.57 µs ± 366 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
    

sum(list) 对列表求和
max(list) 寻找最大值
min(list) 寻找最小值

```python
import random
a= [None]*20
for i in range(0,20):
    #value = random.randint(1,6)
    a[i]=(random.randint(1,6))
print ('mean:', sum(a)/len(a))
print('max:', max(a))
```

    mean: 3.2
    max: 5
    


```python
# month = int (input('please input the month:'))
# day = int(input('please input the day:'))

# count = day
# if month>1:
   #  count += 31
# if month >2:
 #   count +=28

month = int (input('please input the month:'))
day = int(input('please input the day:'))

days_in_month = [31,28,31,30,31,30,31,31,30,31,30,31]

count = day
i=1
while i < month:
     count += days_in_month[i-1]
     i +=1
    
print ('this is the {}the day in the year.'.format(count))


```

    please input the month:3
    please input the day:5
    this is the 64the day in the year.
    


```python
while True:
    score = int(input ('please input a score:'))
    if 100>=score>=90:
        grade = 'A'
    elif 90 >= score>=75:
        grade = 'B'
    elif 75 >= score>=60:
        grade = 'C'
    elif 60 >= score>=0:
        grade = 'D'
    else :
        print('invalid')
        break
    print('grade:', grade)

```

    please input a score:96
    grade: A
    please input a score:67
    grade: C
    please input a score:HELLO
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-56-d173ef7b21d2> in <module>
          1 while True:
    ----> 2     score = int(input ('please input a score:'))
          3     if 100>=score>=90:
          4         grade = 'A'
          5     elif 90 >= score>=75:
    

    ValueError: invalid literal for int() with base 10: 'HELLO'



```python
grades = ['D']*60+['C']*15+['B']*15+['A']*15
while True:
    print('grades:',grades[int(input('please input a score:'))])
    break

```

    Please input a score: 80
    grade:  B


```python
import random
count = [0]*6
for i in range (0,60000):
    value = random.randint(1,6)
    count[value-1]+=1
    
print (count)
print ((max(count)-min(count))*6/sum(count))
```

    [99825, 99896, 99545, 100697, 99989, 100048]
    0.01152


```python
a=[1,2,3,4]
print(a)
```


```python
import random
count = 0
last_three=[3,3,3]
for i in range (0,60000):
    last_three.append(random.randint(1,6))
    last_three.pop(0)
    if(last_three ==[6,6,6]):
        count +=1

print (count, count/60000)    

```
    265 0.004416666666666667



```python
break
```


```python
a=[1,2,3,4]
print(a)
```
    [1, 2, 3, 4]

```python
a[0]
```
    [1]