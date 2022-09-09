This repository contains data for the submission ***Now You See Me: Exploiting Weakness in ObjectDetection for Testing Autonomous Driving Systems***

The data in this repository is organized as follows:
- Folder **RQ1_RQ2** contains the JSON files representing each round of data. Meaning of important keys in each round:
    - PRECISION: precision as shown in the submitted paper
    - RECALL: recall as shown in the submitted paper
    - SIM: Data received from Apollo perception
        - perception_rate: perception rate for each obstacle as shown in the submitted paper
        - frames: The frame-by-frame details of the ego vehicle and obstacles, which contain the following keys
            - ego: details of ego
            - gt: ground truth for Fusion (of camera and LiDAR) or LiDAR only
            - gt_cam: ground truth for camera sensors only (only available for camera neuron coverage guided)
            - fusion: actual obstacles detected by Apollo using either fusion (of camera and LiDAR) or LiDAR only (in case of LiDAR neuron coverage guided)
    - LIDAR_COVERAGE: neuron coverage of LiDAR model
    - CAMERA_COVERAGE: neuron coverage of camera model
- Folder **RQ3** contains the video recordings of the cases discussed in RQ3. The analysis of which is in the submitted paper.
    - Figure 10: collide_deer.mkv
    - Figure 11: collide_sidewalk.mkv
    - Figure 12: collide_pedestrian.mkv
<!-- Generated simulation runs by SimsV
•Data  (coverage,  precision,  recall  perception  rate  etc.)  of simulation runs
•Recordings and analysis on the found problems of Apollo -->