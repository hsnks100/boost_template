# boost_template

```
cd /tmp
wget https://dl.bintray.com/boostorg/release/1.72.0/source/boost_1_72_0.tar.gz
tar zxvf boost_1_72_0.tar.gz
boost_1_72_0
./bootstrap.sh
sudo ./b2 install

```

```
git clone https://github.com/hsnks100/boost_template.git 
cd boost_template
mkdir build
cd build
cmake ..
make -j4
```

안되면 CMakeLists.txt 에 설정된 시스템에 설치된 openssl 경로 확인.

openssl 직접설치(선택)
```
cd /tmp 
wget https://www.openssl.org/source/openssl-1.1.0.tar.gz 
tar zxvf openssl-1.1.0.tar.gz 
cd openssl-1.1.0
./config
make
sudo make install

```


