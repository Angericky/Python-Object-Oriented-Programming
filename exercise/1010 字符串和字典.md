

```python
str="hello,world"
str[5]
```




    ','




```python
len(str)
```




    11




```python
str[11]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-5e4046356d12> in <module>
    ----> 1 str[11]
    

    IndexError: string index out of range



```python
max(str)
```




    'w'




```python
print (str.upper())
```

    HELLO,WORLD
    


```python
print(str.lower())
```

    hello,world
    


```python
print(str.title())
```

    Hello,World
    


```python
str='hello,'
name = 'hqh'
print (str+name)
```

    hello,hqh
    


```python
str.join(name)
```




    'hhello,qhello,h'




```python
numbers = '12345'
print(' + '.join(numbers))
```

    1 + 2 + 3 + 4 + 5
    


```python
"hello, %s"%'world.'
```




    'hello, world.'




```python
"hello, %s"%'123.'
```




    'hello, 123.'




```python
x=3
print('{}={}*{}'.format(x*x,x,x))
print('{1}={0}*{0}'.format(x,x*x))
```

    9=3*3
    9=3*3
    


```python
print('my name is{name},my age is {age}'.format(name='yg', age =51)) # 告诉format赋值的参数是什么
name = 'yg'
age = 51
print (f'my name is {name}, my age is {age}')  #f 就像format 的调用格式
```

    my name isyg,my age is 51
    my name is yg, my age is 51
    


```python
"hello".center(9, '*')
```




    '**hello**'




```python
print ('*' *40)
print('hello world'.center(40))  # hello world 在中间，整个宽度为40
print ('*' *40)
```

    ****************************************
                  hello world               
    ****************************************
    


```python
print ('*' *40)
print('hello world'.center(38).center(40,'*'))
print ('*' *40)
```

    ****************************************
    *             hello world              *
    ****************************************
    


```python
file_path =  r'd:\PythonProjects\notebooks\strings.ipynb' #找文件的扩展名， 我这里的地址不准确，回去再改
index = file_path.find('.')
print (index)
file_path[index+1:]  

file_path.rfind('\\')
file_path[file_path.rfind('\\')+1: file_path.find('.')] # 输出文件名
```

    35
    




    'strings'




```python
answer = input ('do you like python?')
if answer.lower() == 'yes':
    print('great.')
```

    do you like python?yes
    great.
    


```python
'hello'.replace('h','H')   #替换函数
```




    'Hello'




```python
'Hello, #name#'.replace('#name#', 'yg')
```




    'Hello, yg'




```python
# 接下来讲字典
names = ['zhang','li', 'wu','fu']   
scores = [100,90,80,70]
name = input('please input a name')
print(scores[names.index(name)])  #跟名字对应的分数
```

    please input a namezhang
    100
    


```python
# 这才是字典
scores = {'zhang': 100, 'li':90, 'wu':80, 'fu':70} # 引号里面是索引项，具体的值是冒号后面的分数
name= input('please input a name')
print (scores[name])
```

    please input a namewu
    80
    


```python
# 创建字典
scores = {}
scores = dict()
scores ['zhang']=100
scores
```




    {'zhang': 100}




```python
'zhang' in scores
```




    True




```python
'lisi' in scores 
```




    False




```python
name = input('please input a name:')
if name in scores :
    print(scores[name])
else :
    print('name not found.')

```

    please input a name:si
    name not found.
    


```python
del scores['zhangsan']
scores 
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-32-d94592e1bd53> in <module>
    ----> 1 del scores['zhangsan']
          2 scores
    

    KeyError: 'zhangsan'



```python
del scores['zhang']
scores
```




    {}




```python
scores ['lisi']=90
scores['lisi']=80
```


```python
socres
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-35-5dbdb78c5a26> in <module>
    ----> 1 socres
    

    NameError: name 'socres' is not defined



```python
scores
```




    {'lisi': 80}




```python
scores ['zhang']=100
scores
```




    {'lisi': 80, 'zhang': 100}




```python
scores = {}.fromkeys(['zhangsan','lisi','wangwu','maliu'])
scores
```




    {'zhangsan': None, 'lisi': None, 'wangwu': None, 'maliu': None}




```python
str = 'hello, this is a test. i designed this test last night.'
count = dict.fromkeys('aeiou', 0)
for ch in str:
    if ch in 'aeiou':
        count[ch] +=1
