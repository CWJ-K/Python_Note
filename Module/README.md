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