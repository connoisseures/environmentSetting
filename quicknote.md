Python Quick Note
===============

Notes
-----------

### covention 
+ file naming
  - https://stackoverflow.com/questions/2235173/file-name-path-name-base-name-naming-standard-for-pieces-of-a-path

### string
+ format
  - https://www.programiz.com/python-programming/methods/string/format
```python
# padding for float numbers
print("{:8.3f}".format(12.2346))
```

### class

+ Structs without constructors:
  - https://stackoverflow.com/questions/35988/c-like-structures-in-python  

```python
class Sample:
  name = ''
  average = 0.0
  values = None # list cannot be initialized here!
```

### list
+ tutorial 
  - http://openbookproject.net/thinkcs/python/english3e/lists.html
```python
#add code here to figure out the number of 0's you need, naming the variable n.
listofzeros = [0] * n
```
### dict
+ defaultdict
  - https://docs.python.org/3/library/collections.html#collections.defaultdict
  - http://l4wisdom.com/python/python_collection_default.php

### library
+ sort
  - https://www.programiz.com/python-programming/methods/built-in/sorted
```python
# set
pySet = {'e', 'a', 'u', 'o', 'i'}
print(sorted(pySet, reverse=True))

# dictionary
pyDict = {'e': 1, 'a': 2, 'u': 3, 'o': 4, 'i': 5}
print(sorted(pyDict, reverse=True))
# output:['u', 'o', 'i', 'e', 'a']
```
### decorator
+ https://www.datacamp.com/community/tutorials/decorators-python


### sample
```python
def get_image_subdir(self, path):
      return [os.path.join(path, x, 'images') for x in os.listdir(path) if os.path.isdir(os.path.join(path, x))]

    def get_files(self, path):
      return [x for x in os.listdir(path) if os.path.isfile(os.path.join(path, x))]

    def get_filelist_from_dir(self, subdirs, shuffle):
      filelists = defaultdict(list)
      size_of_filelists = defaultdict(int)
      for d in subdirs:
        filelists[d] = self.get_files(d)
        size_of_filelists[d] = len(filelists[d])
        if shuffle:
          np.random.shuffle(filelists[d])
      return filelists, size_of_filelists
```

https://cmdlinetips.com/2012/09/three-ways-to-write-text-to-a-file-in-python/


The easiest way to simply create a file without truncating it in case it exists is:

open('my_file.txt', 'a').close()

https://docs.python.org/3/library/os.path.html


https://pyformat.info/

https://www.programiz.com/python-programming/methods/string/format


https://docs.python.org/3/faq/programming.html#how-do-i-write-a-function-with-output-parameters-call-by-reference


https://stackoverflow.com/questions/8270092/remove-all-whitespace-in-a-string-in-python


https://stackoverflow.com/questions/13033278/image-size-python-opencv/23207185

json
----
+ https://stackabuse.com/reading-and-writing-json-to-a-file-in-python/
+ https://developer.rhino3d.com/guides/rhinopython/python-xml-json/
+ https://realpython.com/python-json/
  - any file-like object can be passed to the second argument, even if it isn't an actual file. A good example of this would be a socket, which can be opened, closed, and written to much like a file. With JSON being popular throughout the web, this is another use-case you may encounter.
+ Serializing class instance to JSON
  - https://stackoverflow.com/questions/10252010/serializing-class-instance-to-json
  

Q & A
-----------

+ Pass a list of string from command line
  - https://stackoverflow.com/questions/43786174/how-to-pass-and-parse-a-list-of-strings-from-command-line-with-argparse-argument?rq=1
```python
parser.add_argument('-n', '--names-list', nargs='+', default=[])
```

+ Python syntax to delete a folder
  - shutil.rmtree()
  - https://stackoverflow.com/questions/6996603/delete-a-file-or-folder

```python
#!/usr/bin/python
import os
import sys
import shutil

# Get directory name
mydir= raw_input("Enter directory name: ")

## Try to remove tree; if failed show an error using try...except on screen
try:
    shutil.rmtree(mydir)
except OSError as e:
    print ("Error: %s - %s." % (e.filename, e.strerror))
```




