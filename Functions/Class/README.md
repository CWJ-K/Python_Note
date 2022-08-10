<!-- omit in toc -->
# Introduction

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [Terminal](#terminal)
  - [1. Inheritance](#1-inheritance)
    - [1.1. instance method](#11-instance-method)
    - [1.2. Class method](#12-class-method)
    - [1.3. Static method](#13-static-method)
    - [1.4. Class Inheritance](#14-class-inheritance)
- [Multiple Inheritance](#multiple-inheritance)
- [Packages](#packages)
- [Commands](#commands)
  - [Magic Methods](#magic-methods)
    - [Object Representations: `__repr__`, `__str__`](#object-representations-__repr__-__str__)
    - [Comparison Methods: `__eq__`, `__gt__`, `__it__`](#comparison-methods-__eq__-__gt__-__it__)
    - [Callable Object: `__call__` (TODO)](#callable-object-__call__-todo)

<br />

# Fundamental Concepts
## Terminal
* function > class > method


## 1. Inheritance

### 1.1. instance method
* argument = self

```python
class Student:
  def __init__(self):
    ...
  
  def average(self):
    ...
```

<br />

### 1.2. Class method
* if using two classes, functions will not cover the original classes 

```python
class Foo:
    @classmethod
    def hi(cls):
      ...
```

<br />

### 1.3. Static method
* directly using the function
* it is commonly used to tell people that the function will not be inherited

```python
class Foo:
    @staticmethod
    def hi(cls):
      ...
```

<br />

### 1.4. [Class Inheritance](https://stackoverflow.com/a/27134600)
```python
class ChildA(Base):
    def __init__(self):
        Base.__init__(self)
  
    def f(self):
      return 'A'

class ChildB(Base):
    def __init__(self):
        super(ChildB, self).__init__()

    def f(self):
      parent_result = super().f()

      
```
* super().__init__() = super(ChildB, self).__init__()
  > Python2, inheritance is required like `super(ChildB, self).__init__()`

* Base.__init__(self) is not recommended
  >  can not use multiple inheritance since the next parent's call is hard coded

<br />

# Multiple Inheritance
* commonly used in mixins

```python
  class A:
    def f(self):
      return 'A'

  class B:
    def g(self):
      return 'B'

  # Now, child can call both f and g methods
  class child(A, B):
    pass

```
* if a class inherits multiple classes with the same method names, `Method Resolution Order`(MRO) is considered
    * consider the first matching method following the order of the parent classes
      ```python
      # See the order
        child_class.mro()
      
      ```
  ```python
  class A:
    def f(self):
      return 'A'

  class B:
    def f(self):
      return 'B'

  # call f from class A
  class child(A, B):
    pass
  ```


<br />

# Packages

<br />

# Commands 
## Magic Methods
### Object Representations: `__repr__`, `__str__`
* `repr` for software engineers
* `str`: change the results of `print`
```python
    class Temperature:
    def __init__(self, value, scale):
        self.value = value
        self.scale = scale

    def __repr__(self):
        return f"Temperature({self.value}, {self.scale!r})"

    def __str__(self):
        return f"Temperature is {self.value} °{self.scale}"


    t = Temperature(25, "C")
    print(repr(t))  # "Temperature(25, 'C')"
    print(str(t))  # "Temperature is 25 °C"
    print(t) # "Temperature is 25 °C"

```

### Comparison Methods: `__eq__`, `__gt__`, `__it__`
* useful when there are different units
* TODO

### Callable Object: `__call__` (TODO)
* call object instance like a regular function
```python
    class Counter:
    def __init__(self):
        self.counter = 0

    def __call__(self, inc=1):
        self.counter += inc


    c = Counter()
    print(c.counter)  # 0
    c()
    print(c.counter)  # 1
    c(10)
    print(c.counter)  # 11

```