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

```bash
#!/bin/bash
LOCALPATH=<path1>
REMOTEPATH=<path2>
sshfs -o allow_other,default_permissions account@server:$REMOTEPATH $LOCALPATH
```

```
$ apt-get install sshfs
$ sshfs remoteuser@remotehost:/remote/path /local/mountpoint
And that will let you edit your remote files as if they were on your local file system.
```
+ https://superuser.com/questions/964821/translate-permissions-with-as-sshfs-remote-mount

```bash
sudo sshfs -o allow_other,default_permissions X:/ /mntX
# fusermount: option allow_other only allowed if 'user_allow_other' is set in /etc/fuse.conf
```
```bash
# /etc/fuse.conf - Configuration file for Filesystem in Userspace (FUSE)

# Set the maximum number of FUSE mounts allowed to non-root users.
# The default is 1000.
#mount_max = 1000

# Allow non-root users to specify the allow_other or allow_root mount options.
user_allow_other
```

I had tried both allow_other (which gives every user read and write access to the root of the other machine, bad idea) and default_permissions (which does nothing) alone. Turns out that if you combine them then it respects the permissions. Be sure that usernames are the same across machines though or you might allow someone to write into the home directory of another machine of an account he or she doesn't own.


To make it even smoother you can add a line to /etc/fstab

+ file or folder comparison 
  - https://www.tecmint.com/compare-find-difference-between-two-directories-in-linux/

+ nohup
  - https://unix.stackexchange.com/questions/137759/why-use-nohup-rather-than-exec
  - https://unix.stackexchange.com/questions/45913/is-there-a-way-to-redirect-nohup-output-to-a-log-file-other-than-nohup-out
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
rsync -r --info=progress2 {your folder} {destination}

```

+ best image viwer 
  - https://itsfoss.com/image-viewers-linux/

### windows drive on linux
+ https://www.thomas-krenn.com/en/wiki/Mounting_a_Windows_Share_in_Linux
```bash
#example 
admin@adminpc-ubuntu:~$ sudo mount -t cifs //192.168.1.100/freigabe /mnt -o user=testuser
```

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

+ create a branch 
  - https://confluence.atlassian.com/bitbucket/branching-a-repository-223217999.html

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
  

