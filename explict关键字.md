# explict关键字

取消隐式转换。

CString（int size）；为构造函数



加了explicit关键字后



CString string = 10；就无法成立，因为10是int类型，不能隐式转换后，类型不匹配，无法通过。



CString string1（24）；这样可以，调用构造函数将24作为行参传入。