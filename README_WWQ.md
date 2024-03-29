## 开发工具安装
```
sudo apt update
sudo apt install vim emacs net-tools openssh-server git  gcc g++ make cmake
```

```
sudo apt install libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
sudo apt install --no-install-recommends libboost-all-dev
sudo apt install libgflags-dev libgoogle-glog-dev liblmdb-dev
sudo apt install libopenblas-dev libatlas-base-dev
```

## 安装Miniconda3
下载python3.8版本的Miniconda3，并安装
```
wget https://repo.anaconda.com/miniconda/Miniconda3-py38_4.12.0-Linux-x86_64.sh
bash Miniconda3-py38_4.12.0-Linux-x86_64.sh
```

## 创建conda环境
```
conda create -n dl-test python=3.8
conda activate dl-test
conda install scikit-image numpy pytest
```

## caffe源码编译安装和测试
http://caffe.berkeleyvision.org/installation.html
```
cd caffe
mkdir build && cd build
cmake ../
make all
make install
make runtest
```

## conda虚拟环境安装protobuf
注意：caffe编译完后再进行安装
```
conda activate dl-test
conda install protobuf
```

## pycaffe测试
```
import sys
sys.path.insert(0, '/home/wangwq/Documents/repos/caffe/python')
import caffe
```
注意：libtiff需要4.0版本，wsl ubuntu20.04更新后可能会升级为4.1，可以从[官网](http://download.osgeo.org/libtiff/)下载[tiff-4.0.10.zip](http://download.osgeo.org/libtiff/tiff-4.0.10.zip)，然后编译安装libtiff
```
cd tiff-4.0.10/
mkdir cmake-build
cd cmake-build/
cmake ..
make
sudo make install
```
参考：[编译报错：undefined reference to `TIFFReadDirectory@LIBTIFF_4.0‘解决方法](https://blog.csdn.net/qq_39779233/article/details/127718188)