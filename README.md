# Converts panoptic nuScenes into SemanticKITTI-compatible format.

First you have to download the [panoptic nuScenes](https://nuscenes.org/nuscenes) dataset.

Script usage: 
```
python3 nuscenes2kitti.py --nuscenes_dir <nuscenes_directory> --output_dir <output_directory>
```
options: 

`--normalize_remission` set remission values to range `[0,1]`.

`--mini` compute only for the mini set of scenes.

`--save_images` save frontal image for each point cloud

This will create a directory for each scene in `<output_directory>` with the same structure as SemanticKITTI containing:

```
output_directory
└── scene_id
    ├── calib.txt           # dummy file containing just identity transforms
    ├── files_mapping.txt   # original filenames
    ├── labels              # directory containing the panoptic labels
    ├── lidar_tokens.txt    # token for each point cloud
    ├── poses.txt           # pose for each laserscan
    └── velodyne            # directory containing the point clouds
```

## Config file
We provide the `semantic-nuscenes.yaml` file, which follows same structure as `semantic-kitti.yaml` and contains the labels, color_map, learning_map and splits.


# License
Copyright 2023, Rodrigo Marcuzzi, Cyrill Stachniss, Photogrammetry and Robotics Lab, University of Bonn.

This project is free software made available under the MIT License. For details see the LICENSE file
