## 开发工具安装
```
sudo apt update
sudo apt install vim emacs net-tools openssh-server git  gcc g++ make cmake
```

```
sudo apt install  libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev 
sudo apt install --no-install-recommends libboost-all-dev
sudo apt install libgflags-dev libgoogle-glog-dev liblmdb-dev
sudo apt install libopenblas-dev libatlas-base-dev
```

## 创建conda环境
```
conda create -n dl-test python=3.8
conda activate dl-test
conda install scikit-image numpy pytest protobuf
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

## pycaffe测试
```
import sys
sys.path.insert(0, '/home/wangwq/Documents/repos/caffe/python')
import caffe
```
