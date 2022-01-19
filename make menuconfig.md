## make menuconfig

(1)可能出现的错误1：ncurses库没装
错误信息：
 *** Unable to find the ncurses libraries or the
 *** required header files.
 *** 'make menuconfig' requires the ncurses libraries.

***
 *** Install ncurses (ncurses-devel) and try again.

解决方案：  apt-get install libncurses5-dev （参考了：http://blog.csdn.net/yao_qinwei/article/details/8805101）

