# CNNs_HAR_and_HR
This repository is an artifact for the paper "CNNs for Heart Rate Estimation and Human Activity Recognition in Wrist Worn Sensing Applications" submitted to the WristSense workshop as part of PerCom 2020.

The code has been supplied as Jupyter Notebooks and designed to run in Google Colaboratory. The dataset used is open source and freely available. The data was collected by [D. Jarchi and A. Casson (2017)](https://www.mdpi.com/2306-5729/2/1/1) and downloaded from [PhysioNet](https://physionet.org/content/wrist/1.0.0/).

You should execute the repo in the following order:

```
1.   Create a directory in Google Drive named 'WristSense'
2.   Clone this GitHub repository into 'WristSense'
3.   Run the notebook Download_Data.ipynb
4.   Run the notebook CNN_Recurrent.ipynb
5.   Run the notebook HAR_Data.ipynb
6.   Run the notebook Transfer_Learning_HAR.ipynb

```

## Downloading the Data
```Download_Data.ipynb```

This notebook will download the data necessary to complete the experiments below. It will also create some directories to store your data and results


## Running CNNR - Heart Rate Error
```CNN_Recurrent.ipynb```

When you call the RCNN function you can specify Conv-Pooling params which will affect the outcome of your heart rate error.
Your choice of conv-pooling ```filter (cv_k)``` and ```stride (cv_k)``` sizes will be dependent on  ```seq_len``` that changes with you downsampling factors ```dwns_factor```.  You can set these in the ```call_RCNN()``` function.

The results will be written to a json file in format:
[```batch_size```, ```exercise```, ```downsampled frequency```, ```heart rate error```]

## Running HAR - Human Activity Recognition

### Preparing Data
```HAR_Data.ipynb```
This notebook provides functions to segment, plot and save the individual images used in the Tranfer Learning section of this experiment. 

### Transfer Learning
```Transfer_Learning_HAR.ipynb```

This notebook computes Transfer Learning on a Inception-v3 model pretrained on ImageNet.


## Citation

If you find this repo helpful in any way please cite our forthcoming paper:

    @inproceedings{Brophy2020,
    author = {Brophy, Eoin and Muehlhausen, Willie and Smeaton, Alan F. and Ward, Tomas},
    title     = {CNNs for Heart Rate Estimation and Human Activity Recognition in Wrist Worn Sensing Applications},
    booktitle = {2020 {IEEE} International Conference on Pervasive Computing and Communications,
               PerCom, Austin, Texas, March 23-27, 2020},
    publisher = {{IEEE}},
    year      = {2020}
    }

No longer necessary -> You should include the following command at the top of your `.bib` file to cite a forthcoming paper: `@preamble{ " \newcommand{\noop}[1]{} " }` 
