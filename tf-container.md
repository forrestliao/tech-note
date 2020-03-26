# TF-GPU Container + Py3 + Jupyter 

Resource: https://www.tensorflow.org/install?hl=zh-cn   
## Install Nvidia Docker
show Docker version
```
docker -v  //show docker version
```
If docker version >= 18.06 and <19, install nvidia v2
```
$ wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
$ sudo dpkg -i cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
$ sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
$ sudo apt-get update 
$ sudo apt-get install -y linux-headers-$(uname -r)
$ sudo apt-get -o Dpkg::Options::="--force-overwrite" install -y cuda-10-0 cuda-drivers
```
If Docker version <18.06, install nvidia-docker v1
```
sudo apt-get install nvidia-docker
```
## Start Nvidia Docker Container
docker-ce v19up:
```
docker run --gpus all
```
nvidia-docker v2:
``` 
docker run --runtime=nvidia 
```
nvidia-docker v1:
```
nvidia-docker run 
```
example:
```
#pull images
docker pull tensorflow/tensorflow:latest-gpu-py3-jupyter  

#run conatainer
nvidia-docker run -it --name forrest_tf2 -p 8888:8888 ce8f 

#get a jupyter URL
http://192.168.16.236:8888/?token=dd0d11c3f3e1a77bb866c0825ff1fddae4d019e7b5c82ba9
```