# YUTO: A Large Scale Aerial LiDAR Data Set for Semantic Segmentation
This is the official repository of the **YUTO Semantic** dataset.


### Overview
<p align="center"> <img src="imgs/visualization.png" width="100%"> </p>

YUTO Semantic is a multi-mission large-scale aerial LiDAR dataset specifically designed for 3D point cloud semantic segmentation. The dataset comprises approximately 738 million points, covering an area of 9.46 square kilometers of York University Campus in Toronto, Ontario Canada.  Each point in the dataset is annotated with one of nine semantic classes.

<p align="center"> <img src="imgs/YUTO release date.PNG" width="100%"> </p>

At this time, we are releasing one mission, Galaxy 2018 Fall. We are planning to release the rest of the missions. Details of the dataset can be found in ISPRS GSW 2023.

### Available Classes
* Ground: This class includes unpaved surfaces, grass, and natural terrain.
* Vegetation: This class encompasses trees, bushes, and other forms of vegetation.
* Building: This class represents both commercial and residential buildings.
* Water: This class includes bodies of water such as lakes and rivers.
* Car: This class includes all types of vehicles except for commercial trucks.
* Truck: This class specifically represents commercial trucks.
* Traffic Road: This class corresponds to vehicle roads.
* Sidewalk: This class represents pedestrian walkways.
* Parking: This class represents parking lots.

### Available Attributes
* x, y, z: The position coordinates of each point recorded in UTM zone 17N using the NAD83 horizontal datum.
* Intensity: The normalized LiDAR intensity value of each point, ranging from 0 to 255.
* Number of Return: The number of times the laser pulse was reflected back.
* GPS time: The GPS time of each point, providing temporal information about the data acquisition.
* Scan Angle: The scan angle of each point, indicating the angle at which the laser beam hit the target.
* Class: The label assigned to each point, representing the semantic class or category of the object or surface the point belongs to.

### Test Split
The results are based on the following test split.
<details> <summary><strong>self.test_file_name = [
    "618175.81_4846250.00__618775.81_4846850.00",
    "618775.81_4844450.00__619375.81_4845050.00",
    "618175.81_4846850.00__618775.81_4847450.00",
    "618175.81_4848650.00__618775.81_4849250.00",
    "618175.81_4847450.00__618775.81_4848050.00",
    "618775.81_4845050.00__619375.81_4845650.00",
    "618175.81_4848050.00__618775.81_4848650.00",
    "618775.81_4845650.00__619375.81_4846250.00",
    "618775.81_4846250.00__619375.81_4846850.00"
]</strong></summary>

### Semantic Segmentation Results
New results will be updated.

| Method                             | OA    | mIoU  | ground | vegetation | building | water | car   | truck | traffic road | sidewalk | parking |
|------------------------------------|-------|-------|--------|-----------|----------|-------|-------|-------|--------------|----------|---------|
| PointNet (Qi et al., 2017)         |  --   | 33.22 | 74.50  | 76.80     | 63.30    | 0.00  | 39.94 | 0.00  | 15.10        | 0.00     | 29.80   |
| PointNet++ (Qi et al., 2017)       |  --   | 26.16 | 68.10  | 66.70     | 31.80    | 0.00  | 14.10 | 0.00  | 26.00        | 2.50     | 26.20   |
| SPG (Landrieu et al., 2018)        |  --   | 36.68 | 79.31  | 97.92     | 0.00     | 57.37 | 0.00  | 36.92 | 0.39         | 39.51    | 0.00    |
| SFL-Net (Li et al., 2023)          |  --   | 51.05 | 80.91  | 94.10     | 88.33    | 0.00  | 74.47 | 0.00  | 53.71        | 23.08    | 44.81   |
| RandLA (Hu et al., 2020)           | 84.19 | 58.37 | 80.61  | 94.44     | 95.39    | 3.34  | 74.59 | 13.87 | 78.10        | 23.43    | 61.56   |
| KPConv (Thomas et al., 2019)       | 85.22 | 56.14 | 86.94  | 96.25     | 94.01    | 0.00  | 84.02 | 0.00  | 79.93        | 3.26     | 60.83   |
| EyeNet (Yoo et al., 2023)          | 87.41 | 63.44 | 86.26  | 95.94     | 96.78    | 13.61 | 83.02 | 14.26 | 84.65        | 31.08    | 65.34   |



### Downloads
- [YUTO Semantic](https://huggingface.co/datasets/ausmlab/yuto-semantic)


### Citation
If you find our work useful in your research, please consider citing:
```
      @article{yoo2023yuto,
        title={Yuto Semantic: a Large Scale Aerial LIDAR Dataset for Semantic Segmentation},
        author={Yoo, S and Ko, C and Sohn, G and Lee, H},
        journal={The International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences},
        volume={48},
        pages={209--215},
        year={2023},
        publisher={Copernicus GmbH}
      }
```

### Acknowledgements
This data set is collected with Teledyne Optech's Galaxy LiDAR.
