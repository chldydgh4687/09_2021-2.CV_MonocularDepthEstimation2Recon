# 09_2021-2.CV_MonocularDepthEstimationRecon

---

### Training

1. Start Nvidia-docker : https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker 
2. Checking CUDA, pytorch, python version in paper. (cuda9.1, pytorch 0.4 or 1.0.0 )
3. Finding images in dockerHub : https://hub.docker.com/r/iraadit/cuda9.1-cudnn7-opencv-fn
4. pull(Download) images into OS.
```sh
docker pull iraadit/cuda9.1-cudnn7-opencv-fn:latest
docker images
```

![56856856](https://user-images.githubusercontent.com/11037567/146694833-1b29e995-66ab-4201-af08-348a9d4d297b.PNG)

  
5. Create Container
```
#보통의 경우
$docker run --name $컨테이너이름 -it (images_id)

#gpu버전의 경우(nvidia-docker)
$docker run --gpus all --name $컨테이너이름 -it (images_id) bash

# Display all of containers
$docker ps -a
```

6. anacodna3, pytorch 1.0.0 install
7. Following Gudieline (https://github.com/big-chan/Sejong_computervision_termproject_monodepth)
```
wget -i splits/kitti_archives_to_download.txt -P kitti_data/
cd kitti_data
unzip "*.zip"
cd ..

CUDA_VISIBLE_DEVICES=0 python train.py --model_name tested --png --log_dir tested_log
```

### Training Monitoring
  
![training](https://user-images.githubusercontent.com/11037567/144466246-6c4aaf46-7814-47cd-ae18-f896790ee439.PNG)


---

### EvalAI LeaderBoard
- Environment : Ubuntu18.04, TITAN RTX, Docker, CUDA9.1, python3.6.6, pytorch 1.0.1
- Reference DockerHub : 
- Trained_model : 모델이 커서 생략합니다.
- Predicted_Submission.npy_link : https://drive.google.com/file/d/1-9192deJaYaqh_VAeHSUw4EOAtBrcaik/view?usp=sharing
  
![12345](https://user-images.githubusercontent.com/11037567/144466498-18afd658-89ba-4c6d-9536-af36e3ae4cd3.png)

---

### How to do learning in this task?

![745745](https://user-images.githubusercontent.com/11037567/144722911-2177a572-0f65-4627-9ed6-177b14fa1e20.PNG)

### Loss

![5547](https://user-images.githubusercontent.com/11037567/144722919-a922272f-566b-4251-8e70-a358ad54bb0c.PNG)
![568568](https://user-images.githubusercontent.com/11037567/144722925-1482ebdf-7a90-463a-be07-174fd9118d2f.PNG)

---

### Performance to be enable to learn  

- DepthEstimation Task
- Using Docker
- Syntehsized view Task using DeepLearning.
- Various loss

--- 

#### This repo was referenced by https://github.com/big-chan/Sejong_computervision_termproject_monodepth  
InClass : https://github.com/sejongresearch/ComputerVision  
EvalAIStarters : https://github.com/sejong-rcv/EvalAI-Starters  

