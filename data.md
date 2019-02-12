# Source of Data Set 

1. Caltech Camera Traps on Animals (CCTA)
- https://beerys.github.io/CaltechCameraTraps/
- image count : 57865
2. Oxford Pets (OxPet)
- http://www.robots.ox.ac.uk/~vgg/data/pets/
- images count : 7394
3. in-house video data set (inVideo)
- review of video content 
    - noObjectVideos.log
    - VideoForAutomaticAnotation.log


```
project
│   README.md
│   file001.txt    
│
└───folder1
│   │   file011.txt
│   │   file012.txt
│   │
│   └───subfolder1
│       │   file111.txt
│       │   file112.txt
│       │   ...
│   
└───folder2
    │   file021.txt
    │   file022.txt
```

# Data Placement 

The data set is placed in the DATAPOOL, which is a repository to park data. 
Within DATAPOOL, we have the following sub-directory. 

```
DATAPOOL
│   README.md
│
└───dataset_ssd_face
|   |
│   └───ssd_train_v2_wi_faces
|   │            
|   └───ssd_test_v7_s
│   
└───fp_selection
|   |
│   └───<YearDate>_<hourMin> (a fold is created when FP data is selected)
|       │   CCTA.tar.gz
|       │   Oxford-iiit_pet.tar.gz
|       │   video_crops.tar.gz
│   
└───fp_source (sources of collected false positive data set)
    │   CaltechCameraTraps
    │   Oxford-iiit_pet
    |   video_crops
    |   raw


DATAPOOL=/mnt/data-pcie1/zf.working/
```
