# Week 1
Explore different approaches to creating human animate avatars using Gaussian splatting.
List of the papers: https://docs.google.com/spreadsheets/d/1HZXw-ABPMRWfHruoicAGn2l48Ccqb2dGa16WicAbMFk/edit?usp=sharing

## Implemented Gaussian splatting base code for our video where a girl interacts with the objects in the Kitchen environment.

**Steps to implement**

Step 1: Convert images into point cloud from video to images.

    $ ffmpeg -i kitchen_girl.mp4 -qscale:v 1 -qmin 1 -vf fps=4 %04d.jpg

Step 2: Make data compatible with your model training

    $ python convert.py -s data/kitchen_env

Step 3: Train the model for your dataset

    $ python train.py -s data/kitchen_env
    
Step 4: Visualize the trained model

    $ ./SIBR_viewers/install/bin/SIBR_gaussianViewer_app -m /home/dr/Desktop/Gaurav/Research/BU/gaussian-splatting/output/kitchen_env