print (count)
```

    {'a': 2, 'e': 5, 'i': 6, 'o': 1, 'u': 0}
    


```python
student = dict.fromkeys('name','scores')
student['name']=input('please input a name:')
student['score']=int(input('please input a score:'))
print ("{} 's score is{}".format(student['name'],student['score']))
```

    please input a name:han
    please input a score:100
    han 's score is100
    


```python
first_names = ['san','si','wu','jie','bing','ding']
last_names = ['s','so','wuo','jin','bai','di']
names =list()
for first_name in first_names:
    for last_name in last_names :
        names.append(first_name+' '+last_name)
print (names)

```

    ['san s', 'san so', 'san wuo', 'san jin', 'san bai', 'san di', 'si s', 'si so', 'si wuo', 'si jin', 'si bai', 'si di', 'wu s', 'wu so', 'wu wuo', 'wu jin', 'wu bai', 'wu di', 'jie s', 'jie so', 'jie wuo', 'jie jin', 'jie bai', 'jie di', 'bing s', 'bing so', 'bing wuo', 'bing jin', 'bing bai', 'bing di', 'ding s', 'ding so', 'ding wuo', 'ding jin', 'ding bai', 'ding di']
    


```python
len(names)
```




    36




```python
import random
random.choice(name)

```




    's'




```python
for i in range(0,100):
    score = random.randint(0,100)
    print(score, end=' ')

```

    87 78 12 5 68 6 60 30 23 54 4 36 8 5 96 95 61 67 26 70 23 99 28 87 21 63 10 7 100 98 3 82 73 10 95 91 28 61 51 97 3 28 1 100 68 11 61 46 71 87 83 45 70 83 67 20 7 78 77 67 20 77 4 59 44 42 87 73 78 28 58 33 36 21 23 34 14 67 42 48 9 2 37 61 32 75 81 24 26 1 15 20 39 38 38 9 56 78 83 10 


```python
import math
for i in range(0,100):
    score =math.ceil( random.gauss(75,20))
    print(score, end=' ')
```

    94 90 66 79 64 78 67 74 54 41 79 76 83 82 100 75 119 84 39 93 120 81 53 77 50 60 64 74 51 46 89 73 72 73 54 84 93 87 84 66 55 114 73 115 111 45 97 73 74 62 85 88 96 98 85 56 62 86 99 70 63 62 52 87 103 66 72 82 79 49 89 50 71 55 75 90 31 65 89 100 65 98 108 66 87 95 101 39 50 26 60 32 75 112 130 46 55 68 87 56 


```python
import math
for i in range(0,100):
    score =math.ceil( random.gauss(75,20))   # 限定随机产生的数据范围在75-20
    if score >100: score =100
    elif score <0: score =0
    print(score, end=' ')
```

    100 74 97 91 96 97 49 95 71 100 73 71 62 49 94 67 60 83 72 98 74 39 86 100 52 100 44 68 89 74 62 39 76 71 87 95 57 100 62 100 79 59 61 81 96 100 64 88 51 60 84 88 78 39 89 76 93 72 65 47 82 90 65 67 38 100 75 69 38 73 38 90 64 87 52 79 71 86 100 69 92 69 89 89 100 97 67 62 48 57 83 74 68 77 100 52 100 58 95 50 


```python
score_db = {}
score_template = {}.fromkeys(['phy','math','python'])
for name in names:
    scores = score_template.copy()
    
    score = math.ceil(random.gauss(75,20))
    if score>100: score=100
    elif score <0 : score =0
    scores['phy']= score
    
    score = math.ceil(random.gauss(75,20))
    if score>100: score=100
    elif score <0 : score =0
    scores['math']= score
    
    score = math.ceil(random.gauss(75,20))
    if score>100: score=100
    elif score <0 : score =0
    scores['python']= score
    
    score_db[name] = scores
    
