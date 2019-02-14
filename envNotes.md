Work Space
===

### How to count lines in a document?
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

## remove filesystem over ssh 
- https://stackoverflow.com/questions/2136127/how-to-use-gvim-to-edit-a-remote-file

```
$ apt-get install sshfs
$ sshfs remoteuser@remotehost:/remote/path /local/mountpoint
And that will let you edit your remote files as if they were on your local file system.
```
To make it even smoother you can add a line to /etc/fstab


