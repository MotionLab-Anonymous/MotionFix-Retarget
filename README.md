### Download MotionFix

[MotionFix](https://github.com/atnikos/motionfix) is avaliable from [here](https://drive.google.com/drive/folders/1DM7oIJwxwoljVxAfhfktocTptwVX5sqR).

You should rename the motionfix.pth.tar into motionfix_train.pth.tar

### Download SMPL+H and DMPL model

Download SMPL+H mode from [SMPL+H](https://mano.is.tue.mpg.de/download.php) (choose Extended SMPL+H model used in AMASS project) and DMPL model from [DMPL](https://smpl.is.tue.mpg.de/download.php) (choose DMPLs compatible with SMPL). Then place all the models under "./body_model/".

### Extract and Process Data

You need to run the following scripts in order to obtain MotionFix-Retarget dataset:

You have specify your_path in these ipynb!!!

1. output_files_from_MotionFix.ipynb
2. raw_pose_processing.ipynb
3. motion_representation.ipynb
4. cal_mean_variance.ipynb


## Data Structure
```sh
<DATA-DIR>
./animations.rar        //Animations of all motion clips in mp4 format.
./new_joint_vecs.rar    //Extracted rotation invariant feature and rotation features vectors from 3d motion positions.
./new_joints.rar        //3d motion positions.
./texts.rar             //Descriptions of motion data.
./Mean.npy              //Mean for all data in new_joint_vecs
./Std.npy               //Standard deviation for all data in new_joint_vecs
./all.txt               //List of names of all data
./train.txt             //List of names of training data
./test.txt              //List of names of testing data
./train_val.txt         //List of names of training and validation data
./val.txt               //List of names of validation data
./all.txt               //List of names of all data
```
HumanML3D data follows the SMPL skeleton structure with 22 joints. 

The file named in "MXXXXXX.\*" (e.g., 'M400000.npy') is mirrored from file with correspinding name "XXXXXX.\*" (e.g., '400000.npy'). Text files and motion files follow the same naming protocols, meaning texts in "./texts/XXXXXX.txt"(e.g., '400000.txt') exactly describe the human motions in "./new_joints(or new_joint_vecs)/XXXXXX.npy" (e.g., '400000.npy')

