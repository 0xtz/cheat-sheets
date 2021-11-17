

# Input and Output *🐍 Python*

# Python 3's f-Strings:

## 1.1 “Old-school” String Formatting in Python

```python
# optios #1 : %s

>>> name = "0xtz"
>>> age = 18
>>> "Hello, %s." % name
'Hello, 0xtz.'
# Option #2: str.format()
>>> "Hello, {}. You are {}.".format(0xtz, age)
'Hello, 0xtz. You are 19.'


```

### 

```python
>>> first_name = "0xtz"
>>> last_name = "Idle"
>>> age = 18
>>> profession = "comedian"
>>> affiliation = "Monty Python"
>>> print(("Hello, {first_name} {last_name}. You are {age}. " + 
>>>        "You are a {profession}. You were a member of {affiliation}.") \
>>>        .format(first_name=first_name, last_name=last_name, age=age, \
>>>                profession=profession, affiliation=affiliation))
'Hello, 0xtz Idle. You are 18. You are a comedian. You were a member of Monty Python.'


```

## 1.2 f-Strings: A New and Improved Way to Format Strings in Python :


### Simple Syntax :

The syntax is similar to the one you used with `str.format()` but less verbose. Look at how easily readable this is: 
It would also be valid to use a capital letter F:
```py
>>> name = "0xtz"
>>> age = 18
>>> f"Hello, {name}. You are {age}."
'Hello, 0xtz. You are 18.'
>>> #It would also be valid to use a capital letter F:
>>> F'Hello, {name}. You are {age}.'
'Hello, 0xtz. You are 18.'

```

## Arbitrary Expressions

Because f-strings are evaluated at runtime, you can put any and all valid Python expressions in them. This allows you to do some nifty things.

*F-strings are just amazing*

```py
class Comedian:
	'''  YOU CAN EVEN USE THEM INSIDE YOUR OBJ its just work '''
    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

    def __str__(self):
        return f"{self.first_name} {self.last_name} is {self.age}."

    def __repr__(self):
        return f"{self.first_name} {self.last_name} is {self.age}. Surprise!"

```

You’d be able to do this:
```py
>>> new_comedian = Comedian("0xtz", "Idle", "18")
>>> f"{new_comedian}"
'0xtz Idle is 18.'
```


> for more info read the (*the official DOCs*)[https://docs.python.org/3/tutorial/inputoutput.html]
> i get those from [realpython](https://realpython.com/python-f-strings/)


## follow me on :

(![@0xtz](http://i.imgur.com/tXSoThF.png))(https://twitter.com/0xtz_52)

