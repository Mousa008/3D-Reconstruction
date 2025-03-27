# 3D-Reconstruction
3D Reconstruction

**Overview**
**The pipeline performs the following steps:**

Load images from a specified folder.

Undistort images using pre-calibrated camera intrinsics.

Extract features using the SIFT algorithm.

Match features between consecutive image pairs.

Estimate motion using the Essential Matrix and recover relative camera pose (R, t).

Triangulate 3D points from matched keypoints.

Visualize the sparse 3D point cloud.

**Requirements**

Python 3.x

OpenCV (opencv-python)

NumPy

Matplotlib


**Input**

A folder of images (at least 2) of the same object or scene from different viewpoints.

Camera intrinsics and distortion coefficients (from calibration).

**Camera Parameters**
    # CAMERA CALIBRATION (intrinsic matrix)
    # Taken from your camera_matrix data
    K = np.array([
        [3893.40418,       0.0,    2113.97597],
        [      0.0,   4082.33222,    106.97093],
        [      0.0,         0.0,         1.0   ]
    ])

Distortion coefficients from camera_info
dist_coeffs = np.array([-0.155459, 0.066577, -0.050429, 0.010197, 0.000000])

**Running the Code**
python sfm_pipeline.py

Make sure to update the image_folder path in the script:
image_folder = "/path/to/your/images"

**Output**
3D point cloud plotted using Matplotlib.

Console output shows:

Number of matches

Inlier statistics

Number of triangulated points


**Limitations**

Sparse reconstruction only (no dense depth or textures).

No global bundle adjustment or loop closure.

Depth can be noisy without refinement.


Created by Mohamed Mohamed
Email: K24113059@kcl.ac.uk


