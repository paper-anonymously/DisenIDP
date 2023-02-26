# DisenIDP

A PyTorch implementation of our DisenIDP.

## Dependencies
Install the dependencies via [Anaconda](https://www.anaconda.com/):
+ Python (>=3.8)
+ PyTorch (>=1.8.1)
+ NumPy (>=1.17.4)
+ Scipy (>=1.7.3)
+ torch-geometric(>=2.0.4)
+ tqdm(>=4.62.2)


create virtual environment:
```
conda create --name DisenIDP python=3.8
```

activate environment:
```
conda activate DisenIDP
```

install pytorh from [pytorch](https://pytorch.org/get-started/previous-versions/):
```
conda install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 cudatoolkit=10.2 -c pytorch
```

To install all dependencies:
```
pip install -r requirements.txt
```

## Usage
Here we provide the implementation of DisenIDP along with twitter dataset.

+ To train and evaluate on Twitter:
```
python run.py -data_name=twitter
```
More running options are described in the codes, e.g., `-data_name= twitter`

## Folder Structure

MetaCas
```
└── data: # The file includes datasets
    ├── twitter
       ├── cascades.txt       # original data
       ├── cascadetrain.txt   # training set
       ├── cascadevalid.txt   # validation set
       ├── cascadetest.txt    # testing data
       ├── edges.txt          # social network
       ├── idx2u.pickle       # idx to user_id
       ├── u2idx.pickle       # user_id to idx
       
└── models: # The file includes each part of the modules in MetaCas.
    ├── ConvBlock.py.py # The core source code of Convolution.
    ├── model.py # The core source code of DisenIPD.
    ├── TransformerBlock.py # The core source code of time-aware attention.

└── utils: # The file includes each part of basic modules (e.g., metrics, earlystopping).
    ├── EarlyStopping.py  # The core code of the early stopping operation.
    ├── Metrics.py        # The core source code of metrics.
    ├── graphConstruct.py # The core source code of building hypergraph.
    ├── parsers.py        # The core source code of parameter settings. 
└── Constants.py:    
└── dataLoader.py:     # Data loading.
└── run.py:            # Run the model.
└── Optim.py:          # Optimization.

```
