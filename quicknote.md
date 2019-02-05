### python

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
