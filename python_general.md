# general

## To make a python file executable

Add the following to the bigenning of the file.py (Shell scripts usually start with #!/bin/bash or #!/bin/sh.):

    #!/usr/bin/env python3

Then run:

    chmod +x file.py
    # more help on chmod:
    man chmod  # (man for manual)

Now you can run the file.py 
 
    ./file.py

Unless . (or the parent directory of file.py) is in your PATH variable you need to include ./ before the name (or the full path to the executable).
perhaps you want the program on your PATH so you can run it at any time


## Do not use these for variable naming

    # To show all current keywords:
    import keyword
    print(keyword.kwlist)
    
    # To show all builtins:
    dir(__builtins__)
    
a few built-ins that would be tempting variable names otherwise: 

    dict, id, list,
    min, max, open, 
    range, str, sum, and type.

### dir() lists all the attributes of the object passed into it.
### A basic rule of thumb is that a comment should explain the why rather than the how (code alone should be sufficient for the how). 

# Strings
## string methods:

    S.capitalize()
    S.endswith('.xlsx')
    S.startswith('Oct')
    S.find('ate')
    S.lower().endswith('txt')
    S.strip()
    
# Lists

## Removing items from lists during iteration

    names = ['John', 'Paul', 'George', 'Ringo']
    for name in names[:]: # copy of names
        if name not in ['John', 'Paul']:
        names.remove(name)

# Dictionaries

## The .get method of a dictionary will retrieve a value for a key.

## Counter
Performing counting of all members in a collection

    import collections
    count = collections.Counter(['Ringo', 'Paul','John', 'Ringo'])
    >>> count
    Counter({'Ringo': 2, 'Paul': 1, 'John': 1})
    >>> count['Ringo']
    2
    >>> count['Fred']
    0

## defaultdict
This class behaves like a dictionary but it also allows for setting the default value of a key to an arbitrary factory. If the default factory is not None, it is initialized and inserted as a value any time a key is missing.

    from collections import defaultdict
    names_to_bands = defaultdict(list)
    for name in band1_names:
        names_to_bands[name].append('Beatles')
    for name in band2_names:
        names_to_bands[name].append('Wings')
    >>> print(names_to_bands['Paul'])
    ['Beatles', 'Wings']

 ## Dictionary iteration
 
    for key in data:
    
    # You can also do a lookup by value, but it is slow. If you find yourself doing this operation often, 
    # it is a code smell that you should use a different data structure.
    for value in data.values():
    
    for key, value in data.items():
    
    for name in sorted(data.keys(), reverse=True):
    
# remove a key from a Python dictionary

If key is in the dictionary, remove it and return its value, else return default. 
If default is not given and key is not in the dictionary, a KeyError is raised.

    my_dict.pop("key", None) # default : None
    
    try:
        del my_dict['key']
    except KeyError:
        pass
 
Python will prevent you from adding to or removing from a dictionary while you are looping over it. 
Python will throw a RuntimeError:

    >>> data = {'name': 'Matt'}
    >>> for key in data:
            del data[key]
    Traceback (most recent call last):
    ...
    RuntimeError: dictionary changed size during iteration

# functions

# lambda functions:

    # Syntax of Lambda Function – lambda arguments: expression
    
    #Simple Lambda Function
    multiply = lambda a, b : a * b
    print(multiply(5, 7))
    
    #Lambda Function within a normal function
    def myAdditionFunctionWithLambda(add):
        return lambda val: val+add
        
    square_result=myAdditionFunctionWithLambda(2)
    print(square_result(5))
    
## map()

Takes a function as one of its arguments and the sequence as its second argument and applies the function to each and every element of the sequence.

    Syntax - resulting_map = map(function , sequence)

    #converting Celsius to Fahrenheit
    Celsius = [40, 33.2, 35.3, 41.8, 30.1]
    Fahrenheit = list(map(lambda x: (float(9)/5)*x + 32, Celsius))
    
map returns an iterator that yields the returened values.

## filter:
is used to filter out all elements from the list, for which the function returns True.

    # Syntax – filter(function,list)
    
    numbers = [0,0,1,2,3,5,6,9,11,23,34,45,50,77]
    
    #obtaining the odd numbers from the numbers list
    odd_numbers = filter(lambda x: x % 2, numbers)
    print(list(odd_numbers))
    
    #obtaining the even numbers from the numbers list
    even_numbers = filter(lambda x: x % 2 == 0, numbers)
    print(list(even_numbers))

## reduce
is used to continuously apply a function logic to the elements of the list.
Syntax – reduce(function,list)

    from functools import reduce #importing the reduce library
    
    counting=reduce(lambda x, y: x+y, range(1,50))
    print("Sum of numbers 1 to 50 is {}".format(counting))
    
    multiplying=reduce(lambda x,y: x*y, [1,5,10])
    print("Multiplied list result is {}".format(multiplying))
    
    largest_in_list = lambda a,b: a if (a > b) else b
    largest=reduce(largest_in_list, [100,101,155,122,210])
    print("Largest element of list is {}".format(largest)

# Store and load class instances
    
    # save
    joblib.dump(instance, 'file_name.sav')
    
    # load
    instance = joblib.load('file_name.sav')

# Store and load numpy arrays
    
    # save
    np.savetxt('file_name.txt', array, fmt='%d')
    
    # load
    array = np.loadtxt('file_name.txt', dtype = int)
    
    
    
