# Input Output (I/O)

Many of you reading this have probably come from [Code in Game](https://www.codingame.com/), where most of the file management has been automated for you. However, as you progress through different community puzzles you may want to work out more complex examples for yourself or even make your own contributions. 
If this is the case, or if you're just curious, then you might be interested in learning some of the basics of working with your own files. The good news is that this is incredibly easy! There are essentially only 4 things you need to do in order use your own data in a python script.

* Import os
* open(filePath, "mode")
* parse the data from the file
* close()

## The Python OS Library

For full documentation read the [Python os docs](https://docs.python.org/3/library/os.html).

At the beginning of your script you need to include ```import os```. This will allow you to use two very important functions: ```open()``` and ```close()```.

## Open

The os.open function is fairly simple. It only requires one parameter, a string defining the location of the file that you are interested in using. By default python opens the file as **read** only. This means that you can access all of the data contained within the file, but you cannot change or update the file itself. If you want to **write** data to the file, then you need to pass an additional parameter. Additional acceptable **mode** parameter values include: "**x**", "**a**", "**b**", "**t**", and "**+**".

```python
import os

# all data from file1 can be read, but the file itself cannot be altered 
file1 = open("\\path\\to\\file\\file1.txt")

# additional data can be written to file2 
file2 = open("\\path\\to\\file\\file2.txt", "w")

# file3 is also read only, like file1
file3 = open("\\path\\to\\file\\file3.txt", "r")
```

### File Path String 

When using backslashes in the file path a second `\` character is required to escape the behavior of a single `\` in a string. Depending on your operating system you made need to format this string differently or use forward slashes.

You can also take advantage of the [os.path](https://docs.python.org/3/library/os.path.html) methods.

```python 

import os

pathString = "text.txt"
absPath = os.path.abspath(pathString)

print(absPath) # result (mac): /Users/username/pythonProjects/text.txt

```

## Close

Best practice when dealing with files is to close any file that you have opened before your script finishes executing. This is done using the close function.

```python
import os

file = open("\\path\\file.txt")

file.close()
```

## How to Actually Use Your Data

This is arguably the most important step in this process. There are a lot of different ways to read and write data, and it all depends on the problem you are trying to solve. Sometimes you have written the data files yourself, and other times you will have to work with someone else's formatting. Below are a couple simple examples for reading and writting a simple text file.

### Reading

### Writing

# sys and input()

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Python template](https://tech.io/select-repo/429)
