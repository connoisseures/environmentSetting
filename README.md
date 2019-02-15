Overview
===
This is the note for environment setting 

### markdown
+ https://guides.github.com/features/mastering-markdown/
+ https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## Dependencies

You need a [anaconda](https://www.continuum.io/downloads) or [miniconda](https://conda.io/miniconda.html) to use the environment setting.

```python
# Use TensorFlow without GPU
conda env create -f environments.yml 

# Use TensorFlow with GPU
conda env create -f environment-gpu.yml

# To activate this environment, use:
source activate env_name

# To deactivate this environment, use:
source deactivate env_name

# To remove a env
conda env remove -n ENV_NAME
```


Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.


## Issue on Installation 
Error when installing TensorFlow

- For conda, keep in mind the scripts are written in BASH (not SH), so therefore you must execute the installer using bash:
http://astroconda.readthedocs.io/en/latest/getting_started.html

```
change to bash shell
$ bash
$ source activate env_name
```

- ImportError: /lib64/libc.so.6: version `GLIBC_2.XX' not found
https://github.com/tensorflow/tensorflow/issues/53

```
$ cd /tmp
$ wget http://launchpadlibrarian.net/137699828/libc6_2.17-0ubuntu5_amd64.deb
$ wget http://launchpadlibrarian.net/137699829/libc6-dev_2.17-0ubuntu5_amd64.deb
$ mkdir libc6_2.17
$ cd libc6_2.17
$ ar p libc6_2.17-0ubuntu5_amd64.deb data.tar.gz | tar zx
$ ar p libc6-dev_2.17-0ubuntu5_amd64.deb data.tar.gz | tar zx
$ cd -

load python as the following
$ LD_LIBRARY_PATH=/tmp/libc6_2.17/lib/x86_64-linux-gnu/ /tmp/libc6_2.17/lib/x86_64-linux-gnu/ld-2.17.so bin/python 

Or prepare a script, py_tf:
LD_LIBRARY_PATH=/home/yourname/anaconda3/myLib/libc6_2.17/lib/x86_64-linux-gnu/ /home/yourname/anaconda3/myLib/libc6_2.17/lib/x86_64-linux-gnu/ld-2.17.so /home/yourname/anaconda3/envs/tf_keras/bin/python $1

$ py_tf cnn.py
```


## quick note
### How to forward X over SSH to run graphics applications remotely?
```
belden@skretting:~$ ssh -X blyman@the-server
```

### scp
http://www.hypexr.org/linux_scp_help.php
