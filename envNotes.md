Work Space
===

+ kill a process on GPU
```
$ nvidia-smi -q
# This gives a list of all the processes (and their PIDs) occupying GPU memory. I killed them one by one by using
$ kill -9 PID
```

+ How to concatenate string variables in Bash
  - https://stackoverflow.com/questions/4181703/how-to-concatenate-string-variables-in-bash
```
bla=hello
laber=kthx
echo "${bla}ohai${laber}bye"
```
+ open images on terminal 
  - https://unix.stackexchange.com/questions/35333/what-is-the-fastest-way-to-view-images-from-the-terminal
```
feh <image-name>
```

+ How to count lines in a document?
```
Use wc:
wc -l <filename>
```
This will output the number of lines in <filename>:
```
$ wc -l /dir/file.txt
3272485 /dir/file.txt
```
+ Recursively counting files in a directory
```
$ find DIR_NAME -type f | wc -l
//or at the DIR
$ lc -l | wc -l
```

+ remove filesystem over ssh 
  - https://stackoverflow.com/questions/2136127/how-to-use-gvim-to-edit-a-remote-file

```
$ apt-get install sshfs
$ sshfs remoteuser@remotehost:/remote/path /local/mountpoint
And that will let you edit your remote files as if they were on your local file system.
```
To make it even smoother you can add a line to /etc/fstab

+ file or folder comparison 
  - https://www.tecmint.com/compare-find-difference-between-two-directories-in-linux/

+ nohup
  - https://unix.stackexchange.com/questions/137759/why-use-nohup-rather-than-exec

+ gvim
 - https://askubuntu.com/questions/334219/gvim-produces-error-when-hitting-the-close-window

git
---
+ bitbucket
  - https://stackoverflow.com/questions/25620662/how-to-delete-a-folder-from-bitbucket-repository
+ http://rogerdudler.github.io/git-guide/
