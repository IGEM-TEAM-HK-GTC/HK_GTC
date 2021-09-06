# HK_GTC - Detection Of PET Bottles
As we all know, plastic pollution is a severe problem to our ecosystem. In respond to this problem, our team had created a plastic detecting model. In this Github Repository, you will know how to use the model, and train the model with your own dataset.

## Dependenies
- Local Linux environment or [Google Colab Notebook](https://colab.research.google.com/drive/1sCnt15Fhb1XbxI3z0nbDSENIBLorK7ve "Google Colab Notebook")
- Detectron2
- Jupyter Notebook
- pytorch 1.8
- torchvision
- OpenCV
- Numpy
## Training
You can either train using our [Colab Notebook](https://colab.research.google.com/drive/1sCnt15Fhb1XbxI3z0nbDSENIBLorK7ve "Colab Notebook") or in a local linux enviornment.
### Local  Training / Using the Model
Clone the repository and open `colab.ipynb` for model training and usage. Details of using the codes will be included in the notebooks.

# Training Results
We've trained our photos with different backbones and sample size. Backbones can be found in [detectron2/MODEL_ZOO](https://github.com/facebookresearch/detectron2/blob/master/MODEL_ZOO.md "detectron2/MODEL_ZOO"). The samples are selected randomly from the training dataset. The configurations used for all training are as follow:
- Backbone used: X101-FPN, R101-FPN, R50-FPN
- Batch size per step: 2
- Iterations: 1000
- Train image percentages used: 100%, 75%, 50%, 25% of training data
### Backbone test

| Backbone  |  AP  |   AP50| AP75  | APs  | APm  |  APl | model |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |------------ |
|  R50-FPN |  51.1|  72.2 | 60.6  | 16.7  |  44.8 |  68.3 |[model](https://github.com/IGEM-TEAM-HK-GTC/HK_GTC/blob/main/models/R50FPN/model_final.pth)|
| R101-FPN  |52.3| 74.8  | 59.9  | 19.0 |  45.7 | 69.0 |[model](https://github.com/IGEM-TEAM-HK-GTC/HK_GTC/blob/main/models/101FPN3x/model_final.pth)|
| X101-FPN  | 54.8  | 77.8 | 61.4 | 10.9 |  48.8 | 72.5 |[model](https://github.com/IGEM-TEAM-HK-GTC/HK_GTC/blob/main/models/X101FPN/model_final.pth) |

### Random-subampling test
(Models here are all using R50-FPN backbone)

| Train Images Percentage  |  AP  |   AP50| AP75  | APs  | APm  |  APl |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|  100 |   51.1|  72.2 | 60.6  |16.7|  44.8 |   68.3 |
| 75  |  49.6 |  70.0 | 58.2  |  12.0 | 44.0  |  66.7 |
| 50  | 48.6  | 70.4  | 58.0  | 12.9  |  43.0 |  64.0 |
| 25  | 48.0  |  68.4 |  57.5 | 11.9  |  43.4 | 63.0|

