# Qt for Android环境搭建

### 1.1所需要的工具

Android SDK , Android NDK, JDK



### 1.2 JDK安装

本例使用jdk8成功

配置系统环境变量：

变量名：**JAVA_HOME**

变量值：C:\Program Files\Java\jdk1.8.0_144

变量名：**CLASSPATH**

变量值：.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar

注意%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar前面还有一个.;

在Path变量名中添加变量值：%JAVA_HOME%\bin



### 1.3安装Android SDK

http://tools.android-studio.org/index.php/sdk/

![img](https://img2022.cnblogs.com/blog/700384/202205/700384-20220512003154887-261112354.png)

首先Android SDK 检测 Java的安装位置

![img](https://img2022.cnblogs.com/blog/700384/202205/700384-20220512003346024-1128324273.png)

如果要让所有用户使用Android SDK，则要使用“管理员身份运行”打开SDK Manager.exe

![img](https://img2022.cnblogs.com/blog/700384/202205/700384-20220512012206705-613865720.png)

将保持默认的包都下载好

![img](https://img2022.cnblogs.com/blog/700384/202205/700384-20220512012249677-1144703992.png)



### 1.4 安装Android NDK

https://developer.android.google.cn/ndk/downloads/

![img](https://img2022.cnblogs.com/blog/700384/202205/700384-20220515000838629-1676003274.png)

本例使用该版本成功配置，下载完android-ndk-r18b-windows-x86_64.zip这个压缩包，直接解压就行

### 1.5 QT安装

对于QT的版本，我这里使用的是最新的5.12版本（带QT Creater5.12）

下载：http://download.qt.io/archive/qt/5.12/5.12.0/

安装可参考：https://blog.csdn.net/gaojixu/article/details/82185694

### 2.1Qt Creater中配置Android

打开Qt Creater，菜单[工具]->[选项]->[设备]-“Android”以及“设备”，填写各项如下：

![img](https://img2018.cnblogs.com/blog/1012444/201907/1012444-20190718113445677-1671075146.png)

![img](https://img2018.cnblogs.com/blog/1012444/201907/1012444-20190718113515764-252234707.png)

正确配置应用后，转到“Kits”中可以看到已经可以吧构建Android的套件显示出来了。

![img](https://img2018.cnblogs.com/blog/1012444/201907/1012444-20190718113536217-206032550.png)



创建一个qt quick项目

执行build...

成功后在build-HelloQtOnAndroid-Android_for_armeabi_v7a_Clang_Qt_5_12_0_for_Android_ARMv7-Debug

\android-build\build\outputs\apk\debug中找到生成的apk文件，安装测试即可！