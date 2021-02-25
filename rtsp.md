
RTSP与HTTP类似，消息分为Request和Response

RTSP（实时流传输协议），端口默认为554，RTSP提供流媒体一个控制功能，主要音视频传输使用RTP协议，RTSP分为OPTIONS（客户端得到服务器的可用方法），DESCRIBE（得到服务器会话描述信息SDP，其中包含RTP的端口，IP信息等），SETUP（客户端与服务器确定传输方式），PLAY（客户端向服务器发起播放请求），PAUSE（客户端向服务器发起暂停请求）SCALE（快进快退）

流程：
客户端                               服务器
1、C->S 端口554建立连接，发送OPTIONS询问服务器可用方法，服务Response
2、C->S 发送Describe，得到服务器会话描述信息SDP，这里包含音视频流的格式，RTP传输方式，端口等信息
3、C->S 发送SETUP命令，与服务器确定传输方式，此时客户端准备好RTP接收，解码工作
4、C->S 发送PLAY命令，服务器通过RTP发送音视频流给客户端
5、C->S 发送TEARDOWN，结束此次播放
