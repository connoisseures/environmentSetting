Python Quick Note
===============

Notes
-----------

### slice
+ https://docs.python.org/2.3/whatsnew/section-slices.html
+ https://stackoverflow.com/questions/31633635/what-is-the-meaning-of-inta-1-in-python
```python
s='abcd'
s[::2]
# 'ac'
s[::-1]
# 'dcba'
```
### covention 
+ file naming
  - https://stackoverflow.com/questions/2235173/file-name-path-name-base-name-naming-standard-for-pieces-of-a-path
+ underscore
  - https://shahriar.svbtle.com/underscores-in-python
  - https://docs.python.org/3.4/tutorial/classes.html#tut-private

### string
+ format
  - https://www.programiz.com/python-programming/methods/string/format
```python
# padding for float numbers
print("{:8.3f}".format(12.2346))
```
+ https://stackoverflow.com/questions/8266529/python-convert-string-to-list
```python
states.split(',')
```

### numpy
+ https://thatascience.com/learn-numpy/save-numpy-array-to-csv/

### class

+ Structs without constructors:
  - https://stackoverflow.com/questions/35988/c-like-structures-in-python  

```python
class Sample:
  name = ''
  average = 0.0
  values = None # list cannot be initialized here!
```
+ a static method of the class - which does not take an instance but applies to all instances of the class. To do that, you would add a @staticmethod decorator before the method.
  - https://www.programiz.com/python-programming/methods/built-in/classmethod
  - https://stackabuse.com/pythons-classmethod-and-staticmethod-explained/
  - https://www.programiz.com/python-programming/methods/built-in/staticmethod
+ how-to-call-a-method-from-another-method
  - https://stackoverflow.com/questions/1859959/python-static-methods-how-to-call-a-method-from-another-method

```python
class Test() :
    @staticmethod
    def static_method_to_call()
        pass

    @staticmethod
    def another_static_method() :
        Test.static_method_to_call()

    def a_method(self) :
    '''
    call a staticmethod within the class
    '''
        self.static_method_to_call()

    @classmethod
    def another_class_method(cls) :
        cls.static_method_to_call()
```
+ operator 
  - https://rszalski.github.io/magicmethods/
  - https://stackabuse.com/overloading-functions-and-operators-in-python/
  - http://hplgit.github.io/primer.html/doc/pub/class/._class-readable007.html

### multiprocessing 
+ https://timber.io/blog/multiprocessing-vs-multithreading-in-python-what-you-need-to-know/
  - Because of this, the usual problems associated with threading (such as data corruption and deadlocks) are no longer an issue. Since the processes don't share memory, they can't modify the same memory concurrently.
+ https://sebastianraschka.com/Articles/2014_multiprocessing.html#multi-threading-vs-multi-processing
+ https://www.journaldev.com/15631/python-multiprocessing-example
+ https://pymotw.com/2/multiprocessing/communication.html#process-pools
+ By default Pool creates a fixed number of worker processes and passes jobs to them until there are no more jobs. Setting the maxtasksperchild parameter tells the pool to restart a worker process after it has finished a few tasks. This can be used to avoid having long-running workers consume ever more system resources.
```python
pool = multiprocessing.Pool(processes=pool_size,
                                initializer=start_process,
                                maxtasksperchild=2,
                                )
```
### image
+ remember to close image
  - https://stackoverflow.com/questions/31751464/how-do-i-close-an-image-opened-in-pillow
+ image past
  - https://stackoverflow.com/questions/28407462/how-to-paste-an-image-onto-a-larger-image-using-pillow
  - https://note.nkmk.me/en/python-pillow-paste/
  - https://pillow.readthedocs.io/en/4.1.x/handbook/tutorial.html

### mongoDB
+ mongoDB example
  - https://stackoverflow.com/questions/11832556/writing-a-simple-mongodb-module-in-python

### yaml 
+ https://stackoverflow.com/questions/6866600/how-to-parse-read-a-yaml-file-into-a-python-object

### list
+ tutorial 
  - http://openbookproject.net/thinkcs/python/english3e/lists.html
```python
#add code here to figure out the number of 0's you need, naming the variable n.
listofzeros = [0] * n
```

+ asterisk meaning
  - https://stackoverflow.com/questions/400739/what-does-asterisk-mean-in-python
  - https://medium.com/understand-the-python/understanding-the-asterisk-of-python-8b9daaa4a558

### dict
+ defaultdict
  - https://docs.python.org/3/library/collections.html#collections.defaultdict
  - http://l4wisdom.com/python/python_collection_default.php
+ copy
  - https://stackoverflow.com/questions/2465921/how-to-copy-a-dictionary-and-only-edit-the-copy
+ key
  - https://thispointer.com/python-how-to-check-if-a-key-exists-in-dictionary/

