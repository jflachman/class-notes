## Class Notes Table of Contents

-   [Course Overview](README.md)
-   [Tool Setup](1_DU_tool_setup.md)
-   [Tool Setup Mac](1.1_DU_tool_setup_mac.md)
-   [Tool Setup Windows](1.2_DU_tool_setup_windows.md)
-   [Tool Setup Windows - alternate setup](1.2.1_DU_tool_setup_windows_WSL.md)
-   [Online Research Tips](2_Online_Research_Tips.md)
-   [Further Reading and Helpful Links](3_Further_Reading_and_Helpful_Links.md)
-   [Articles & Subscriptions](4_Articles_and_subscriptions.md)
-   [Career Engagement](6_Useful_Python.md)

----------------------------------------------

# Useful Python Stuff

## Clearing the screen
```
import os
 
# Clearing the Screen
os.system('cls')
```
## Check value type
```
if type(mydict) is dict:
if type(mylist) is list:
if type(myint) is int:
if type(myfloat) is float:
if type(mystring) is string:
```

## check if main program

Add this for code your intend to run directly from the command line.

```
if __name__ == "__main__"
```

See more here: [What Does if __name__ == "__main__" Do in Python?](https://realpython.com/if-name-main-python/)

## Special Functions

### map
The map() function executes a specified function for each item in an iterable. The item is sent to the function as a parameter.

*Syntax*
```
map(function, iterables)
```

*Example*
```
def myfunc(a, b):
  return a + b

x = map(myfunc, ('apple', 'banana', 'cherry'), ('orange', 'lemon', 'pineapple'))

print(x)

#convert the map into a list, for readability:
print(list(x))
```
returns:
```
<map object at 0x034244F0>
['appleorange', 'bananalemon', 'cherrypineapple']
```

| Parameter | Description |
| --------- | ----------- |
|function | Required. The function to execute for each item
|iterable | Required. A sequence, collection or an iterator object. You can send as many iterables as you like, just make sure the function has one parameter for each iterable.


### lambda
A lambda function is a small anonymous function.

A lambda function can take any number of arguments, but can only have one expression.

*Syntax*
```
lambda arguments : expression
```

*Example 1*
```
x = lambda a, b : a * b
print(x(5, 6))
```

*Example 2*
```
x = lambda a, b : a * b
print(x(5, 6))
```

*Example 3*
```
x = lambda a, b, c : a + b + c
print(x(5, 6, 2))
```
### filter
The filter() function returns an iterator where the items are filtered through a function to test if the item is accepted or not.

*Syntax*

```
filter(function, iterable)
```

*Parameter Values*
| Parameter | Description |
| --------- | ----------- |
| function | A Function to be run for each item in the iterable |
| iterable | The iterable to be filtered |

*Example*
```
ages = [5, 12, 17, 18, 24, 32]

def myFunc(x):
  if x < 18:
    return False
  else:
    return True

adults = filter(myFunc, ages)

for x in adults:
  print(x)
```

returns:
```
18
24
32
```

## Docstring

See the [Docstring tutorial]()