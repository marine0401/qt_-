#### Ubuntu18.0.4 出现 qt.qpa.xcb: could not connect to display错误





```
export QT_QPA_PLATFORM='offscreen'
```

在rk3568没有装屏幕的情况下，使其平台配置为这个。

