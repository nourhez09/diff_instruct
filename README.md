This is an adaptation of the code from  Diff-Instruct: A Universal Approach for Transferring Knowledge From Pre-trained Diffusion Models (Diff-Instruct) Official PyTorch implementation of the NeurIPS 2023 paper forked from the repo https://github.com/pkulwj1994/diff_instruct : which we customized to run our own experiments.


We provide here the guidelines on how to run our experiments and the modifications we did in comparison with the original code 

Namely, with respect to the original repository , we modify the main training files ; di_training_loop and di_train to run our experiments, as well as dataset_tool_file.py 


This is done as a project for the Generative modeling course of the masters program M2DS.

Steps to run the code : 

<!-- Preparing the dataset -->
python dataset_tool_edm.py --source=/data/downloads/cifar-10-python.tar.gz --dest=/data/datasets/cifar10-32x32.zip

<!-- Run the code -->
 python diff_instruct-main\diff_instruct-main\di_train2.py --outdir=logs\di\ci10-uncond --data=data\datasets\cifar10-32x32.zip --arch=ddpmpp --batch 64  --edm_model cifar10-uncond --cond=0 --metrics 'fid50k_full,is50k' --tick 1 --snap 1000 --lr 0.00001 --glr 0.00001 --init_sigma 1.0 --fp16=0 --lr_warmup_kimg -1 --ls 1.0 --sgls 1.0