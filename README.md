# Map to Map: From SLAM to CAD Maps and Back Using Generative Models
put the bash scripts in this folder and run the ones of the winning result.

the ones that include cropping change dataset_cropping.py to dataset.py
and vice versa

also to decide on how long to keep the training change in options the epoch mapping
so at every resolution for how many epochs you would like to stay at this res

also batch rate by default is 1 decrease depending on processing power (but to do that use all py files from additionalfiles int and double issues)

for niter and niter_decay depending on the number of iterations put 70% niter and 30% decay. together they are equal the total number of epochs. 


1. Update test data to include images that have round walls and real images
2. in folder additional.. in ucl VM run this 
for BtoA: 
updatedNode1032cstthickthesisNoPartialBA
32 epoch mapping (400000 for 32)
no cropping (use dataset.py with no cropping)
nohup python train.py --project_name BAaddCroppedTesting --dataset DATASET_proc_nopartial_BA_thick --niter 525 --niter_decay 225 &


for AtoB:
thesisNoPartialCropped
restore epoch mapping to how it was (15,30...)
cropping (use dataset.py with cropping)
python train.py --project_name ABaddCroppedTesting --dataset DATASET_proc_nopartial --niter 140 --niter_decay 60

3. for evaluation use this: C:\Users\REMAD\OneDrive\Desktop\RALresubmission\anime2clothing\winning-result\updatedNode1032cstthickthesisNoPartialBA_Results\FinalResultpaper matlab file

