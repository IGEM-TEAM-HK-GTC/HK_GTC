# HK_GTC - Detection Of PET Bottles
As we all know, plastic pollution is a severe problem to our ecosystem. In respond to this problem, our team had created a plastic detecting model. In this Github Repository, you will know how to use the model, and train the model with your own dataset.

## Dependanies
- Local Linux environment or [Google Colab Notebook](https://colab.research.google.com/drive/1sCnt15Fhb1XbxI3z0nbDSENIBLorK7ve "Google Colab Notebook")
- Detectron2
- Jupyter Notebook
- pytorch 1.8
- torchvision
- OpenCV
- Numpy
## Training
You can either train using our [Colab Notebook](https://colab.research.google.com/drive/1638UiZIIqFsfVlL0pctbNzJ-BjrPjdYQ#scrollTo=MCBlPWkL7giV "Colab Notebook") or in a local linux enviornment.
### Local  Training / Using the Model
Clone the repository and open `colab.ipynb` for model training and usage. Details of using the codes will be included in the notebooks.

# Training Results
We've trained our photos with different backbones and sample size. Backbones can be found in [detectron2/MODEL_ZOO](https://github.com/facebookresearch/detectron2/blob/master/MODEL_ZOO.md "detectron2/MODEL_ZOO"). The samples are selected randomly from the training dataset. The configurations used for all training are as follow:
- Backbone used: X101-FPN, R101-FPN, R50-FPN
- Batch size per step: 4
- Iterations: 1000
- Train image percentages used: 100%, 75%, 50%, 25% of training data
### Backbone test

| Backbone  |  AP  |   AP50| AP75  | APs  | APm  |  APl | model |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |------------ |
|  R50-FPN |   |   |   |   |   |   |||
| R101-FPN  |52.2| 75.6  | 59.8  |19.7|  45.5 | 68.7 ||
| X101-FPN  |   |   |   |   |   |   |   ||

### Random-subampling test
(Models here are all using R50-FPN backbone)

| Train Images Percentage  |  AP  |   AP50| AP75  | APs  | APm  |  APl | model |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|  100 |   |   |   |   |   |   ||
| 75  |   |   |   |   |   |   ||
| 50  |   |   |   |   |   |   |   ||
| 25  |   |   |   |   |   |   |   ||

