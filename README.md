# CNNs_HAR_and_HR
This repository is an artifact for the paper "CNNs for Heart Rate Estimation and Human Activity Recognition in Wrist Worn Sensing Applications" submitted to the WristSense workshop as part of PerCom 2020.

The code has been supplied as Jupyter Notebooks and set up to run in Google Colaboratory. The dataset used is open source and freely available. The data was collected by [D. Jarchi and A. Casson (2017)](https://www.mdpi.com/2306-5729/2/1/1) and downloaded from [PhysioNet](https://physionet.org/content/wrist/1.0.0/).

## Running CNNR - Heart Rate Error
```CNN_Recurrent.ipynb```

When you call the RCNN function you can specify Conv-Pooling params which will affect the outcome of your heart rate error. \\
Your choice of conv-pooling ```filter (cv_k)``` and ```stride (cv_k)``` sizes will be dependent on  ```seq_len``` that changes with you downsampling factors ```dwns_factor```.  You can set these in the ```call_RCNN()``` function\\

The results will be written to a json file in format: \\
[```batch_size```, ```exercise```, ```downsampled frequency```, ```heart rate error```]

## Running HAR - Human Activity Recognition
```HAR.ipynb```

### Preparing Data
This notebook provides functions to segment, plot and save the individual images used in the Tranfer Learning section of this experiment. 

### Transfer Learning

After plotting and formatting of your PPG data you can run the Transfer Learning script that was taken from [Tensorflow for Poets](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0). \\

There is now a simplified notebook available on Google Colaboratory [here](https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/images/transfer_learning_with_hub.ipynb). \\

***Note***: We used the transfer learning script from Tensorflow 1.0, which is now deprecated. The results from the new scripts using Tensorflow 2.0 may vary slightly. \\
All default parameter values bar one were kept the same. We changed the number of training iterations from a default value of 10,000 to 4,000, this helped minimise overfitting through sufficient convergence of the loss function
