exec函数族



会替换当前进程，转而执行传入的程序



有六个函数

execl

execlp

execlpe

execv

execvp

execvpe





其中  l和v的区别是，两种函数传参方式不同，l就是list，用的参数列表的形式传参

v是vector，用一个数组来接收参数，然后传入函数。



p就是PATH，指可以在环境变量PATH中查找该程序文件



e就是environ，函数可以多传入一个环境变量列表