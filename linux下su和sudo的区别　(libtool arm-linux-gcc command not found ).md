# linux下su和sudo的区别　(/libtool: arm-linux-gcc command not found )



su 和 sudo 的区别：
  1.共同点：都是root用户的权限；
  2.不同点：su仅仅取得root权限，工作环境不变，还是在切换之前用户的工作环境；sudo是完全取得root的权限和root的工作环境。

我编译碰到的问题是：./libtool: arm-[linux](https://so.csdn.net/so/search?q=linux&spm=1001.2101.3001.7020)-gcc: command not found

解决如下：

解决如下：
  执行make 之前，先用下su - 命令取得root权限。然后再执行make 。