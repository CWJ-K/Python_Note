class.__dict__
func.__name__

.module
module

can not import module
# PATH
https://carsonwah.github.io/15213187969322.html

# Dynamic Imports
why needs
https://www.initialyze.com/blog/2020/11/what-are-dynamic-imports-and-how-to-use-them/
## getattr
    return the attribute of objects
    class Test:
        def __init__(self):
            self.name = 'test'
    
    t = Test()
    getattr(t, 'name') # print test

    getattr(t, 'name2') 
    # raise AttributeError: 'Test' object has no attribute 'name2'

    getattr(t, 'name2', 'hi')  # assign a nonexist attribute to t and give a default value, hi

## Package: importlib
* provides the implementation of the import statement in Python source code
* provides an implementation which is easier to comprehend than one implemented in a programming language other than Python


# init



# * 
    * (single asterisk) and ** (double asterisks)
* *args
  attach a variable-length number of arguments
  
* **kwargs
  * pass a keyworded variable length of arguments to a function
        func(**{'type':'Event'}) = func(type='Event')
  * unpack the dict elements 
        **{'type':'Event'} = type='Event'

* **_
  * _ is just a variable like any other, but by convention it means that you don't intend to use that value, just declare and forget it.
  * e.g.
        # before **_ is key-value arguments, so ** is used
        def _fetch_ratings(templates_dict, batch_size=1000, **_)

# underline

https://medium.com/python-language/python-tricks-%E5%BA%95%E7%B7%9A%E5%AE%B6%E6%97%8F%E7%9A%84%E7%A7%98%E5%AF%86-d84a2ce9cde6


# yield
https://zh-blog.logan.tw/2019/03/30/python3-intro-to-yield-from-expr/




# wrapper
[@apply_defaults](https://airflow.apache.org/docs/apache-airflow/stable/_modules/airflow/models/baseoperator.html#BaseOperator)
  @functools.wraps(func)



# [inheritance from class](https://stackoverflow.com/a/27134600)
```python
class ChildA(Base):
    def __init__(self):
        Base.__init__(self)
        
class ChildB(Base):
    def __init__(self):
        super(ChildB, self).__init__()
```
* super().__init__() = super(ChildB, self).__init__()
  > Python2, inheritance is required like `super(ChildB, self).__init__()`

* Base.__init__(self) is not recommended
  >  can not use multiple inheritance since the next parent's call is hard coded