print (score_db)
```

    {'san s': {'phy': 64, 'math': 86, 'python': 44}, 'san so': {'phy': 100, 'math': 48, 'python': 59}, 'san wuo': {'phy': 100, 'math': 64, 'python': 69}, 'san jin': {'phy': 83, 'math': 83, 'python': 79}, 'san bai': {'phy': 59, 'math': 54, 'python': 98}, 'san di': {'phy': 84, 'math': 51, 'python': 87}, 'si s': {'phy': 72, 'math': 67, 'python': 73}, 'si so': {'phy': 69, 'math': 84, 'python': 83}, 'si wuo': {'phy': 82, 'math': 99, 'python': 100}, 'si jin': {'phy': 70, 'math': 87, 'python': 66}, 'si bai': {'phy': 80, 'math': 58, 'python': 81}, 'si di': {'phy': 79, 'math': 79, 'python': 67}, 'wu s': {'phy': 75, 'math': 45, 'python': 92}, 'wu so': {'phy': 28, 'math': 66, 'python': 84}, 'wu wuo': {'phy': 60, 'math': 89, 'python': 74}, 'wu jin': {'phy': 100, 'math': 84, 'python': 66}, 'wu bai': {'phy': 100, 'math': 99, 'python': 75}, 'wu di': {'phy': 69, 'math': 56, 'python': 63}, 'jie s': {'phy': 84, 'math': 100, 'python': 89}, 'jie so': {'phy': 27, 'math': 57, 'python': 75}, 'jie wuo': {'phy': 72, 'math': 37, 'python': 78}, 'jie jin': {'phy': 62, 'math': 75, 'python': 57}, 'jie bai': {'phy': 100, 'math': 19, 'python': 49}, 'jie di': {'phy': 34, 'math': 52, 'python': 75}, 'bing s': {'phy': 92, 'math': 99, 'python': 46}, 'bing so': {'phy': 54, 'math': 87, 'python': 54}, 'bing wuo': {'phy': 100, 'math': 95, 'python': 89}, 'bing jin': {'phy': 67, 'math': 64, 'python': 82}, 'bing bai': {'phy': 39, 'math': 71, 'python': 86}, 'bing di': {'phy': 100, 'math': 60, 'python': 100}, 'ding s': {'phy': 28, 'math': 66, 'python': 72}, 'ding so': {'phy': 61, 'math': 80, 'python': 42}, 'ding wuo': {'phy': 74, 'math': 76, 'python': 99}, 'ding jin': {'phy': 52, 'math': 69, 'python': 89}, 'ding bai': {'phy': 95, 'math': 51, 'python': 80}, 'ding di': {'phy': 52, 'math': 100, 'python': 85}}
    


```python
def add(a,b):
    return a+b

print (add(3,4))
```

    7
    


```python
import math
def get_random_score():
    score = math.ceil(random.gauss(75,20))
    if score >100: score=100
    elif score <0: score =0
    return score
    
        
score_db = {}
score_template = {}.fromkeys(['phy','math','python'])
for name in names:
    scores = score_template.copy()
    scores['phy']=get_random_score()
    scores['math']=get_random_score()
    scores['python']=get_random_score()
    score_db[name] = scores
    
print (score_db)

```

    {'san s': {'phy': 88, 'math': 64, 'python': 84}, 'san so': {'phy': 71, 'math': 92, 'python': 66}, 'san wuo': {'phy': 100, 'math': 56, 'python': 65}, 'san jin': {'phy': 100, 'math': 70, 'python': 79}, 'san bai': {'phy': 72, 'math': 82, 'python': 64}, 'san di': {'phy': 86, 'math': 75, 'python': 37}, 'si s': {'phy': 65, 'math': 92, 'python': 74}, 'si so': {'phy': 84, 'math': 66, 'python': 66}, 'si wuo': {'phy': 80, 'math': 77, 'python': 100}, 'si jin': {'phy': 74, 'math': 75, 'python': 76}, 'si bai': {'phy': 66, 'math': 84, 'python': 81}, 'si di': {'phy': 85, 'math': 84, 'python': 80}, 'wu s': {'phy': 79, 'math': 39, 'python': 95}, 'wu so': {'phy': 47, 'math': 38, 'python': 31}, 'wu wuo': {'phy': 89, 'math': 85, 'python': 69}, 'wu jin': {'phy': 89, 'math': 100, 'python': 100}, 'wu bai': {'phy': 63, 'math': 86, 'python': 86}, 'wu di': {'phy': 51, 'math': 80, 'python': 73}, 'jie s': {'phy': 66, 'math': 89, 'python': 92}, 'jie so': {'phy': 40, 'math': 100, 'python': 47}, 'jie wuo': {'phy': 100, 'math': 54, 'python': 78}, 'jie jin': {'phy': 55, 'math': 70, 'python': 71}, 'jie bai': {'phy': 52, 'math': 67, 'python': 100}, 'jie di': {'phy': 72, 'math': 55, 'python': 82}, 'bing s': {'phy': 100, 'math': 66, 'python': 92}, 'bing so': {'phy': 50, 'math': 100, 'python': 87}, 'bing wuo': {'phy': 93, 'math': 100, 'python': 44}, 'bing jin': {'phy': 65, 'math': 91, 'python': 61}, 'bing bai': {'phy': 66, 'math': 100, 'python': 55}, 'bing di': {'phy': 47, 'math': 55, 'python': 13}, 'ding s': {'phy': 80, 'math': 52, 'python': 68}, 'ding so': {'phy': 75, 'math': 86, 'python': 38}, 'ding wuo': {'phy': 94, 'math': 86, 'python': 79}, 'ding jin': {'phy': 81, 'math': 94, 'python': 66}, 'ding bai': {'phy': 77, 'math': 60, 'python': 71}, 'ding di': {'phy': 100, 'math': 59, 'python': 64}}
    


```python
name = input ('please input a name')
if name in score_db:
    print('phy:', score_db[name]['phy'])
    print('math:', score_db[name]['math'])
    print('python:', score_db[name]['python'])
