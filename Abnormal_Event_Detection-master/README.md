# Abnormal_Event_Detection
Abnormal Event Detection in Videos using SpatioTemporal AutoEncoder


Code for the [paper](https://arxiv.org/abs/1701.01546).


# Dependencies:


Install ffmpeg for Video frame extraction.
    windows环境：
    github将zip下载到本地，将bin目录下的三个exe文件放到conda环境中和pythonw.exe同级的目录下。命令行使用ffmpeg -h查看帮助。

# Library based Dependencies:

numpy

sklearn

keras

tensorflow

h5py

scipy

OpenCV


# Instructions

Run processor.py with args the path of Video directory and frame rate.
    
    python processor.py ./train 5
    ./train目录下存放视频文件，会通过ffmpeg抽帧保存图片格式到./train/frames下，然后通过存储函数，将图片存储成training.npy,并把中间文件夹frames/删除
Run train.py to train the model
    
    python train.py
    实际上是将x_train复制一份到y_train，计算偏差则是model(x_train)和y_train；
    即通过预测

Run test.py to test on testing data.
    
    通过processor.py生成了test.npy,传入使用test.py进行测试
    

Run start_live_feed.py to test the model on live webcam feed.
    
    通过cv2.VideoCapture

You can adjust the threshold parameter in test.py to different values to adjust sensitivity

Datasets Recommended: Avenue Dataset for Anomaly Detection
