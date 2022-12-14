<div align="center">
  <h1> 30 Days Of Python: Day 8 - Dictionaries</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Second Edition: July, 2021</small>
</sub>

</div>

[<< Day 7 ](../07_Day_Sets/07_sets.md) | [Day 9 >>](../09_Day_Conditionals/09_conditionals.md)

![30DaysOfPython](../../images/30DaysOfPython_banner3@2x.png)

- [๐ Day 8](#-day-8)
  - [Dictionaries](#dictionaries)
    - [Creating a Dictionary](#creating-a-dictionary)
    - [Dictionary Length](#dictionary-length)
    - [Accessing Dictionary Items](#accessing-dictionary-items)
    - [Adding Items to a Dictionary](#adding-items-to-a-dictionary)
    - [Modifying Items in a Dictionary](#modifying-items-in-a-dictionary)
    - [Checking Keys in a Dictionary](#checking-keys-in-a-dictionary)
    - [Removing Key and Value Pairs from a Dictionary](#removing-key-and-value-pairs-from-a-dictionary)
    - [Changing Dictionary to a List of Items](#changing-dictionary-to-a-list-of-items)
    - [Clearing a Dictionary](#clearing-a-dictionary)
    - [Deleting a Dictionary](#deleting-a-dictionary)
    - [Copy a Dictionary](#copy-a-dictionary)
    - [Getting Dictionary Keys as a List](#getting-dictionary-keys-as-a-list)
    - [Getting Dictionary Values as a List](#getting-dictionary-values-as-a-list)
  - [๐ป Exercises: Day 8](#-exercises-day-8)

# ๐ Day 8

## Dictionaries

Dictionary๋ ์์๊ฐ ์๋ ์์ (๋ณํ) ๊ฐ๋ฅํ ์(ํค: ๊ฐ)์ ์๋ฃํ์ ์ปฌ๋ ์์๋๋ค.

### Creating a Dictionary

Dictionary๋ฅผ ๋ง๋ค๋ ค๋ฉด ์ค๊ดํธ {} ๋๋ *dict()* ๋ด์ฅ ํจ์๋ฅผ ์ฌ์ฉํฉ๋๋ค.

```py
# syntax
empty_dict = {}
# Dictionary with data values
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
```

์๋จ์ Dictionary๋ ๊ฐ์ด ์ด๋ค ์๋ฃํ์ผ ์๋ ์๋ค๋ ๊ฒ์ ๋ณด์ฌ์ค๋๋ค:string, boolean, list, tuple, set ๋๋ dictionary.

### Dictionary Length

dictionary ๋ด 'key: value' ์์ ๊ฐ์๋ฅผ ํ์ธํฉ๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(len(dct)) # 4
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(len(person)) # 7

```

### Accessing Dictionary Items

ํค์ ์ด๋ฆ์ ํตํด ๋์๋๋ฆฌ ์์ดํ์ ์ ๊ทผํ  ์ ์์ต๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct['key1']) # value1
print(dct['key4']) # value4
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person['first_name']) # Asabeneh
print(person['country'])    # Finland
print(person['skills'])     # ['JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person['skills'][0])  # JavaScript
print(person['address']['street']) # Space street
print(person['city'])       # Error
```

์กด์ฌํ์ง ์๋ ํค์ ์ด๋ฆ์ผ๋ก ์์ดํ์ ์ ๊ทผํ  ๊ฒฝ์ฐ ์๋ฌ๊ฐ ๋ฐ์ํ  ์ ์์ต๋๋ค. ์ด ์๋ฌ๋ฅผ ํผํ๊ธฐ์ํด ์ฐ๋ฆฌ๋ ์ฐ์  ํค๊ฐ ์กด์ฌํ๋์ง ํ์ธํด์ผํฉ๋๋ค. ๋๋ _get_ ๋ฉ์๋๋ฅผ ์ฌ์ฉํ ์ ์์ต๋๋ค. get ๋ฉ์๋๋ ํค๊ฐ ์กด์ฌํ์ง ์์ ๊ฒฝ์ฐ, NoneType object ์๋ฃํ์ธ None์ ๋ฐํํฉ๋๋ค.
```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
print(person.get('first_name')) # Asabeneh
print(person.get('country'))    # Finland
print(person.get('skills')) #['HTML','CSS','JavaScript', 'React', 'Node', 'MongoDB', 'Python']
print(person.get('city'))   # None
```

### Adding Items to a Dictionary

๋์๋๋ฆฌ์ ์๋ก์ด ํค์ ๊ฐ์ ์์ ์ถ๊ฐํ  ์ ์์ต๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key5'] = 'value5'
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
        }
}
person['job_title'] = 'Instructor'
person['skills'].append('HTML')
print(person)
```

### Modifying Items in a Dictionary

๋์๋๋ฆฌ์ ์์ดํ์ ์์ ํ  ์ ์์ต๋๋ค

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct['key1'] = 'value-one'
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person['first_name'] = 'Eyob'
person['age'] = 252
```

### Checking Keys in a Dictionary

๋์๋๋ฆฌ์ ํค๊ฐ ์กด์ฌํ๋ ์ง ํ์ธํ๊ธฐ ์ํด  _in_ ์ฐ์ฐ์๋ฅผ ์ฌ์ฉํฉ๋๋ค

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print('key2' in dct) # True
print('key5' in dct) # False
```

### Removing Key and Value Pairs from a Dictionary

- _pop(key)_: ํน์  ํค ์ด๋ฆ์ ๊ฐ์ง ์์ดํ์ ์ญ์ ํฉ๋๋ค
- _popitem()_: ๋ง์ง๋ง ์์ดํ์ ์ญ์ ํฉ๋๋ค
- _del_: ํน์  ํค ์ด๋ฆ์ ๊ฐ์ง ์์ดํ์ ์ญ์ ํฉ๋๋ค

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.pop('key1') # removes key1 item
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct.popitem() # removes the last item
del dct['key2'] # removes key2 item
```

**Example:**

```py
person = {
    'first_name':'Asabeneh',
    'last_name':'Yetayeh',
    'age':250,
    'country':'Finland',
    'is_marred':True,
    'skills':['JavaScript', 'React', 'Node', 'MongoDB', 'Python'],
    'address':{
        'street':'Space street',
        'zipcode':'02210'
    }
    }
person.pop('first_name')        # Removes the firstname item
person.popitem()                # Removes the address item
del person['is_married']        # Removes the is_married item
```

### Changing Dictionary to a List of Items

_items()_ ๋ฉ์๋๋ ๋์๋๋ฆฌ๋ฅผ ํํ์ ๋ฆฌ์คํธ๋ก ๋ณํํฉ๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.items()) # dict_items([('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'), ('key4', 'value4')])
```

### Clearing a Dictionary

๋์๋๋ฆฌ ๋ด์ ์์ดํ์ ์ํ์ง ์๋๋ค๋ฉด  _clear()_ ๋ฉ์๋๋ฅผ ์ฌ์ฉํด ๋น์ธ ์ ์์ต๋๋ค

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
print(dct.clear()) # None
```

### Deleting a Dictionary

๋์๋๋ฆฌ๋ฅผ ์ฌ์ฉํ์ง์๋๋ค๋ฉด ์์ ํ ์ง์ธ ์ ์์ต๋๋ค

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
del dct
```

### Copy a Dictionary

_copy()_ ๋ฉ์๋๋ฅผ ํตํด ๋์๋๋ฆฌ๋ฅผ ๋ณต์ฌํ  ์ ์์ต๋๋ค. copy๋ฅผ ์ฌ์ฉํด ์๋ ๋์๋๋ฆฌ์ ๋ณํ๋ฅผ ๋ง์ ์ ์์ต๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
dct_copy = dct.copy() # {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
```

### Getting Dictionary Keys as a List

_keys()_ ๋ฉ์๋๋ ํ๋์ ๋์๋๋ฆฌ์ ๋ชจ๋  ํค๋ฅผ ๋ฆฌ์คํธ๋ก ์ค๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
keys = dct.keys()
print(keys)     # dict_keys(['key1', 'key2', 'key3', 'key4'])
```

### Getting Dictionary Values as a List

_values_ ๋ฉ์๋๋ ํ๋์ ๋์๋๋ฆฌ์ ๋ชจ๋  ๊ฐ์ ๋ฆฌ์คํธ๋ก ์ค๋๋ค.

```py
# syntax
dct = {'key1':'value1', 'key2':'value2', 'key3':'value3', 'key4':'value4'}
values = dct.values()
print(values)     # dict_values(['value1', 'value2', 'value3', 'value4'])
```

๐ ๋น์ ์ ์ ๋ง ๋๋ผ์์. ์ด์ , ์ฌ๋ฌ๋ถ์ ์ฌ์ ์ ํ์ผ๋ก ์์ ํ ์ถฉ์ ๋์ด ์์ต๋๋ค. ์ฌ๋ฌ๋ถ์ ์ด์  ๋ง 8์ผ์งธ์ ๋์ ์ ๋ง์ณค๊ณ  ์๋ํจ์ ํฅํด 8๋ณด ์ ์งํ์ต๋๋ค. ์ด์  ์ฌ๋ฌ๋ถ์ ๋์ ๊ทผ์ก์ ์ํ ์ด๋์ ํ์ธ์.

## ๐ป Exercises: Day 8

1. dog๋ผ๋ ์ด๋ฆ์ ๋น ๋์๋๋ฆฌ๋ฅผ ์์ฑํฉ๋๋ค
2. dog ๋์๋๋ฆฌ์ name, color, breed, legs, age ๋ฅผ ์ถ๊ฐํฉ๋๋ค
3. student ๋์๋๋ฆฌ๋ฅผ ์์ฑํ๊ณ  first_name, last_name, gender, age, marital status, skills, country, city ์ address ๋ฅผ ํค๋ก ์ถ๊ฐํฉ๋๋ค
4. student ๋์๋๋ฆฌ์ ๊ธธ์ด๋ฅผ ์ป์ต๋๋ค
5. skills ์ ๊ฐ์ ์ป๊ณ  ์๋ฃํ์ ํ์ธํฉ๋๋ค, list ์ฌ์ผ ํฉ๋๋ค
6. ํ๊ฐ๋ ๋๊ฐ๋ฅผ ์ถ๊ฐํด skills์ ๊ฐ์ ์์ ํฉ๋๋ค
7. ๋์๋๋ฆฌ์ ํค๋ฅผ ๋ฆฌ์คํธ๋ก ์ป์ต๋๋ค
8. ๋์๋๋ฆฌ์ ๊ฐ์ ๋ฆฌ์คํธ๋ก ์ป์ต๋๋ค
9. _items()_ ๋ฉ์๋๋ฅผ ์ด์ฉํด ํํ์ ๋ฆฌ์คํธ๋ก ๋์๋๋ฆฌ๋ฅผ ๋ฐ๊ฟ๋๋ค
10. ๋์๋๋ฆฌ์ ์์ดํ์ค ํ๋๋ฅผ ์ญ์ ํฉ๋๋ค
11. ๋์๋๋ฆฌ ์ค ํ๋๋ฅผ ์ญ์ ํฉ๋๋ค

๐ CONGRATULATIONS ! ๐

[<< Day 7 ](../07_Day_Sets/07_sets.md) | [Day 9 >>](../09_Day_Conditionals/09_conditionals.md)