#### deep copy
+ https://www.python-course.eu/deep_copy.php


#### bisect
+ https://github.com/python/cpython/blob/master/Lib/bisect.py

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

### import 
+ https://alex.dzyoba.com/blog/python-import/
+ https://stackabuse.com/python-modules-creating-importing-and-sharing/
  - Modules are units that store code and data, provide code-reuse to Python projects, and are also useful in partitioning the system's namespaces in self-contained packages. They're self-contained because you can only access a module's attributes after importing it. In fact, any Python file with a .py extension represents a module.
  - When a top-level Python file is run, its source code statements, and the statements within imported modules, are compiled in an intermediate format known as byte code, which is a platform-independent format. Byte code files of imported modules are stored with a .pyc extension in the same directory as the .py file for Python versions up to 3.2.

+ Using global variables between files
  - https://stackoverflow.com/questions/13034496/using-global-variables-between-files
+ https://stackoverflow.com/questions/4142151/how-to-import-the-class-within-the-same-directory-or-sub-directory

### decorator
+ https://www.datacamp.com/community/tutorials/decorators-python

### regular expression
+ https://en.wikibooks.org/wiki/Python_Programming/Regular_Expression
```python
print re.sub(r"(.*)\1", r"\1", "HeyHey")    # Prints "Hey"; backreference
print re.sub("EY", "ey", "HEy", flags=re.I) # Prints "Hey"; case-insensitive sub
print re.sub(r"(?i)EY", r"ey", "HEy")       # Prints "Hey"; case-insensitive sub
```
+ https://stackoverflow.com/questions/32698614/python-re-sub-only-replace-part-of-match?rq=1
+ https://regexone.com/references/python
```python
import re
regex = r"([a-zA-Z]+) (\d+)"
# This will reorder the string and print:
#   24 of June, 9 of August, 12 of Dec
print(re.sub(regex, r"\2 of \1", "June 24, August 9, Dec 12"))
#\1 = 1st ()
#\2 = 2nd ()
```

+ https://www.programiz.com/python-programming/regex
+ https://developers.google.com/edu/python/regular-expressions

random
---
+ https://docs.python.org/3/library/random.html


tips 
---
+ http://book.pythontips.com/en/latest/enumerate.html

plot
---
+ https://matplotlib.org/gallery/color/named_colors.html#sphx-glr-gallery-color-named-colors-py

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
  
plot
---
+ https://stackoverflow.com/questions/44709970/exporting-histogram-from-python-to-excel
```python
def plot_his(list_of_list, legend, xlabel, ylabel, the_title):
    color_def = ['orange', 'green', 'red', 'blue']
    the_color = color_def[0:len(list_of_list)]
    counts, bins, patches = plt.hist(list_of_list, color = the_color)
    plt.xlabel(xlabel)
    plt.ylabel(ylabel)
    plt.legend(legend)
    plt.title(the_title)
    plt.show()
    return counts, bins, patches
```

cv
---
+ https://kharshit.github.io/blog/2019/09/20/evaluation-metrics-for-object-detection-and-segmentation
+ https://github.com/open-mmlab/mmdetection/tree/master/mmdet/core/evaluation
+ https://tarangshah.com/blog/2018-01-27/what-is-map-understanding-the-statistic-of-choice-for-comparing-object-detection-models/
+ https://github.com/rafaelpadilla/Object-Detection-Metrics/blob/master/lib/Evaluator.py#L315
+ https://github.com/rafaelpadilla/Object-Detection-Metrics
+ https://github.com/Cartucho/mAP/blob/master/main.py
+ https://www.datacamp.com/community/tutorials/object-detection-guide
+ 


mAP
---
+ https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)
+ https://nlp.stanford.edu/IR-book/html/htmledition/evaluation-of-ranked-retrieval-results-1.html
+ https://tarangshah.com/blog/2018-01-27/what-is-map-understanding-the-statistic-of-choice-for-comparing-object-detection-models/
+ https://tarangshah.com/blog/2018-01-27/what-is-map-understanding-the-statistic-of-choice-for-comparing-object-detection-models/
+ https://medium.com/@timothycarlen/understanding-the-map-evaluation-metric-for-object-detection-a07fe6962cf3
+ 



Q & A
-----------

+ Pass a list of string from command line
  - https://stackoverflow.com/questions/43786174/how-to-pass-and-parse-a-list-of-strings-from-command-line-with-argparse-argument?rq=1
```python
parser.add_argument('-n', '--names-list', nargs='+', default=[])
```
+ check-whether-a-file-exists-without-exceptions
  - https://stackoverflow.com/questions/82831/how-do-i-check-whether-a-file-exists-without-exceptions

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

+ random numbers without duplicates 
  - https://stackoverflow.com/questions/9755538/how-do-i-create-a-list-of-random-numbers-without-duplicates



