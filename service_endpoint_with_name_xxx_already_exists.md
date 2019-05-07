#### 症状
##### 发现docker关闭后端口依然占用
#### 解决方案
> 清理此容器的网络占用 docker network disconnect --force 网络模式 容器名称
> 简查是否还有同名容器占用 docker network inspect 网络模式(net)
> ref: https://www.jianshu.com/p/bf7ae7919473

