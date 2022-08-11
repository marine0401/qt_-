## firefly 编译ffmpeg

```
./configure --prefix="./FFmpeg" --enable-shared --enable-cross-compile --target-os=linux --arch=aarch64 --cc=/opt/firefly-qt-5.12.2-aarch64/host/bin/aarch64-buildroot-linux-gnu-gcc --cxx=/opt/firefly-qt-5.12.2-aarch64/host/bin/aarch64-buildroot-linux-gnu-g++ --enable-gpl --extra-libs=-ldl --extra-cflags="-fPIC" --extra-ldflags=-Wl,-Bsymbolic --extra-libs="-lpthread -lm" --disable-stripping --ln_s="cp -rfs"
```



```
../configure --prefix="./FFmpeg" --enable-shared --enable-cross-compile --target-os=linux --arch=aarch64 --cc=/usr/bin/aarch64-linux-gnu-gcc --cxx=/usr/bin/aarch64-linux-gnu-g++ --enable-gpl --extra-libs=-ldl --extra-cflags="-fPIC" --extra-ldflags=-Wl,-Bsymbolic --extra-libs="-lpthread -lm" --disable-stripping --ln_s="cp -rfs"
```





```
cmake -DCMAKE_BUILD_TYPE=RELEASE \
-DCMAKE_INSTALL_PREFIX=./usr/local \
-DPYTHON_DEFAULT_EXECUTABLE=$(which python3.6) \  
-DPYTHON3_EXECUTABLE=$(which python3.6) \        
-DPYTHON3_INCLUDE_DIR=/usr/include/$PY_NAME \
-DPYTHON3_INCLUDE_DIR2=/usr/include/aarch64-linux-gnu/$PY_NAME \
-DPYTHON3_LIBRARY=/usr/lib/aarch64-linux-gnu/lib$PY_NAME.so \
-DPYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/$PY_NAME/dist-packages/numpy/core/include/ \
-DBUILD_DOCS=OFF \
-DBUILD_EXAMPLES=OFF \
-DBUILD_TESTS=OFF \
-DBUILD_PERF_TESTS=OFF \


```

