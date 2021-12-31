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

When using backslashes in the file path a second `\` character may be required to escape the behavior of a single `\` in a string. Depending on your operating system you made need to format this string differently or use forward slashes.

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

This is arguably the most important step in this process. There are a lot of different ways to read and write data, and it all depends on the problem you are trying to solve. 
Sometimes you have written the data files yourself, and other times you will have to work with someone else's formatting. 
Below are a couple simple examples for reading and writting a simple text file.

### Reading

First let's look at what results when we open a file and store this data as a variable. We are using a simple text file containing the following:

```text
Line 1
Line 2
Line 3
```

Using the methods discussed above import the os library to enable the open and close methods, and save the data from the file as a variable we call `file`.


```python 
import os

path = "/Users/username/demoFolder/data.txt"
file = open(path);

print(type(file))

for line in file:
    print(line)

file.close()
```

The results from this script first print the data type of the `file` variable. It is a special data type reserved for os data, but we do not need to go in depth about it now. 
The main point is that this variable is *iterable*. Using a simple for loop you can read one line at a time. These lines are simple strings and can be manipulated as such.

```console
 >>> python demo.py 
 <type 'file'>
 Line 1

 Line 2

 Line 3
```

The additional lines printed between the text file data is a result of carriage return characters in the text file itself. These can be eliminated by 
using methods like `string.strip()`, may require importing the string library.

### Writing

If you wish to add data to a file, you need to tell python that you plan to *write* data to the file when you use the open method. Then simply use the 
`write()` or `writeline()` method on the file variable. See example below:

```python
import os

path = "/Users/username/pythonProjects/text.txt"
file = open(path, "w");

for i in range(4):
    file.write(str(i))

file.close()
```

The resulting text file will look as follows:

```text 
0123
```

If you want to write to a new line, there are several different ways to do this. One way is to simply add a newline character after your data in the write method.

`file.write(str(i) + "\n")`

You can also use the `writelines()` method that takes an array as an argument:

`file.writelines(["Line 1", "Line 2", "Line 3"])`



# sys and input()

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Python template](https://tech.io/select-repo/429)
