目录结构
BasicUsageEnvironment 存放基本任务类
gtoupsock
hlsProxy
liveMedia             协议类
mediaServer
proxyServer
testProgs
UsageEnvironment


文件：RTCPClient.cpp
rtsp交互流程

客户端得到rtsp流地址后，向rtsp服务器发起tcp连接。
然后客户端发送OPTIONS指令，获取服务器所支持的方法。
客户端发送DESCRIBE指令，获取服务器的SDP信息，包含rtp的地址和端口，传输方式，音视频信息等
客户端发送SETUP指令，再这个过程中初始化RTP端口，音视屏解码器等工作，为接下来是音视频传输做准备，
客户端发送PLAY指令，服务器开始往RTP端口发送音视频流，客户端接收流后解码并显示，

RTP的乱序，丢包，抖动等问题解决
由于RTP一般使用UDP传输，属于不可靠连接，存在丢包，乱序，抖动等问题，因此RTP需要通过缓冲，乱序重排，重新请求关键帧等问题去改善音视频传输质量。

Live555库使用C++编程
主要类

主要函数

BasicTaskScheduler::createNew()                ------基本live555的基类，一些任务处理，sock创建维护，延时任务，函数回调都在这里处理
BasicUsageEnvironment::createNew()
env->taskScheduler().doEventLoop(）

RTSPClient -----rtsp客户端，客户端发送RTSP协议命令基本通过这个类完成
MediaSink  -----音视频的链接类，需要重写这个类去处理服务器给我们传输的音视频数据，这个非常重要！！！

rtspClient->sendDescribeCommand(continueAfterDESCRIBE); ----通过函数回调的方式获取服务器返回的信息






