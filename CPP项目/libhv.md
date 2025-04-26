## 名称由来
libhv是一个类似于libevent、libev、libuv的跨平台网络库，提供了带非阻塞IO和定时器的事件循环。
libhv的名称也正是继承此派，寓意高性能的事件循环High-performance event loop library。

## ibhv能干什么
编写跨平台c/c++程序；
基于TCP/UDP/SSL开发自定义协议网络程序；
编写HTTP客户端/服务端程序；
编写WebSocket客户端/服务端程序；
学习实践网络编程；
## libhv和libevent、libev、libuv有什么不同
libevent最为古老、有历史包袱，bufferevent虽为精妙，却也难以上手；
libev可以说是libevent的简化版，代码极为精简，但宏定义用的过多，代码可读性不强，且在Windows上实现不佳；
libuv是nodejs的c底层库，最先也是由libevent+对Windows IOCP支持，后来才改写自成一体，同时实现了管道、文件的异步读写，很强大，但结构体比较多，封装比较深；
libhv本身是参考了libevent、libev、libuv的实现思路，它们的核心都是事件循环（即在一个事件循环中处理IO、定时器等事件），但提供的接口最为精简，API接近原生系统调用，最容易上手；
具体这几个库的写法比较见echo-servers，可见libhv是最简单的；
此外libhv支持心跳、转发、拆包、多线程安全write和close等特性，提供了HTTP、WebSocket等协议实现；
当然这几个库的性能是接近的，都将非阻塞IO多路复用用到了极致;
## 编译与安装
libhv 提供了 Makefile 和cmake 两种构建方式
