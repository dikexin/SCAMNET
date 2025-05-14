# SCAMNET - A Brainiy Strategy for Few-Shot Classification: Learn more from Less
### Training
To start the training procedure using a previously pretrained **ViT-small** architecture using 
one GPU for **100 epochs** on the **miniImageNet** training dataset, using beta = 0.5 run:
- For a 5-way 5-shot scenario:
```
python3 train_scamnet.py --num_epochs 100 --data_path <path-to-dataset> --arch vit_small --n_way 5 --k_shot 5 --chkpt_epoch 1600 --mdl_checkpoint_path <path-to-checkpoint-of-pretrained-model> --beta 0.5
```
- For a 5-way 1-shot scenario:
```
python3 train_scamnet.py --num_epochs 100 --data_path <path-to-dataset> --arch vit_small --n_way 5 --k_shot 1  --chkpt_epoch 1600 --mdl_checkpoint_path <path-to-checkpoint-of-pretrained-model> --beta 0.5
```


_Note_: Replace the `--data_path <path-to-dataset>` and possibly `--mdl_checkpoint_path <path-to-checkpoint-of-pretrained-model>` with the corresponding paths where you stored the model on your machine! 



## Evaluating
To evaluate a meta-trained **ViT-small** architecture on the **miniImageNet** test dataset, run:
- For a 5-way 5-shot scenario:
```
python3 eval_scamnet.py --data_path <path-to-dataset> --arch vit_small --n_way 5 --k_shot 5 --trained_model_type metaft --mdl_checkpoint_path <path-to-checkpoint-of-metaft-model>
```
- For a 5-way 1-shot scenario:
```
python3 eval_scamnet.py --data_path <path-to-dataset> --arch vit_small --n_way 5 --k_shot 1 --trained_model_type metaft  --mdl_checkpoint_path <path-to-checkpoint-of-metaft-model>
```
