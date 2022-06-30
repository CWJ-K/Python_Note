<!-- omit in toc -->
# Introduction
How to validate data by schemas?

<br />

<!-- omit in toc -->
# Table of Contents
- [Packages](#packages)
  - [1. Pydantic](#1-pydantic)
- [Commands](#commands)
  - [1. Define objects in pydantic by](#1-define-objects-in-pydantic-by)
  - [2. Initialization of the object performs all **parsing** and **validation**](#2-initialization-of-the-object-performs-all-parsing-and-validation)


<br />

# Packages

## 1. Pydantic
* to validate data schema and change types based on schema
* can change original column types to fit in a data schema
* can support models that map to **ORM** objects
    
<br />

# Commands

## 1. Define objects in pydantic by 

  ```python
  from pydantic import BaseModel

  class Schema(BaseModel):
      name: str   # data type
      column1 = 5 # default value
      column2: List[str]
      column3: Optional[str] = None 
      column4: Dict[str, int]
      column5: Class(BaseModel) 
  ```

  * column3: default value is None, expected type is string
  * column5: use other class inherited BashModel, if the structure of data is complex

<br />

## 2. Initialization of the object performs all **parsing** and **validation**
    
  ```python
  # validate input data - name, column2
  test = Schema(name='hi', column2=['hello', 'world'])
  ```

