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

```
pip3 install --upgrade pip
pip3 install --upgrade setuptools
```
### More prerequisites
Make an requirements.txt file and add these:
```
ipykernel
pytest
pandas
numpy
h5py
netcdf4
scipy
matplotlib
seaborn
arviz
daft
causalgraphicalmodels
wheel
requests
opt_einsum
```
Then install the required packages:
```
pip install -U -r requirements.txt
pip install -U keras_preprocessing --no-deps
```
### Install CUDA
[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local) \
Add these in .bashrc so the CUDA is in the PATH:
```
export PATH=/usr/local/cuda-11.8/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-11.8/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```
### Install cuDNN
https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html \
Copy the libraries and header in cuda-12.1 and not just cuda
### Install nccl
https://developer.nvidia.com/nccl \
These will be the paths for nccl
```
/usr/include
/usr/lib/x86_64-linux-gnu
```
### Install tensorRT
https://developer.nvidia.com/tensorrt
### Install bazelisk
Install it as bazel: \
https://github.com/bazelbuild/bazelisk \
Download the binary file. Rename it to bazel and put it in `/usr/local/bin/`

## Install Package
`pip install --user --editable .`
