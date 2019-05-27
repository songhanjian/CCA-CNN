# CCA-CNN
Action Temporal Detection Method Based on Confidence Curve Analysis

CCA-CNN is improvement of S-CNN, the basic structure adopts structure of S-CNN, the installation of CCA-CNN is as similar as S-CNN(https://github.com/zhengshou/scnn)



Training:

we offer the pre-train model of C3D on ./models/conv3d_deepnetA_sport1m_iter_1900000

the training labels in THUMOS2014 is set on ./experiments/THUMOS14/network_proposal_alter/train/labels

train_out.lst: the training label for 4-class proposal network 

train_pro_pre_uniform_16: the training label in pre-training stage used UCF-101 and background dataset for 2-class proposal network 

train_uniform_16: the training label in training stage for 2-class proposal network 

we offer a script on ./experiments/THUMOS14/network_proposal_alter/finetuning.sh for training.



run demo:

the implement of CCA-CNN is on ./experiments/THUMOS14/network_proposal_alter/train/script/calculate_alter.py

the main of calculate_alter.py is interface contained of 4 input:

1.video_dir : the path of input dataset
2.input_videos : a list of input videos in video_dir
3.isKeepProposal : is the result of proposal network need to be retained
3.isKeepLoc : is the result of localization network need to be retained

the model of proposal network is on ./models/:
SCNN_uniform16_binary_iter_30000 is model for 4-class network
SCNN_uniform16_binary_bgaciton_iter_50000 is model for 2-class network

the output of main method is seg_swin which is same defined as S-CNN(https://github.com/zhengshou/scnn)



