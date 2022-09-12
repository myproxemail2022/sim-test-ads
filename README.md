This repository contains data for the submission ***Now You See Me: Exploiting Weakness in ObjectDetection for Testing Autonomous Driving Systems***

The data in this repository is organized as follows:
- Folder `RQ1_RQ2/` contains files representing each round of data and their corresponding visualizations.
    - `raw/` contains the JSON files representing each round of data. Meaning of important keys in each round:
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
    - `figures/` contains the figures visualizing some statistics of the raw data in `raw/` with the following subfolders. Each subfolder contains four files which represents the results from four different types of guidance, which are **random** (which has the fusion obstacle detection results and neuron coverage from both camera and LiDAR models), **camera-LiDAR fusion** neuron coverage guided  (which has the fusion obstacle detection results and neuron coverage from both camera and LiDAR models), **solo camera** neuron coverage guided  (which only has the obstacle detection results for camera and neuron coverage from both camera LiDAR model), **solo LiDAR** neuron coverage guided  (which only has the obstacle detection results for LiDAR and neuron coverage from LiDAR model).
        - `precision`: contains the average precision for each round in 300 rounds
        - `recall`: contains the average recall for each round in 300 rounds
        - `perception_rate`: contains the average perception rate for each obstacle type (vehicle vs. pedestrian) for each round in 300 rounds
        - `neuron_coverage`: contains the maximum neuron coverage from all frames for each round in all 300 rounds shown as the number of activated neurons divided by the maximum number of neurons
            - **random** and **camera-LiDAR fusion** shows the neuron coverage for the combination of both camera and LiDAR models
            - **solo camera** and **solo LiDAR** only has neuron coverage for the corresponding model
- Folder `RQ3/` contains the video recordings of the cases discussed in RQ3 in the paper. The analysis of which is in the submitted paper.
    - Figure 10: `collide_deer.mkv`
    - Figure 11: `collide_sidewalk.mkv`
    - Figure 12: `collide_pedestrian.mkv`
<!-- Generated simulation runs by SimsV
•Data  (coverage,  precision,  recall  perception  rate  etc.)  of simulation runs
•Recordings and analysis on the found problems of Apollo -->