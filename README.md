# Deep Learning for Time Series Classification
This is the companion repository for [our paper](https://arxiv.org/abs/1809.04356) titled "Deep learning for time series classification: a review". 

![architecture resnet](https://github.com/hfawaz/dl-4-tsc/blob/master/png/resnet-archi.png)

## Data 
The data used in this project comes from two sources: 
* The [UCR archive](http://www.cs.ucr.edu/~eamonn/time_series_data/), which contains the 85 univariate time series datasets. 
* The [MTS archive](http://www.mustafabaydogan.com/files/viewcategory/20-data-sets.html), which contains the 13 multivariate time series datasets.

## Code 
The code is divided as follows: 
* The [main.py](https://github.com/hfawaz/dl-4-tsc/blob/master/main.py) python file contains the necessary code to run an experiement. 
* The [utils](https://github.com/hfawaz/dl-4-tsc/tree/master/utils) folder contains the necessary functions to read the datasets and visualize the plots.
* The [classifiers](https://github.com/hfawaz/dl-4-tsc/tree/master/classifiers) folder contains nine python files one for each deep neural network tested in our paper. 

To run a model on one dataset you should issue the following command: 
```
python3 main.py UCR_TS_Archive_2015 Coffee fcn _itr_8
```
which means we are launching the [fcn](https://github.com/hfawaz/dl-4-tsc/blob/master/classifiers/fcn.py) model on the univariate UCR archive for the Coffee dataset (see [constants.py](https://github.com/hfawaz/dl-4-tsc/blob/master/utils/constants.py) for a list of possible options).

## Prerequisites
All python packages needed are listed in [pip-requirements.txt](https://github.com/hfawaz/dl-4-tsc/blob/master/utils/pip-requirements.txt) file and can be installed simply using the pip command. 

* [numpy](http://www.numpy.org/)  
* [pandas](https://pandas.pydata.org/)  
* [sklearn](http://scikit-learn.org/stable/)  
* [scipy](https://www.scipy.org/)  
* [matplotlib](https://matplotlib.org/)  
* [tensorflow-gpu](https://www.tensorflow.org/)  
* [keras](https://keras.io/)  
* [h5py](http://docs.h5py.org/en/latest/build.html)
* [keras_contrib](https://www.github.com/keras-team/keras-contrib.git)

## Results
Our [results](https://github.com/hfawaz/dl-4-tsc/tree/master/results) showed that a deep residual network architecture performs best for the time series classification task. 

The following table contains the averaged accuracy over 10 runs of each implemented model on the UCR archive. 

| Datasets                       | MLP  | FCN  | ResNet | Encoder | MCNN | t-LeNet | MCDCNN | Time-CNN | TWIESN | 
|--------------------------------|------|------|--------|---------|------|---------|--------|----------|--------| 
| 50words                        | 0.71 | 0.65 | 0.74   | 0.73    | 0.22 | 0.13    | 0.58   | 0.62     | 0.48   | 
| Adiac                          | 0.4  | 0.84 | 0.83   | 0.48    | 0.02 | 0.02    | 0.61   | 0.38     | 0.43   | 
| ArrowHead                      | 0.78 | 0.85 | 0.84   | 0.79    | 0.34 | 0.3     | 0.69   | 0.73     | 0.71   | 
| Beef                           | 0.73 | 0.69 | 0.75   | 0.67    | 0.2  | 0.2     | 0.56   | 0.76     | 0.45   | 
| BeetleFly                      | 0.87 | 0.88 | 0.85   | 0.74    | 0.5  | 0.5     | 0.61   | 0.89     | 0.77   | 
| BirdChicken                    | 0.78 | 0.94 | 0.89   | 0.66    | 0.5  | 0.5     | 0.6    | 0.6      | 0.72   | 
| CBF                            | 0.87 | 0.99 | 0.99   | 0.95    | 0.33 | 0.33    | 0.82   | 0.96     | 0.9    | 
| Car                            | 0.77 | 0.9  | 0.93   | 0.74    | 0.24 | 0.32    | 0.74   | 0.78     | 0.77   | 
| ChlorineConcentration          | 0.8  | 0.82 | 0.84   | 0.57    | 0.53 | 0.53    | 0.64   | 0.6      | 0.55   | 
| CinCECGtorso                   | 0.84 | 0.83 | 0.83   | 0.9     | 0.38 | 0.25    | 0.73   | 0.75     | 0.28   | 
| Coffee                         | 1.0  | 1.0  | 1.0    | 0.98    | 0.51 | 0.54    | 0.98   | 1.0      | 0.98   | 
| Computers                      | 0.56 | 0.82 | 0.81   | 0.58    | 0.52 | 0.5     | 0.56   | 0.55     | 0.62   | 
| CricketX                       | 0.59 | 0.8  | 0.79   | 0.7     | 0.19 | 0.07    | 0.49   | 0.55     | 0.62   | 
| CricketY                       | 0.6  | 0.79 | 0.8    | 0.68    | 0.18 | 0.08    | 0.5    | 0.57     | 0.65   | 
| CricketZ                       | 0.62 | 0.81 | 0.81   | 0.7     | 0.18 | 0.06    | 0.48   | 0.49     | 0.64   | 
| DiatomSizeReduction            | 0.92 | 0.33 | 0.3    | 0.92    | 0.3  | 0.3     | 0.77   | 0.95     | 0.9    | 
| DistalPhalanxOutlineAgeGroup   | 0.8  | 0.81 | 0.8    | 0.86    | 0.62 | 0.64    | 0.82   | 0.85     | 0.8    | 
| DistalPhalanxOutlineCorrect    | 0.78 | 0.8  | 0.8    | 0.78    | 0.63 | 0.63    | 0.79   | 0.77     | 0.8    | 
| DistalPhalanxTW                | 0.72 | 0.77 | 0.76   | 0.79    | 0.44 | 0.53    | 0.78   | 0.78     | 0.73   | 
| ECG200                         | 0.92 | 0.89 | 0.88   | 0.93    | 0.64 | 0.64    | 0.84   | 0.81     | 0.88   | 
| ECG5000                        | 0.93 | 0.94 | 0.93   | 0.94    | 0.65 | 0.58    | 0.94   | 0.93     | 0.92   | 
| ECGFiveDays                    | 0.97 | 0.99 | 0.97   | 0.98    | 0.5  | 0.5     | 0.76   | 0.88     | 0.71   | 
| Earthquakes                    | 0.78 | 0.78 | 0.76   | 0.79    | 0.82 | 0.82    | 0.81   | 0.7      | 0.81   | 
| ElectricDevices                | 0.6  | 0.7  | 0.73   | 0.68    | 0.34 | 0.24    | 0.64   | 0.68     | 0.61   | 
| FISH                           | 0.85 | 0.95 | 0.98   | 0.86    | 0.14 | 0.13    | 0.76   | 0.85     | 0.88   | 
| FaceAll                        | 0.8  | 0.95 | 0.83   | 0.79    | 0.16 | 0.08    | 0.72   | 0.77     | 0.67   | 
| FaceFour                       | 0.84 | 0.93 | 0.95   | 0.83    | 0.27 | 0.3     | 0.71   | 0.91     | 0.81   | 
| FacesUCR                       | 0.83 | 0.95 | 0.96   | 0.87    | 0.15 | 0.14    | 0.76   | 0.87     | 0.65   | 
| FordA                          | 0.73 | 0.9  | 0.92   | 0.92    | 0.55 | 0.51    | 0.77   | 0.88     | 0.53   | 
| FordB                          | 0.61 | 0.88 | 0.91   | 0.89    | 0.51 | 0.51    | 0.54   | 0.81     | 0.5    | 
| GunPoint                       | 0.93 | 1.0  | 0.99   | 0.94    | 0.51 | 0.49    | 0.87   | 0.93     | 0.97   | 
| Ham                            | 0.69 | 0.72 | 0.76   | 0.72    | 0.52 | 0.51    | 0.72   | 0.71     | 0.75   | 
| HandOutlines                   | 0.83 | 0.76 | 0.86   | 0.84    | 0.64 | 0.64    | 0.84   | 0.84     | 0.7    | 
| Haptics                        | 0.43 | 0.48 | 0.52   | 0.43    | 0.21 | 0.21    | 0.39   | 0.37     | 0.37   | 
| Herring                        | 0.53 | 0.62 | 0.61   | 0.59    | 0.59 | 0.59    | 0.59   | 0.54     | 0.6    | 
| InlineSkate                    | 0.34 | 0.34 | 0.37   | 0.3     | 0.17 | 0.16    | 0.22   | 0.29     | 0.3    | 
| InsectWingbeatSound            | 0.61 | 0.39 | 0.51   | 0.64    | 0.16 | 0.09    | 0.59   | 0.58     | 0.44   | 
| ItalyPowerDemand               | 0.95 | 0.96 | 0.96   | 0.97    | 0.5  | 0.5     | 0.96   | 0.95     | 0.88   | 
| LargeKitchenAppliances         | 0.47 | 0.9  | 0.9    | 0.62    | 0.41 | 0.33    | 0.44   | 0.66     | 0.78   | 
| Lighting2                      | 0.67 | 0.74 | 0.77   | 0.69    | 0.56 | 0.54    | 0.62   | 0.64     | 0.68   | 
| Lighting7                      | 0.63 | 0.83 | 0.84   | 0.62    | 0.31 | 0.26    | 0.53   | 0.65     | 0.69   | 
| MALLAT                         | 0.92 | 0.97 | 0.97   | 0.87    | 0.17 | 0.12    | 0.9    | 0.92     | 0.55   | 
| Meat                           | 0.9  | 0.83 | 0.97   | 0.74    | 0.33 | 0.33    | 0.72   | 0.9      | 0.97   | 
| MedicalImages                  | 0.72 | 0.78 | 0.77   | 0.74    | 0.51 | 0.51    | 0.64   | 0.68     | 0.67   | 
| MiddlePhalanxOutlineAgeGroup   | 0.75 | 0.74 | 0.73   | 0.8     | 0.27 | 0.27    | 0.79   | 0.78     | 0.68   | 
| MiddlePhalanxOutlineCorrect    | 0.74 | 0.81 | 0.81   | 0.55    | 0.65 | 0.65    | 0.63   | 0.54     | 0.55   | 
| MiddlePhalanxTW                | 0.58 | 0.58 | 0.6    | 0.64    | 0.27 | 0.31    | 0.63   | 0.63     | 0.62   | 
| MoteStrain                     | 0.86 | 0.93 | 0.93   | 0.84    | 0.5  | 0.54    | 0.76   | 0.88     | 0.78   | 
| NonInvasiveFatalECGThorax1     | 0.92 | 0.96 | 0.94   | 0.92    | 0.16 | 0.03    | 0.91   | 0.86     | 0.47   | 
| NonInvasiveFatalECGThorax2     | 0.92 | 0.95 | 0.94   | 0.93    | 0.16 | 0.03    | 0.92   | 0.9      | 0.54   | 
| OSULeaf                        | 0.56 | 0.98 | 0.98   | 0.58    | 0.24 | 0.18    | 0.38   | 0.46     | 0.6    | 
| OliveOil                       | 0.67 | 0.75 | 0.83   | 0.4     | 0.39 | 0.38    | 0.39   | 0.4      | 0.82   | 
| PhalangesOutlinesCorrect       | 0.73 | 0.82 | 0.84   | 0.76    | 0.61 | 0.61    | 0.8    | 0.79     | 0.65   | 
| Phoneme                        | 0.1  | 0.32 | 0.33   | 0.18    | 0.13 | 0.11    | 0.13   | 0.09     | 0.12   | 
| Plane                          | 0.98 | 1.0  | 1.0    | 0.98    | 0.13 | 0.14    | 0.96   | 0.96     | 1.0    | 
| ProximalPhalanxOutlineAgeGroup | 0.86 | 0.83 | 0.85   | 0.84    | 0.49 | 0.49    | 0.84   | 0.83     | 0.84   | 
| ProximalPhalanxOutlineCorrect  | 0.73 | 0.91 | 0.92   | 0.81    | 0.68 | 0.68    | 0.88   | 0.81     | 0.82   | 
| ProximalPhalanxTW              | 0.8  | 0.81 | 0.79   | 0.8     | 0.41 | 0.45    | 0.8    | 0.78     | 0.79   | 
| RefrigerationDevices           | 0.38 | 0.51 | 0.52   | 0.5     | 0.35 | 0.33    | 0.37   | 0.44     | 0.51   | 
| ScreenType                     | 0.4  | 0.63 | 0.62   | 0.37    | 0.34 | 0.33    | 0.41   | 0.39     | 0.42   | 
| ShapeletSim                    | 0.49 | 0.72 | 0.73   | 0.52    | 0.5  | 0.5     | 0.51   | 0.5      | 0.58   | 
| ShapesAll                      | 0.77 | 0.9  | 0.92   | 0.76    | 0.13 | 0.02    | 0.61   | 0.62     | 0.62   | 
| SmallKitchenAppliances         | 0.37 | 0.78 | 0.78   | 0.59    | 0.41 | 0.33    | 0.49   | 0.62     | 0.67   | 
| SonyAIBORobotSurface           | 0.67 | 0.96 | 0.96   | 0.75    | 0.43 | 0.43    | 0.65   | 0.69     | 0.65   | 
| SonyAIBORobotSurfaceII         | 0.84 | 0.98 | 0.98   | 0.84    | 0.59 | 0.62    | 0.77   | 0.84     | 0.67   | 
| StarLightCurves                | 0.95 | 0.96 | 0.97   | 0.96    | 0.65 | 0.58    | 0.94   | 0.93     | 0.85   | 
| Strawberry                     | 0.97 | 0.96 | 0.96   | 0.95    | 0.64 | 0.64    | 0.95   | 0.96     | 0.88   | 
| SwedishLeaf                    | 0.85 | 0.97 | 0.96   | 0.93    | 0.12 | 0.07    | 0.85   | 0.89     | 0.82   | 
| Symbols                        | 0.83 | 0.95 | 0.91   | 0.83    | 0.26 | 0.17    | 0.76   | 0.81     | 0.8    | 
| ToeSegmentation1               | 0.58 | 0.96 | 0.96   | 0.64    | 0.51 | 0.53    | 0.49   | 0.6      | 0.86   | 
| ToeSegmentation2               | 0.74 | 0.87 | 0.91   | 0.77    | 0.7  | 0.82    | 0.44   | 0.74     | 0.81   | 
| Trace                          | 0.81 | 1.0  | 1.0    | 0.96    | 0.34 | 0.24    | 0.85   | 0.95     | 0.96   | 
| TwoLeadECG                     | 0.76 | 1.0  | 1.0    | 0.88    | 0.5  | 0.5     | 0.76   | 0.87     | 0.91   | 
| TwoPatterns                    | 0.95 | 0.87 | 1.0    | 1.0     | 0.4  | 0.26    | 0.98   | 0.99     | 0.87   | 
| UWaveGestureLibraryAll         | 0.95 | 0.82 | 0.86   | 0.95    | 0.29 | 0.13    | 0.93   | 0.92     | 0.59   | 
| Wine                           | 0.56 | 0.59 | 0.74   | 0.53    | 0.5  | 0.5     | 0.49   | 0.52     | 0.71   | 
| WordsSynonyms                  | 0.6  | 0.56 | 0.62   | 0.62    | 0.28 | 0.22    | 0.47   | 0.57     | 0.5    | 
| Worms                          | 0.35 | 0.66 | 0.62   | 0.46    | 0.43 | 0.42    | 0.42   | 0.34     | 0.42   | 
| WormsTwoClass                  | 0.6  | 0.74 | 0.74   | 0.68    | 0.59 | 0.58    | 0.54   | 0.59     | 0.56   | 
| syntheticcontrol               | 0.98 | 0.99 | 1.0    | 1.0     | 0.3  | 0.17    | 0.98   | 0.99     | 0.86   | 
| uWaveGestureLibraryX           | 0.77 | 0.75 | 0.78   | 0.79    | 0.26 | 0.13    | 0.71   | 0.71     | 0.61   | 
| uWaveGestureLibraryY           | 0.7  | 0.64 | 0.67   | 0.7     | 0.24 | 0.12    | 0.64   | 0.63     | 0.5    | 
| uWaveGestureLibraryZ           | 0.7  | 0.73 | 0.75   | 0.71    | 0.24 | 0.12    | 0.65   | 0.64     | 0.57   | 
| wafer                          | 1.0  | 1.0  | 1.0    | 1.0     | 0.91 | 0.89    | 0.99   | 0.96     | 0.92   | 
| yoga                           | 0.86 | 0.84 | 0.87   | 0.82    | 0.54 | 0.54    | 0.75   | 0.78     | 0.63   | 
| **total wins**                 | 6    | 36   | **50** | 17      | 1    | 1       | 1      | 4        | 3      |

These results should give an insight of deep learning for TSC therefore encouraging researchers to consider the DNNs as robust classifiers for time series data. 

## Reference

If you re-use this work, please cite:

```
@article{IsmailFawaz2018deep,
  Title                    = {Deep learning for time series classification: a review},
  Author                   = {Ismail Fawaz, Hassan and Forestier, Germain and Weber, Jonathan and Idoumghar, Lhassane and Muller, Pierre-Alain},
  journal                = {ArXiv},
  Year                     = {2018}
}
```
## Acknowledgement

We would like to thank NVIDIA Corporation for the Quadro P6000 grant and the Mésocentre of Strasbourg for providing access to the cluster.
We would also like to thank François Petitjean and Charlotte Pelletier for the fruitful discussions, their feedback and comments while writing this paper.
