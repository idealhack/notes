# Docker Internals

## 内核

- 通过 namespace 实现资源隔离
- 通过 cgroups 实现资源限制
- 通过写时复制（copy-on-write）实现高效文件操作

## namespace

namespace | 系统调用参数 | 隔离内容
UTS | CLONE_NEWUTS | 主机与域名
IPC | CLONE_NEWIPC | 信号量、消息队列和共享内存
PID | CLONE_NEWPID | 进程编号
Network | CLONE_NEWNET | 网络设备、网络栈、端口等
Mount | CLONE_NEWNS | 挂载点（文件系统）
User | CLONE_NEWUSER | 用户和用户组

## cgroups

### 术语

- task（任务）：系统的一个进程或线程
- cgroup（控制组）：按某种资源控制标准划分的任务组，包含一个或多个子系统
- subsystem（子系统）：资源调度控制器，例如 CPU 或内存子系统分别控制 CPU 时间和内存使用量
- hierarchy（层级）：一系列 cgroup 以树状结构排列而成，每个层级通过绑定对应子系统进行资源限制，子节点继承父节点挂载的子系统

### 作用

- 资源限制
- 优先级分配
- 资源统计
- 任务控制

### 特点

- API 以伪文件系统方式实现，可在用户态通过文件操作实现组织管理
- 操作单元可以细粒度到线程级别，用户可以创建和销毁控制组从而实现资源再分配
- 所有功能都以子系统方式实现，接口统一
- 子任务创建之初与其父任务处于同一个控制组

## Resources

- [Docker 核心技术与实现原理](https://draveness.me/docker)
- [Docker底层技术 - 简书](https://www.jianshu.com/p/7a1ce51a0eba)
- [Linux容器技术演化史](https://mp.weixin.qq.com/s?__biz=MzIzNjUxMzk2NQ==&mid=2247485792&idx=1&sn=c06e97a8e5a91591a3d327a36320d56c)
