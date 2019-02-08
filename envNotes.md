### cmd
#### How to count lines in a document?
```
Use wc:
wc -l <filename>
```
This will output the number of lines in <filename>:
```
$ wc -l /dir/file.txt
3272485 /dir/file.txt
```
####  Recursively counting files in a directory
```
$ find DIR_NAME -type f | wc -l
//or at the DIR
$ lc -l | wc -l
```
