OSI七层模型
物理层
数据链路层 mac
网络层  ip层,icmp,arp rarp
传输层  tcp/udp
会话层
表示层
应用层

UDP
udp是无连接网络通讯方式，处于OSI模型的传输层

流程
服务器：
建立socket ----- 绑定端口号bind ----- 接收数据 recvfrom

客户端：
建立socket ----- 发送数据 send 


TCP
tcp是长连接通讯方式，传输层，三次握手，4次挥手
服务器：
建立socket ---- 绑定端口号bind  ----监听连接listen ---- 接收连接accept ---- 读取数据read

客户端:
建立socket ----- 发起连接connect ----- 发送数据send

三次握手
第一次握手：建立连接时，客户端发送syn包到服务器，等待服务器确认
第二次握手：服务器收到syn包，发送syn包回复客户端
第三次握手：客户端收到syn包，回复ack给服务器







