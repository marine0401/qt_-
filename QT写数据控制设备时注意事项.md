QT写数据控制设备时注意事项

1.打开文件时要添加QIODevice::Unbuffered

例：

m_file->open(QIODevice::ReadWrite|QIODevice::Text|QIODevice::Unbuffered);

