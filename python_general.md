# To make a python file executable

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


# Do not use these for variable naming

    # To show all current keywords:
    import keyword
    print(keyword.kwlist)
    
    # To show all builtins:
    dir(__builtins__)
    
a few built-ins that would be tempting variable names otherwise: 

    dict, id, list,
    min, max, open, 
    range, str, sum, and type.


# dir() lists all the attributes of the object passed into it.
