# Validate Data

## Package: Pydantic
Goal: to validate data schema and change types based on schema

    from pydantic import BaseModel
    class Schema(BaseModel):
        name: str   # data type
        column1 = 5 # default value
        column2: List[str]
        column3: Optional[str] = None # default value is None, expected type is string
        column4: Dict[str, int]
        column5: Class(BaseModel) # use other class with BashModel, if the structure of value is complex

    if __name__ == "__main__":
        test = Schema(name='hi', column2=['hello', 'world'])

### can output data after validation in different types
#### json
    test_josn = Schema(foo=datetime(2032, 6, 1, 12, 13, 14), bar={'whatever': 123})
    test_josn.json()

#### pickle
    validated_data = Schema(foo=datetime(2032, 6, 1, 12, 13, 14), bar={'whatever': 123})
    test_pickle = pickle.dumps(validated_data)
    test_pickle_final = pickle.loads(test_pickle)