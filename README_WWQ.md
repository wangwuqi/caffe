## 创建conda环境
```
conda create -n dl-test python=3.8
conda activate dl-test
conda install scikit-image numpy pytest protobuf
```
系统安装的protobuf要与conda安装的protobuf版本一致，因此系统protobuf可以通过源码安装
libprotobuf-dev和protobuf-compiler的安装通过源码安装，例如下载`https://github.com/protocolbuffers/protobuf/releases/download/v3.20.1/protobuf-cpp-3.20.1.tar.gz`
```
tar -xvzf protobuf-cpp-3.20.1.tar.gz 
cd protobuf-cpp-3.20.1/
./configure
make -j
make check -j8
sudo make install
sudo ldconfig
```
## 开发工具安装
```
sudo apt install  libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev 
sudo apt install --no-install-recommends libboost-all-dev
sudo apt install libgflags-dev libgoogle-glog-dev liblmdb-dev
sudo apt install libopenblas-dev libatlas-base-dev
```

## caffe源码编译安装和测试
http://caffe.berkeleyvision.org/installation.html
```
cd caffe
sudo make clean
mkdir build && cd build
cmake ..
make all -j8
make install
make runtest -j8
```

## pycaffe测试
```
import sys
sys.path.insert(0, '/home/wwq/Documents/repos/caffe/python')
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