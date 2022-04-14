# 解决开发板运行QT后找不到字体文件

**错误：QFontDatabase: Cannot find font directory ‘/usr/lib/fonts’.**

## 方法1：

**从PC端的qt安装目录下拷贝fonts字体库到目标板/usr/lib/fonts中。
没有/usr/lib/fonts则先创建。**

## 方法2：

在开发板下找字体库

find -name fonts



