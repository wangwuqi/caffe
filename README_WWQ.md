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
