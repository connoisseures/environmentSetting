Getting start  
---

## Working Env

### Virtual env
+ Install virtualenv if needed
+ Create working env
    - Set a virtual env
    ```
    virtualenv --system-site-packages -p python3 YOUR_ENV_NAME
    # or
    virtualenv -p python3 YOUR_ENV_NAME
    ```
    - or you can use the script I provided
    ```
    $ bash 01a_virtualEnv.sh YOUR_ENV_NAME
    ```
    - Activate a virtual env
    ```
    $ source PATH_TO_YOUR_ENV/bin/activate
    ```
    - deactivate env
    ```
    $ deactivate
    ```
    - https://virtualenv.pypa.io/en/latest/userguide/

### Tensorflow - GPU
+ Useful command
```
$ nvidia-smi
    https://developer.nvidia.com/nvidia-system-management-interface
$ nvidia-smi -q -g 0 -d UTILIZATION 
$ gpustat -cp
```
+ https://unix.stackexchange.com/questions/38560/gpu-usage-monitoring-cuda
```
watch -n 0.5 nvidia-smi
```
+ https://stackoverflow.com/questions/8223811/top-command-for-gpus-using-cuda

+ Make sure cuda installed on the server and set the ENV path for cuda
    - If the server has a symbolic link for cuda   
    ```
    $ export PATH=/usr/local/cuda/bin:${PATH:+:${PATH}}
    $ export LD_LIBRARY_PATH=/usr/local/cuda/lib64\
    $ {LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
    ```
    - You can also define the path of the cuda(Ex: cuda-9.2) installed on the server  
    ```
    $ export PATH=/usr/local/cuda-9.2/bin:${PATH:+:${PATH}}
    $ export LD_LIBRARY_PATH=/usr/local/cuda-9.2/lib64{LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
    ```
    - Or you can use the script I provided
    ```
    $ source 02a_setCudaPath.sh
    ```
    - Verfy Installation of cuda 
    ```
    $ cat /proc/driver/nvidia/version
    $ nvcc -V
    $ cp -r /usr/local/cuda-9.2/samples YOUR_SAMPLE_PATH
    $ make
    $ cd YOUR_SAMPLE_PATH/bin/x86_64/linux/release
    $ ./deviceQuer  
    ```
    - https://medium.com/@zhanwenchen/install-cuda-9-2-and-cudnn-7-1-for-tensorflow-pytorch-gpu-on-ubuntu-16-04-1822ab4b2421
    - http://developer.download.nvidia.com/compute/cuda/9.2/Prod/docs/sidebar/CUDA_Installation_Guide_Linux.pdf

### usefull :
+ pip show tensorflow 
    ```
    pip uninstall tensorflow
    Install tensorflow - gpu
    ```
+ https://www.tensorflow.org/install/pip
    ```
    $ virtualenv --system-site-packages -p python3 ./venv
    $ source ./venv/bin/activate  # sh, bash, ksh, or zsh
    $ pip install --upgrade pip    
    $ pip list  # show packages installed within the virtual environment
    $ pip3 install tensorflow-gpu==1.8 # if you plan to install TF version 1.8
    ```
+ Please make sure that the cuda version complies with the version of the official Tensorflow. Or you will suffer from the common issue that “ libcublas.so.9.0” is not found.  
+ common issue during installing tensorflow-gpu
    - ImportError: libcublas.so.9.0: cannot open shared object file: No such file or directory
        - The issure results from the cuda version doesn’t match with the offiical tensoflow pacakge. 
        Here is the official build configuration. 
        https://www.tensorflow.org/install/source#tested_source_configurations
        solution: 
        Build the tensorflow from source and package it as a pip package. use pip package to install.  
        https://gist.github.com/ljaraque/d18d3dd198dcff3bc40cbe91889564d0
        Ex: we provide a pip package of TF1.9+cuda9.2 on GPUS03
        ```
        $ pip install /tmp/tensorflow_pkg/tensorflow-1.9.0-cp35-cp35m-linux_x86_64.whl
        ```
        
+ verfy tensorflow 
```
$ python -c "import tensorflow as tf; tf.enable_eager_execution(); print(tf.reduce_sum(tf.random_normal([1000, 1000])))"
```
Or you can use the script I provided
```
$ bash 03b_verfyTF1.9.sh
```

## Tensorflow ODAPI

https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md
Dependencies 
```bash
$ pip install --user Cython
$ pip install --user contextlib2
$ pip install --user pillow
$ pip install --user lxml
$ pip install --user jupyter
$ pip install --user matplotlib
```
You can start by loading official version to make sure you already have setup the prerequisite for Tensorflow ODAPI
+ clone tensorflow model (official version)
    - https://github.com/tensorflow/models
+ coco api installation (Our inhouse Tensorflow ODAPI already includes it.)
    - https://github.com/cocodataset/cocoapi.git

Download the cocoapi and copy the pycocotools subfolder to the tensorflow/models/research directory if you are interested in using COCO evaluation metrics. 

Set PYTHONPATH
move to the path you place “Tensorflow ODAPI” 
```bash
# From tensorflow/models/research/
$ export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
Or you can use the script I provided
$ source 04c_setPYTHONPATH.sh
verify the installation
$ cd PATH_TO_TFODAPI_RESEARCH 
$ python object_detection/builders/model_builder_test.py
```
Starting a Project
+ define your own file hierarchy
    - my example: 
1. data
2. log
3. models 
4. myEnv
5. workspace  
6. source a virtual environment 
7. set PATH
8. set cuda path 
9. set pythonpath
10. use bach: $ source 00_setPATH.sh


### Tutorial on Tensorflow-OPAPI
+ prepare TFRecord 
    - https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/preparing_inputs.md
+ prepare data set 
+ prepare pbtxt file 
    - generate TFRecord
```bash
$ python $TFODAPIPATH/object_detection/dataset_tools/create_pet_tf_record.py --label_map_path=`pwd`/pet_label_map.pbtxt --data_dir=`pwd` --output_dir=`pwd`
($TFODAPIPATH: the path where tensorflow-odapi is located)
```

### issue 
+ "gcc: error: pycocotools/_mask.c: No such file" issue #168
    - https://github.com/cocodataset/cocoapi/issues/168
    ```bash
    Because my machine is the first to install "cocoapi", so I meet the same problems.
    pip install Cython
    pip install pycocotools
    make
    ```






