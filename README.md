## Overview

This is the note for environment setting 

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
```


Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.


## Issue on Installation 
Error when installing TensorFlow 
(1) ImportError: /lib64/libc.so.6: version `GLIBC_2.XX' not found
https://github.com/tensorflow/tensorflow/issues/53

$ cd /tmp
$ wget http://launchpadlibrarian.net/137699828/libc6_2.17-0ubuntu5_amd64.deb
$ wget http://launchpadlibrarian.net/137699829/libc6-dev_2.17-0ubuntu5_amd64.deb
$ mkdir libc6_2.17
$ cd libc6_2.17
$ ar p libc6_2.17-0ubuntu5_amd64.deb data.tar.gz | tar zx
$ ar p libc6-dev_2.17-0ubuntu5_amd64.deb data.tar.gz | tar zx
$ cd -
$ //load python as the following
$ LD_LIBRARY_PATH=/tmp/libc6_2.17/lib/x86_64-linux-gnu/ /tmp/libc6_2.17/lib/x86_64-linux-gnu/ld-2.17.so bin/python 

Or prepare a script, py_tf:
LD_LIBRARY_PATH=/home/yourname/anaconda3/myLib/libc6_2.17/lib/x86_64-linux-gnu/ /home/yourname/anaconda3/myLib/libc6_2.17/lib/x86_64-linux-gnu/ld-2.17.so /home/yourname/anaconda3/envs/tf_keras/bin/python $1

$ py_tf cnn.py