else :
    print ('no found.')
```

    please input a nameding bai
    phy: 77
    math: 60
    python: 71
    


```python
print ('name\t\tPhysics\tmath\tpython\ttotal\t')

for name in score_db.keys():
    print (name.center(12), end ='\t')
    print (score_db[name]['phy'], end='\t')
    print (score_db[name]['math'],end='\t')
    print (score_db[name]['python'],end='\t')
    print (score_db[name]['phy']+score_db[name]['math']+score_db[name]['python'], end='\t')
                          
```

    name		Physics	math	python	total	
       san s    	88	64	84	236	   san so   	71	92	66	229	  san wuo   	100	56	65	221	  san jin   	100	70	79	249	  san bai   	72	82	64	218	   san di   	86	75	37	198	    si s    	65	92	74	231	   si so    	84	66	66	216	   si wuo   	80	77	100	257	   si jin   	74	75	76	225	   si bai   	66	84	81	231	   si di    	85	84	80	249	    wu s    	79	39	95	213	   wu so    	47	38	31	116	   wu wuo   	89	85	69	243	   wu jin   	89	100	100	289	   wu bai   	63	86	86	235	   wu di    	51	80	73	204	   jie s    	66	89	92	247	   jie so   	40	100	47	187	  jie wuo   	100	54	78	232	  jie jin   	55	70	71	196	  jie bai   	52	67	100	219	   jie di   	72	55	82	209	   bing s   	100	66	92	258	  bing so   	50	100	87	237	  bing wuo  	93	100	44	237	  bing jin  	65	91	61	217	  bing bai  	66	100	55	221	  bing di   	47	55	13	115	   ding s   	80	52	68	200	  ding so   	75	86	38	199	  ding wuo  	94	86	79	259	  ding jin  	81	94	66	241	  ding bai  	77	60	71	208	  ding di   	100	59	64	223	


```python
# 字典转化为list 排序
def total(item):
    return item[1]['phy']+item[1]['math']+item[1]['python']
items = score_db.items()
sorted_scores=sorted(items, key=total)

for item in sorted_scores:
    print ('{:>15}'.format(item[0]), end ='\t')
    print (item[1]['phy'], end='\t')
    print (item[1]['math'],end='\t')
    print (item[1]['python'],end='\t')
    print (item[1]['phy']+item[1]['math']+item[1]['python'], end='\t')
```

            bing di	47	55	13	115	          wu so	47	38	31	116	         jie so	40	100	47	187	        jie jin	55	70	71	196	         san di	86	75	37	198	        ding so	75	86	38	199	         ding s	80	52	68	200	          wu di	51	80	73	204	       ding bai	77	60	71	208	         jie di	72	55	82	209	           wu s	79	39	95	213	          si so	84	66	66	216	       bing jin	65	91	61	217	        san bai	72	82	64	218	        jie bai	52	67	100	219	        san wuo	100	56	65	221	       bing bai	66	100	55	221	        ding di	100	59	64	223	         si jin	74	75	76	225	         san so	71	92	66	229	           si s	65	92	74	231	         si bai	66	84	81	231	        jie wuo	100	54	78	232	         wu bai	63	86	86	235	          san s	88	64	84	236	        bing so	50	100	87	237	       bing wuo	93	100	44	237	       ding jin	81	94	66	241	         wu wuo	89	85	69	243	          jie s	66	89	92	247	        san jin	100	70	79	249	          si di	85	84	80	249	         si wuo	80	77	100	257	         bing s	100	66	92	258	       ding wuo	94	86	79	259	         wu jin	89	100	100	289	


```python

```
