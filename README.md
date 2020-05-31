# Anonymous GitHub

This is a PyTorch implementation of the paper "XXX".

## Installation

Install the dependency using the following command:

```bash
pip install -r requirements.txt
```

* torch
* scipy>=0.19.0
* numpy>=1.12.1
* pandas>=0.19.2
* pyyaml
* statsmodels
* tensorflow>=1.3.0
* torch
* tables
* future


## Data Preparation

The traffic data files for Los Angeles (METR-LA) and the Bay Area (PEMS-BAY) are put into the `data/` folder. 

Run the following commands to generate train/test/val dataset at  `data/{METR-LA,PEMS-BAY}/{train,val,test}.npz`.
```bash
# Unzip the datasets
unzip data/metr-la.h5.zip -d data/
unzip data/pems-bay.h5.zip -d data/

# Create data directories
mkdir -p data/{METR-LA,PEMS-BAY}

# METR-LA
python -m scripts.generate_training_data --output_dir=data/METR-LA --traffic_df_filename=data/metr-la.h5

# PEMS-BAY
python -m scripts.generate_training_data --output_dir=data/PEMS-BAY --traffic_df_filename=data/pems-bay.h5
```

## Train Model

When you train the model, you can run:

```bash
# METR-LA
python train.py --config_filename=data/model/para_la.yaml --temperature=0.5

# PEMS-BAY
python train.py --config_filename=data/model/para_bay.yaml --temperature=0.5
```

Hyperparameters can be modified in the `para_la.yaml` and `para_bay.yaml` files.

## Design your own model

You can directly modify the model in the "model/pytorch/model.py" file.

## Acknowledgments

XXX, XXX