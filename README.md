# HybridFC: A Hybrid approach for fact checking over knowledge graphs

First step is to clone the project.
## 1) Cloning the project

``` html
git clone https://github.com/umairq/HybridFC.git
``` 

### Reproducing Results
There are two options to repreoduce the results. (1) using pre-generated data, and (2) Regenerate data from FactCheck output

## 2) Using pre-generated data
download and unzip data and embeddings files in the root folder of the project.

``` html
pip install gdown

gdown https://drive.google.com/uc?id=17yiwWHss42ErLEbaPDtbIZBGqJVAj0LC

gdown https://drive.google.com/uc?id=13_tjg7YQby5fHUISixhYPFeH-Ylk816q


unzip dataset.zip

unzip Embeddings.zip
``` 


Note: if it gives permission denied error you can try running the following command

``` html
pip install --upgrade --no-cache-dir gdown
``` 

## 3) Regenerate data from FactCheck output
In case you don't want to use pre-generated data, follow this step:

As an input user need output of [FactCheck](https://github.com/dice-group/FactCheck/tree/develop-for-FROCKG-branch)

running on [FactBench dataset](https://github.com/DeFacto/FactBench).

Details are in [overall_process folder](https://github.com/umairq/HybridFC/tree/main/overall_process)

## 4) Running experiments

``` html

#setting up environment
#creating and activating conda environment

conda env create -f environment.yml

conda activate hfc2


python main.py --emb_type TransE --model KGE-only --num_workers 32 --min_num_epochs 100 --max_num_epochs 1000 --check_val_every_n_epochs 10 --eval_dataset FactBench 

# computing evaluation files in Hybrid_Stroage folder under dataset directory
python evaluate_checkpoint_model.py
``` 

comments:
for differnt embeddings type(emb_type) or model type(model), you just need to change the parameters.
Available embeddings types:
ConEx, TransE, ComplEx, RDF2Vec, QMult
Available models:
full-Hybrid, KGE-only, text-KGE-Hybrid, path-only, text-path-Hybrid, KGE-path-Hybrid

After computing evalua

## Future plan:
TODO
## Acknowledgement 
TODO
## Authors
TODO







