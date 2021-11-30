# Map to Map: From SLAM to CAD Maps and Back Using Generative Models
This is the code implementation of the thesis "Map to Map: From SLAM to CAD Maps and Back Using Generative Models". The code relies on the Anime2clothing repository which is included as part of this code.

## Preparations and Training Options
- create invironment: 
```python 
conda env create -f environment.yml
```
- Unzip the dataset file
- To include cropping in the training use dataset_cropping.py instead of dataset.py
- To decide on how long to keep the training, change in train_options.py the epoch mapping giving the amount of epochs required at every resolution
- When running train.py set niter and niter_decay to 70% and 30 % respectively of the total number of epochs.

## For SLAM to CAD (BtoA): 
- Epoch mapping: Use 32 epoch mapping (400000 epochs for 32 resolution)
- No cropping (use dataset.py with no cropping)
```python
python train.py --project_name BA --dataset DATASET_proc_nopartial_BA_thick --niter 525 --niter_decay 225 &
```

## For CAD to SLAM (AtoB):
- Restore epoch mapping to how it was (15,30...)
- Cropping (use dataset.py with cropping)
```python
python train.py --project_name AB --dataset DATASET_proc_nopartial --niter 140 --niter_decay 60
```

## Testing
- As the model is training, it will test on the testing data.
- The testing file is taken as is from Anime2clothing and thus will not give you the same results generated using the train.py.
- Some pretrained models can be found [here](https://drive.google.com/file/d/15ZnQGuzvSYYnfWKbArAU6BZ1NHZNOe4R/view?usp=sharing).

## Reference
If you use parts of this code please cite this work:
```
@phdthesis{daher2020map,
  title={Map to Map: From SLAM to CAD Maps and Back Using Generative Models},
  author={Daher, Rema},
  year={2020}
}
```
