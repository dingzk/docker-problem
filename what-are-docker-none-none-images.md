##### what-are-docker-none-none-images

> [http://www.projectatomic.io/blog/2015/07/what-are-docker-none-none-images/](http://www.projectatomic.io/blog/2015/07/what-are-docker-none-none-images/)
>
> https://blog.51cto.com/13954634/2294107
>
> [http://dockone.io/article/3056](http://dockone.io/article/3056)



**查看 docker 占用的资源**
在进行资源清理之前我们有必要搞清楚 docker 都占用了哪些系统的资源。这需要综合使用不同的命令来完成。

docker container ls：默认只列出正在运行的容器，-a 选项会列出包括停止的所有容器。
docker image ls：列出镜像信息，-a 选项会列出 intermediate 镜像(就是其它镜像依赖的层)。
docker volume ls：列出数据卷。
docker network ls：列出 network。
docker info：显示系统级别的信息，比如容器和镜像的数量等。

Docker 提供了方便的 docker system prune 命令来删除那些已停止的容器、dangling 镜像、未被容器引用的 network 和构建过程中的 cache

dangling images : 可以简单的理解为未被任何镜像引用的镜像，比如在你重新构建了镜像后，那些之前构建的且不再被引用的镜像层就变成了 dangling images，使用 -a 参数，你还会发现另外一种类型的 <none> 镜像，它们的 repository 和 tag 列都表现为 <none>，这些镜像被称为 intermediate 镜像(就是其它镜像依赖的层)。

docker container prune # 删除所有退出状态的容器
docker volume prune # 删除未被使用的数据卷
docker image prune # 删除 dangling 或所有未被使用的镜像

**只删除那些未被使用的资源**
Docker 提供了方便的 docker system prune 命令来删除那些已停止的容器、dangling 镜像、未被容器引用的 network 和构建过程中的 cache