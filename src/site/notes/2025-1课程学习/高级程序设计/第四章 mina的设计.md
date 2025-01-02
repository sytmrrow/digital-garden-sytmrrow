---
{"dg-publish":true,"tags":["信管课程"],"permalink":"/2025-1课程学习/高级程序设计/第四章 mina的设计/","dgPassFrontmatter":true,"created":"2025-01-01T17:18:24.260+08:00","updated":"2025-01-02T14:32:16.252+08:00"}
---

# 一、MINA的优势
高性能，可以与多种企业级开发框架集成，大厂在用，提供网络通讯框架

# 二、MINA基于NIO
传统的IO（inputStream+outputStream+数组）弊端
（1）需自定义数组的使用方式，存在多线程安全，多线程冲突，内存冲突多线程管理问题
（2）阻塞机制，传统IO在遇到读取/写入操作时，在真正读取到东西或者完全写入之前不能进行其他的任何操作，主线程挂起，但是nio可以进行其他操作
（3）多通道管理，nio可以由单线程进行多通道管理，可以在单线程中监听并通过注册一个selector管理多个通道（单路复用）

# 三、MINA设计
client到server完整通路
client-buffer-channel-channel-buffer-server
channel是连接不同硬件设备或数据源的通路，实现数据的传输
buffer是数据的缓冲区（字节的缓冲区），实现传输管理和数据的逻辑操作
channel和buffer之间是双向传输的
CPU将buffer中的数据通过channel进行传输，同时也向channel要求返回数据

mina的单路复用的操作
首先mina有一个serverSocket进行连接监听，当出现连接时，构建一个channel，并将这个channel注册在selector中，之后selector对channel进行轮询，轮询之后，如果存在需要进行的io读写操作就进行io读写操作（需要注意序列化/反序列化操作的时机），再进行具体的业务逻辑处理。

mina支持tcp与UDP的协议，同时注意序列化和反序列化（mcpack或者protobuffer)，这是niosocket非阻塞的通讯

# 四、MINA线程及启动过程
MINA的线程
IOservice：进行连接操作
<span style="background:#fff88f"><font color="#c00000">ioprocessor</font></span>：io事件管理器，负责管理io事件，包括selector,buffer,channel综合使用单路复用机制与线程池
iosession:这里是执行具体的io的读取或者写入的操作
iohandler：具体的业务处理

启动过程
计算资源分配：buffer分配
初始化通道和管理器：channel，selector
初始化连接和序列化反序列化相关
初始化client端和server端相关服务：连接-Factory-encoder/decoder-handle
配置文件

# 五、MINA涉及的高级程序设计相关
反射（基于类加载）
注解
多线程
队列
网络通信
序列化协议

# 六、总结


