# Cardiac_image_analysis

## Requirements
The code is tested on windows 10 with the following components:

### Software

> Python 2.7
> Keras 2.0.2 using TensorFlow GPU 1.0.1 backend
> CUDA 8.0 with CuDNN 5.1
> OpenCV 3.1
> h5py 2.7
> NumPy 1.11
> PyDicom 0.9.9
> Scikit-Image 0.13

### Datasets

> [Sunnybrook](http://smial.sri.utoronto.ca/LV_Challenge/Downloads.html)
> [LVSC](http://www.cardiacatlas.org/challenges/lv-segmentation-challenge/)
> [RVSC](http://www.litislab.fr/?projet=1rvsc)

## Usage
For training and evaluation, execute the following in the same directory where the datasets reside:

'''bash
# Train the FCN model on the Sunnybrook dataset
$ python train_sunnybrook.py <i/o> <gpu_id>

# Train the FCN model on the LVSC dataset
$ python train_lvsc.py <i/o/myo> <gpu_id>

# Train the FCN model on the RVSC dataset
$ python train_rvsc.py <i/o> <gpu_id>

'''

The flag `<i/o/myo>` indicates inner endocardium, outer epicardium, and myocardium contours, respectively, and `<gpu_id>` denotes the GPU device ID.

To create submission files for the test sets, execute the following:

'''
bash
# Create submission files for the Sunnybrook dataset
$ bash create_submission_sunnybrook.sh <gpu_id>

# Create submission files for the LVSC dataset
$ bash create_submission_lvsc.sh <gpu_id>

# Create submission files for the RVSC dataset
$ bash create_submission_rvsc.sh <gpu_id>
'''

Note: The LVSC and RVSC submission files must be submitted to the respective LVSC and RVSC challenge organizers for the official results evaluation. The Sunnybrook submission files can be evaluated using the MATLAB code provided as part of the data download.
