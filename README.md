# Bayesian-Statistics
Learning Bayesian statistics

In this repository some codes from sources below have been used:\
https://github.com/ksachdeva/rethinking-tensorflow-probability \
https://xcelab.net/rm/statistical-rethinking


Install Ubuntu in WSL. Then add a file named wsl.conf in /etc and add these lines to it:
```
[boot]
systemd=true

[user]
default=soroosh
```
Then export the distro and unregister the Ubuntu. Next import the exported distro in a location. Now you have a distro in your specific location.

## Prerequisites:
```
sudo apt update
sudo apt upgrade -y
sudo apt install software-properties-common make build-essential gdb pkg-config \
      libffi-dev libgdbm-dev libdb-dev libc6-dev libsqlite3-dev libssl-dev \
      libncurses-dev libffi-dev liblzma-dev libbz2-dev libreadline-dev zlib1g \
      tk-dev python3-dev python3-pip wget ca-certificates gedit -y
```
`sudo pip install -U -r requirements.txt`
### Install CUDA
[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local)
```
wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda-repo-wsl-ubuntu-11-8-local_11.8.0-1_amd64.deb
sudo dpkg -i cuda-repo-wsl-ubuntu-11-8-local_11.8.0-1_amd64.deb
sudo cp /var/cuda-repo-wsl-ubuntu-11-8-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt update
sudo apt -y install cuda
```
Add these in .bashrc so the CUDA is in the PATH:
```
export PATH=/usr/local/cuda-11.8/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-11.8/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
export TF_MIN_GPU_MULTIPROCESSOR_COUNT=6
```
### Install cuDNN
Download Tar file from here: \
https://developer.nvidia.com/cudnn
```
tar -xvf cudnn-linux-x86_64-8.*_cuda11-archive.tar.xz
sudo cp cudnn-*-archive/include/cudnn*.h /usr/local/cuda-11.8/include 
sudo cp -P cudnn-*-archive/lib/libcudnn* /usr/local/cuda-11.8/lib64 
sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda-11.8/lib64/libcudnn*
```
Copy the libraries and header in cuda-11.8 and not just cuda
### Install tensorflow
`sudo pip install -U keras_preprocessing --no-deps` \
`sudo pip install -U tensorflow tensorflow_probability`
## Install Package
`pip install --user --editable .`
