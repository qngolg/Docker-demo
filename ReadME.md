# Docker入门

## Docker简介

### 什么是 Dokcer

Docker最初是dotCloud公司创始人 Solomon Hykes在法国期间发起的一个公司内部项目，它是基于dotCloud公司多年云服务技术的一次革新，并与2013年以Apache2.0 授权协议开源，主要项目代码在[Github][https://github.com/moby/moby] 上进行维护。Docker项目后来还加入了Linux基金会，并成立推动开发容器联盟(OCI)。

Docker自开源后受到广泛的关注和讨论，在2013年底，dtoCloud公司决定改名为Docker。 Docker最初是在Ubuntu 12.04上开发实现的；Red Hat则从RHEL6.5开始对Docker进行支持；Google也在其Pass产品中广泛应用Docker。

Docker使用Google公司推出的Go云烟进行开发实现，基于Linux内核的cgroup,namespace，以及AUFS类的Union FS等技术，对进程进行封装隔离，属于[操作系统层面的虚拟化技术][https://en.wikipedia.org/wiki/OS-level_virtualisation] 。由于隔离的进程独立于宿主和其他的隔离的进程，因此也称其为容器。最初实现是基于LXC,从0.7版本以后开始去除LXC,转而使用自行开发的libcontainer，从1.11开始，则进一步演进为使用runC和containerd。

Docker在容器的基础上，进行了进一步的封装，从文件系统、网络互连到进程隔离等等，极大的简化了容器的创建和维护。使得Docker技术比虚拟机技术更为轻便、快捷。

下面的图片比较了Docker和传统虚拟化方式的不同之处。传统虚拟化技术是虚拟出一套硬件后，在其上运行一个完整的操作系统，在该系统上再运行所需的应用进程；而容器内的应用进程直接运行于宿主的内核，容器内没有自己的内核，而且也没有进行硬件虚拟。因此容器要比传统虚拟机更为轻便。

![传统虚拟化](_images/virtualization.png)      								图1.4.1.1 - 传统虚拟化

![传统虚拟化](_images/docker.png)      								图1.4.1.2 - Docker

