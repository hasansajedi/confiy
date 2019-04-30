# **confiy**

With this library you can easy read config file and get your value only by key, in python projects.
Confiy is easiest way to read config file only with key. 
#### Install:
```python
pip install confiy
```

#### Caution:
You must create a config file where you need to call, with any extension but .cnf is better and then write your configs in file such as following lines:

- my_prj
    - db
        - conf.cnf
        ```python
            key1=1234
            key2="string with value2"
            key3="string with value3"
        ```   
        - connector.py 
        ```python
            from confiy.confiy import confiy
            print(confiy().getValue(key='key1'))
        ```   

If you have multiple value for entered key, you can set allow_duplicate with boolean value and you have two choice:

    1. (True) Get all of them as a list
    2. (False) Get the ValueError exception
    
getValue function have a boolean variable with allow_duplicate name. Default value is True, if tou set it False , you get ValueError exception.

- conf.cnf 
    ```python
        key1=value1
        key2="string with value2"
        key3="string with value3"
        key1=value2
        key1=value3
    ```   
    Output:
    ```python
        ['value3', 'value2', 'value1']
    ``` 
    
Use python version >= 2.7
