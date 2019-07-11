# beluga (a simple C++ network library) 

# Introduction
beluga是一款小型的C++网络库，支持高并发，多线程，用于实现高性能网络服务。
# Technical points

# Build

# HCCServer

1. Buffer的设计
2. 定时定量发送
    基于time_fd定期刷新发送缓冲区，如果到达间隔时间或者
    缓冲区长度超过一半就开始监听写入事件
3. 线程池
4. 内存池，动态扩容机制，扩容过程无需拷贝
5. 双任务队列，实现任务处理优先级
6. 心跳检测，时间轮
7. epoll机制
8. 线程分发,基于小根堆,每次添加连接时首先make_heap
9. 添加任务处理优先级2
10.通过BigBuffer对象池来实现快速日志写入，支持定时定量写入
通过