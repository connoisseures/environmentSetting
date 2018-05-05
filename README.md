## Overview

This is the note for environment setting 

## Dependencies

You need a [anaconda](https://www.continuum.io/downloads) or [miniconda](https://conda.io/miniconda.html) to use the environment setting.

```python
# Use TensorFlow without GPU
conda env create -f environments.yml 

# Use TensorFlow with GPU
conda env create -f environment-gpu.yml
```

# To activate this environment, use:
source activate env_name

# To deactivate this environment, use:
source deactivate env_name
```


Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.


