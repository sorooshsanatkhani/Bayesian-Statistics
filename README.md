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
      tk-dev -y
```

### Install new Python:
Installing Python:\
(this can take some time)
```
tar -xvf Python-3.11.3.tar.xz
cd Python-3.11.3
./configure --enable-optimizations
make -j $(nproc)
make test -j $(nproc) /////(This can be ignored)
sudo make install -j $(nproc)
```

```
pip3 install --upgrade pip
pip3 install --upgrade setuptools
sudo apt install wget ca-certificates
sudo apt install gedit -y
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
https://developer.nvidia.com/cuda-downloads \
Add these in .bashrc so the CUDA is in the PATH:
```
export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```
### Install cuDNN
https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html

Install nccl \
Install tensorRT \
Install bazelisk as bazel: \
https://github.com/bazelbuild/bazelisk

## Install Package
`pip install --user --editable .`
