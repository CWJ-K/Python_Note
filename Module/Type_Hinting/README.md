<!-- omit in toc -->
# Introduction
List all typing hints 

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. type annotations in Python](#1-type-annotations-in-python)
- [Packages](#packages)
  - [1. mypy](#1-mypy)
  - [2. typing](#2-typing)
    - [2.1. Data structure](#21-data-structure)
    - [2.2. list with elements of different types](#22-list-with-elements-of-different-types)
    - [2.3. None in parameters](#23-none-in-parameters)
    - [2.4. Complex types](#24-complex-types)
    - [2.5. classes](#25-classes)
    - [2.6. type function signatures with callable](#26-type-function-signatures-with-callable)
    - [2.7. values can be anything](#27-values-can-be-anything)
- [Commands](#commands)

<br />

# Fundamental Concepts

## 1. type annotations in Python
* type annotations are optional and ignored by the interpreter
<br />

# Packages

## 1. mypy
* static-type checkers
* check if the type hinting is correct on the script
  ```s
  pip install mypy

  mypy script.py
  
  ```
* it integrates with IDE

## 2. typing
> type[class/None/...]

### 2.1. Data structure
  ```python
  from typing import Dict, List, Set, Tuple
  
  l: List[int] = [1, 2, ,3, 4]
  t: Tuple[int, str, float] = (1, 'hello', 3.14)
  s: Set[int] = {1, 2, 3, 4, 5}
  d: Dict[str, int] = {'a': 1, 'b': 2, 'c': 3}
  
  ```

### 2.2. list with elements of different types
  ```python
  from typing import List, Union

  l: List[Union[int, float]] = [1, 2.5, 3.14, 5]
  
  ```

### 2.3. None in parameters
  * Method 1
  ```python
  from typing import Union

  def greeting(name: Union[str, None]=None) -> str:
    ...
  ```

 * Method 2 
  ```python
  from typing import Optional
  
  def greeting(name: Optional[str]=None) -> str:
  
  ```

### 2.4. Complex types
  ```python
  from typing import Tuple

  IntStringFloatTuple = Tuple[int, str, float]

  t: IntStringFloatTuple = (1, 'hello', 3.14)
  ```

### 2.5. classes
  ```python 
    from typing import List

    class Post:
        def __init__(self, title: str) -> None:
            self.title = title
        
        def __str__(self) -> str:
            return self.title
    
    posts: List[Post] = [Post('hi'), Post('hello')]
  ```

### 2.6. type function signatures with callable
  * pass a function as arguments
    > `...` implies any number of arguments

    ```python
    from typing import Callable, List

    ConditionFunction = Callable[[int], bool, ...]

    def filter_list(l: List[int], condition: ConditionFunction) ->
    List(int):
        return [i for i in l if condition(i)]
    
    def is_even(i: int) -> bool:
        return i % 2 == 0

    filter_list([1, 2, 3, 4, 5], is_even)

    ```

### 2.7. values can be anything
  * `Any`: any values
  * `cast`: force the type check to consider the type you specify
    > only for type checkers; may be useful for unit test
  > do not use too much or typing hinting becomes meaningless  
  ```python
    from typing import Any, cast
    
    def f(x: Any) -> Any:
        return x

    a = f('a')
    a = cast(str, f('a'))

  ```

<br />

# Commands 