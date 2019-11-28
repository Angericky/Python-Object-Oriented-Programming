

```python
# 修饰器
@property
@height
```


```python
class Rectangle:
    def __init__(self):
        self.width=0
        self.height=0
        
        
    def __setattr__(self,name,value):
        if name = = 'size':
            if value[0] <0 or value[1]<0 : raise ValueError()
            self.width,self.height=value
            
        elif name = = 'width':
            if value < 0 : raise ValueError()
            self.width = value
            
        elif name = = 'height':
            if value < 0 : raise ValueError()
            self.height = value
            
        else :
            self.__dict__[name]=value
            
    def __getattr__(self,name):
        if name = = 'size':
            return self.width, self.height
        
        else :
            return self.__dict__[name]
        

rect= Rectangle()
rect.size= (3,4)
print(rect.size)
```


```python
# 尝试库的概念
import math

math.sin(0)
```




    0.0




```python
# 首先在anaconda文件夹下面创建了名为hellohui.py 格式的文件，然后import到这里，就可以直接输出库里面的内容
import hellohui
```

    hello world
    


```python
hellohui.path
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-7-149801c66aac> in <module>
    ----> 1 hellohui.path
    

    AttributeError: module 'hellohui' has no attribute 'path'



```python
from hellohui import hello
hello()
```

    hello world
    


```python
import hellohui
hello()
```

    hello world
    


```python
import copy
dir(copy)

```




    ['Error',
     '__all__',
     '__builtins__',
     '__cached__',
     '__doc__',
     '__file__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     '_copy_dispatch',
     '_copy_immutable',
     '_deepcopy_atomic',
     '_deepcopy_dict',
     '_deepcopy_dispatch',
     '_deepcopy_list',
     '_deepcopy_method',
     '_deepcopy_tuple',
     '_keep_alive',
     '_reconstruct',
     'copy',
     'deepcopy',
     'dispatch_table',
     'error']




```python
copy.__all__
```




    ['Error', 'copy', 'deepcopy']




```python
copy.__file__
```




    'C:\\Users\\asus\\Anaconda3\\lib\\copy.py'


