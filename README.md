## Drone-Action-Recognition Dataset

The data set contains a total of 240 clips with 66919 images. The number of
actors in the dataset is 10 and they performed each action 5 to 10 times.
times. All videos are provided with a resolution of 1920×1080 and 25 fps. The average
of each action is 11.15 seconds.
All videos were annotated with subject ID, action class, and area
bounding box. Subject The subject IDs are S1 through S10 for all ten actors. In addition to the
annotations of the bounding box, the estimates of the body joints cal-
culated using the OpenPose pose estimator .



## Pose-Based TSN & CNN (P-T-CNN)




It is obvious that the human pose, plays a very important role in the recognition
dynamic recognition of gestures. In this work we have used the position of the joints of the
to extract patches that will be used for the computation of the descriptor vectors.
descriptors.
The feature vectors of the P-T-CNN were created from motion and appearance features
and appearance features centered on the person and extracted from the positions of the
body joints. which is based on the two-stream CNN architecture. For this work,
we used the same principle of P-CNN but with some modifications. This modification
modification allows us to better extract the temporal descriptor vector with the help of the
TSN and extract the spatial descriptor vector with VGGF . The extraction process
of the P-T-CNN features is illustrated in Figure 2.1. The main modules of the
process


## bibliothèque to install

Python = 3.8

PyTorch 

Torchvision >= 0.7

cython

pyyaml

easydict

opencv-python

matplotlib

numpy

scipy

tensorboardX


Requires pip >= 9..

mxnet

### for mxnet in windows
pip install --upgrade mxnet
### for pytorch in windows
pip install torch==1.6.0+cpu torchvision==0.7.0+cpu -f https://download.pytorch.org/whl/torch_stable.html

pip install --upgrade gluoncv


## workflow

- extract frames from each video to obtain the RGB images
- apply calculation_of_optical_flow.ipynb on RGB frames to get OP frames
- extraction of the patches for the 2 types of images (OP, RGB) using Extraction_Des_Patches.ipynb
- compute image descriptor vectors with the file Aggregation_Features_CNN.ipynb
- use the  modeling file to create your model 




