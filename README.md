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
### Install new Python:

Removing old Python:
`sudo apt purge --auto-remove python3

Prerequisites:
```
sudo apt update
sudo apt upgrade -y
sudo apt install software-properties-common make build-essential gdb pkg-config \
      libffi-dev libgdbm-dev libdb-dev libc6-dev libsqlite3-dev tk-dev -y
```
Removing old Python:\
`sudo apt purge --auto-remove python3`

Installing Python:\
(this can take some time)
```
tar -xvf Python-3.11.3.tar.xz
cd Python-3.11.3
./configure --enable-optimizations
make
OR make -s -j$(nproc)
make test
sudo make install
```
if pip/pip3 is not installed: `sudo apt install python3-pip -y` then
```
pip install --upgrade pip
pip install --upgrade setuptools
sudo apt install wget ca-certificates
sudo apt install gedit -y
```
