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
+ open pdf
  - xdg-open file2open.xxx 
  - https://askubuntu.com/questions/43264/how-to-open-a-pdf-file-from-terminal

+ how to log screen
  - https://askubuntu.com/questions/161935/how-do-i-log-all-input-and-output-in-a-terminal-session

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
### sshfs
+ https://linuxize.com/post/how-to-use-sshfs-to-mount-remote-directories-over-ssh/
+ https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh
+ remote filesystem over ssh 
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


+ How to forward X over SSH to run graphics applications remotely?
```
belden@skretting:~$ ssh -X blyman@the-server
```

+ remote restart 
```
sudo service lightdm restart
```

+ scp
  - http://www.hypexr.org/linux_scp_help.php

+ rsync
  - https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories-on-a-vps
  - https://linux.die.net/man/1/rsync
```
rsync -rl --info=progress2 SRC_FOLDER DST_FOLDER
rsync -rL --info=progress2 SRC_FOLDER/ DST_FOLDER
rsync -avhP dir1/ dir2
```

+ best image viwer 
  - https://itsfoss.com/image-viewers-linux/


mac
---
+ https://stackoverflow.com/questions/2056137/how-to-run-mvim-macvim-from-terminal
```
alias gvim='/Applications/MacVim.app/Contents/MacOS/Vim -g'
```


git
---
+ bitbucket
  - https://stackoverflow.com/questions/25620662/how-to-delete-a-folder-from-bitbucket-repository
+ http://rogerdudler.github.io/git-guide/
+ https://blog.techbridge.cc/2018/01/17/learning-programming-and-coding-with-python-git-and-github-tutorial/
+ http://gitqwerty777.github.io/git-commands/
+ https://medium.com/@pk60905/git-%E5%B7%A5%E7%A8%8B%E5%B8%AB%E7%9A%84%E6%99%82%E5%85%89%E6%A9%9F-676ecb07dca3
+ working directory, staging area, and repository
  - git show
  - git log
  - git rm --cached <file>
+ https://stackoverflow.com/questions/15745045/how-do-i-resolve-git-saying-commit-your-changes-or-stash-them-before-you-can-me
+ https://stackoverflow.com/questions/215718/reset-or-revert-a-specific-file-to-a-specific-revision-using-git
  If you want to revert to the commit before c5f567, append ~1 (works with any number):
```
git checkout c5f567~1 -- file1/to/restore file2/to/restore
```
+ checkout a branch 
  - https://confluence.atlassian.com/bitbucket/checkout-a-branch-into-a-local-repository-313466957.html  
  
bash
---
+ sleep
  - https://www.cyberciti.biz/faq/linux-unix-sleep-bash-scripting/
+ while 
  - https://linuxize.com/post/bash-while-loop/
  - https://www.cyberciti.biz/faq/bash-while-loop/
  - http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html
+ touch
  - https://stackoverflow.com/questions/9381463/how-to-create-a-file-in-linux-from-terminal-window
+ variable
  - https://www.tldp.org/LDP/abs/html/parameter-substitution.html
+ missing ]
  - https://stackoverflow.com/questions/15993062/bash-scripting-missing
  

