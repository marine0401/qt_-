将对某个文件IO设置为非阻塞式的两种方法



第一

在open函数中 ，添加O_NONBLOCK 



第二

先通过fcntl获取文件的flag，在原有的基础上添加O_NONBLOCK标志，然后在设置到文件中。



例如：

`int flag = - 1`

`flag = fcntl(0,F_GETFL);`

`flag |= O_NONBLOCK;`

`fcntl(0,F_SETFL,flag);`



其中，0是标准输入的文件描述符，也就是键盘输入





IO多路复用

select 

poll



外部阻塞式，内部非阻塞式自动轮询多路阻塞式IO



