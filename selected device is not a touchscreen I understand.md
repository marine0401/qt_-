# selected device is not a touchscreen I understand 

错误的原因有各式各样，这里仅以我自己遇到的问题记录：

第一种原因是： 内核和交叉编译器的EV_VERSION值不一样，修改一下就可以

内核：我的在目录 /x210kernel/include/linux/input.h 

#define EV_VERSION        0x010001





解决方法： 只需要将内核的

*#define EV_VERSION    0x010001 改为*

*#define EV_VERSION    0x010000*