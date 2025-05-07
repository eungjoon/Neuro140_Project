# READ ME

# SET-UP

This file is compatible with the Kaggle notebook API. Due to the extremely large size of the image datasets used, we were unable to download the datasets locally. Instead, we were able to access these datasets through the Kaggle network and API.

# DATASETS

This project uses the following datasets:
NIH Chest X-ray: https://www.kaggle.com/datasets/nih-chest-xrays/data/code
VinDr: https://www.kaggle.com/datasets/awsaf49/vinbigdata-original-image-dataset
Guangzhou Pediatric Chest X-ray: https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

Based on the file architecture of each dataset, custom Dataset Classes were created (located in the "Setup datasets and dataloaders" section). For the GZ dataset, we used the pre-existing ImageFolder class.

# USE OF AI

ChatGPT was used for de-bugging custom Dataset Classes and working with the kagglehub API. It was also used for de-bugging the For loops used for multiple experimentation in up-sampling procedures.

# MODEL

This project uses the AlexNet model pretrained on ImageNet cited below.
AlexNet: https://papers.nips.cc/paper_files/paper/2012/hash/c399862d3b9d6b76c8436e924a68c45b-Abstract.html
ImageNet: https://www.image-net.org/

# EXPERIMENTS

1. Naive Model: Each model is trained on the NIH dataset only
2. Fine-tuning: The model trained on the NIH dataset is further trained on a subset of the target dataset, using different learning rates and subset sizes
3. Oracle: The model is trained on a combination of NIH and target train datasets
4. Up-sampling: The model bootstraps additional samples of the target train datasets. The model is trained on a combination of NIH and the bootstrapped target train datasets.

# RESULTS

The results of each experiment are stored in results.df. The last part of each row represents which test set the model was evaluated on. Each model was also evaluated on the NIH test set for reference.
