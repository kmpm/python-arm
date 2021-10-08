# Python ARM
This repository contains somewhat newer python releases
compiled on Raspberry Pi (RaspOS).

Use at your own risk.


# How it's made
```shell
# pick version to use
export PYVERSION=3.9.7

# install dependencies
sudo apt-get install -y build-essential tk-dev libncurses5-dev libncursesw5-dev libreadline6-dev libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev libffi-dev

# download source
wget https://www.python.org/ftp/python/$PYVERSION/Python-$PYVERSION.tar.xz

# extract
tar xf Python-$PYVERSION.tar.xz
cd Python-$PYVERSION

# configure and make
./configure --prefix=/usr/local/opt/python-$PYVERSION
make -j 4

# Install
sudo make install

# Package for upload to github
# 32bit RaspiOS on Raspberry Pi 400
tar -zcf python-3.9.7-raspios-armv7l.tar.gz /usr/local/opt/python-3.9.7/

```