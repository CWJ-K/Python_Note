<!-- omit in toc -->
# Introduction
Take note of methods for data validation


<br />

<!-- omit in toc -->
# Table of Contents
- [Packages](#packages)
  - [Pydantic](#pydantic)
- [Commands](#commands)
  - [Define objects in pydantic by](#define-objects-in-pydantic-by)
  - [Initialization of the object performs all **parsing** and **validation**](#initialization-of-the-object-performs-all-parsing-and-validation)


<br />

# Packages
## Pydantic
* to validate data schema and change types based on schema
* can change original column types to fit in a data schema
* can support models that map to **ORM** objects
    
<br />

# Commands
## Define objects in pydantic by 

    from pydantic import BaseModel

    class Schema(BaseModel):
        name: str   # data type
        column1 = 5 # default value
        column2: List[str]
        column3: Optional[str] = None 
        column4: Dict[str, int]
        column5: Class(BaseModel) 

  * column3: default value is None, expected type is string
  * column5: use other class inherited BashModel, if the structure of data is complex

<br />

## Initialization of the object performs all **parsing** and **validation**
    
    # validate input data - name, column2
    test = Schema(name='hi', column2=['hello', 'world'])

