# QT跨线程调用Socket

继承QTcpServer，重写incommingconnection函数，将该函数的handle传递给子线程，在子线程中利用

`socket->setSocketDescriptor来创建Socket`,使其获得通信功能。

```
class MyServer : public QTcpServer
{
public:
    MyServer();
protected:
    virtual void incomingConnection(qintptr handle);
};


void MyServer::incomingConnection(qintptr handle)
{
    qDebug() << "helloWorld" << endl;


     MyWork *m_work= new MyWork(handle);
     QThread *temp = new QThread();
     m_work->moveToThread(temp);
     QObject::connect(temp,&QThread::started,m_work,&MyWork::work);


    QObject::connect(m_work,&MyWork::m_destroyed,[=](){
        temp->quit();
        temp->wait();
        qDebug() << "QThread Id " <<QThread::currentThreadId() <<"destroyed " << endl;
    });


    temp->start();
    qDebug() << m_work << endl;


}

```

