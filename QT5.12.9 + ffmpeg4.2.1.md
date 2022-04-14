# QT5.12.9 + ffmpeg4.2.1

ffmpeg文件目录

![image-20220412210716106](C:\Users\marine0401\AppData\Roaming\Typora\typora-user-images\image-20220412210716106.png)

QT pro文件配置

```
#将输出文件直接放到源码目录下的bin目录下，将dll都放在了次目录中，用以解决运行后找不到dll的问#DESTDIR=$$PWD/bin/
contains(QT_ARCH, i386) {
message("32-bit")
DESTDIR = $${PWD}/bin32
} else {
message("64-bit")
DESTDIR = $${PWD}/bin64
}
 
SOURCES +=
src/main.cpp
 
win32{
 
contains(QT_ARCH, i386) {
message("32-bit")
INCLUDEPATH += $$PWD/lib/win32/ffmpeg/include
$$PWD/src
 
LIBS += -L$$PWD/lib/win32/ffmpeg/lib -lavcodec -lavdevice -lavfilter -lavformat -lavutil -lpostproc -lswresample -lswscale
 
} else {
message("64-bit")
INCLUDEPATH += $$PWD/lib/win64/ffmpeg/include
$$PWD/src
 
LIBS += -L$$PWD/lib/win64/ffmpeg/lib -lavcodec -lavdevice -lavfilter -lavformat -lavutil -lpostproc -lswresample -lswscale
}
 
}
```



将ffmpeg目录下的bin/win64下的东西复制到，QT的可执行文件下，供运行时链接使用





将include下的文件夹也复制到QT的工程目录下