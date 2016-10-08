# Tensorflow-singularity-container-with-GPU-support
This repository provides a bootstrap definition file to build Tensorflow singularity container with Nvidia GPU support. Most of scripts are based on Ignor's work (refer to [Singularity group GPU thread] (https://groups.google.com/a/lbl.gov/forum/m/#!msg/singularity/CezfXNjLGe0/JIv6ay4CBwAJ), where igor provided scripts to build scientific linux 7 GPU container) 

## How to build
 1. Install [singularity](https://github.com/gmkurtzer/singularity) from master branch. You can see the installation instructions on [singularity homepage](http://singularity.lbl.gov/#install) (section: Build an RPM from the source).
 2. Download nvidia driver (NVIDIA-Linux-x86_64-352.93.run), cuda 7.5 (cuda_7.5.18_linux.run) and cudnn5 (cudnn-7.5-linux-x64-v5.1.tgz) (Here I assume that the same nvidia driver/cuda have been installed in your host machine) and store the downloaded files and above scripts under /root
 3. sudo into the root ( sudo -s) and 
 4. cd into /root and run 'sh build.sh'
 5. copy ubuntu_tensorflow_GPU.img into your own local folder and change its owner and group (sudo chown user_id:group_id ubuntu_tensorflow_GPU.img)
 6. Run "singularity exec ubuntu_tensorflow_GPU.img python hello_world.py" to check whether it works.
 

