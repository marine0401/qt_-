yolov8pose自定义训练部署rk3568



1模型训练

​	参考开源的yolov8pose训练代码

​	可修改关键点个数

​	训练后得到pt文件

2 进行预测，将pt只保存权重

在ultralytics/engine/model.py

_load函数末尾添加

`import torch
self.model.fuse()
self.model.eval()
torch.save(self.model.state_dict(), './weights/yolov8pos_relu_dict.pt')
`



然后运行以下代码

```
model = YOLO('./weights/yolov8pos_relu.pt')
results = model(task='pose', mode='predict', source='./images/test.jpg', line_width=3, show=True, save=True, device='cpu')
```

3

修改检测头

![在这里插入图片描述](https://img-blog.csdnimg.cn/4d720ed807174b3f934b358f10b6f35a.png)

修改pose头

![在这里插入图片描述](https://img-blog.csdnimg.cn/273ccda7ed274817a9697f4b6da78ccd.png)



添加生成onnx代码



![在这里插入图片描述](https://img-blog.csdnimg.cn/ead90f634b0649c198717f1368495da3.png)

然后执行以下代码，导出onnx

```
model = YOLO('./ultralytics/models/v8/yolov8-pose.yaml')
```

