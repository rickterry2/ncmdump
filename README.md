Netease Cloud Music Copyright Protection File Dump
===========

## 简介

C++版本由[iyanging](https://github.com/iyanging)提供，且支持Windows

因为最近买了个WALKMAN 发现网易云音乐有的音乐下载的文件是ncm受保护的文件 没法放到里面听 所以这个工具诞生了 用于将ncm格式转回原有的格式. 自动设置封面以及标题作者专辑等信息. 请勿传播扩散送给有缘人. 本来代码用C写的结果没找到支持flac meta数据修改的库强行转c++ 蓝瘦

## 依赖库
	* openssl
	* taglib

## Linux编译

```
mkdir build
cd build
cmake ..
make
```

## Windows编译

先通过[vcpkg](https://github.com/Microsoft/vcpkg)安装依赖库，再编译

```
mkdir build
cd build
cmake -G "Visual Studio 15 2017 <由依赖库triplet决定是否添加Win64>" -DVCPKG_TARGET_TRIPLET=<依赖库triplet> -DCMAKE_TOOLCHAIN_FILE=<本地vcpkg/scripts/buildsystems/vcpkg.cmake路径> ..
cmake --build . --target ALL_BUILD --config <由依赖库triplet决定Debug或是Release>
```

## 使用
	ncmdump [files]...
