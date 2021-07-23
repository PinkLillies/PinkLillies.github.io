# Python - Basics




## Print

```python
print("Hello, world!")
```

## Input

```python
name = input("Name:")
print(f"Hello, {name}")
```


## List


```python
names = ["Bob", "Brad", "Jennifer", "Bianca"]
print(names[0])
names.append("Josephine")
names.sort()
```




## Tuple


## Set


## Dictionary

Mapping of keys to values

```python
cities = {"Bianca":"Los Angeles","Jenifer":"Miami"}
print(cities["Jenifer"])
```


## Loops

```python
for i in [1,2,3,4,5]:
    print(i)
```


```python
for i in range(100)
    print(i)
```

## Length

len(s)

## Define a function

```python
def square(x):
    return x*x
for i in range(10):
    print(f"The square of {i} is {square(i)}")
```


## Class

```python
class Bird:
    count=0
    def __init__(self, chat):
        self.sound=chat
        Bird.count +=1
    def talk(self):
        return self.sound
 ```
 
## Create an instance of the class
 
 ```python
 Bird instance polly
 from Bird import *
 polly = Bird('Squawk, squawk!')
 print(polly.count)
 print(polly.talk())
 ```
 
 
 

You can download Python [here](https://www.python.org/)


![cat3](https://pinklillies.github.io/images/cat3.jfif)

