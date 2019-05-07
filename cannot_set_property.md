##### 症状
- /usr/bin/docker-current: Error response from daemon: oci runtime error: container_linux.go:235: starting container process caused "process_linux.go:258: applying cgroup configuration for process caused \"Cannot set property TasksAccounting, or unknown property.\"".
- 内核版本: 3.10.0-514.6.2.el7.toa.2.x86_64
- docker -v : Docker version 1.13.1, build b2f74b2/1.13.1

##### 解决方案
- 直接升级docker版本
- ref : https://www.cnblogs.com/Dicky-Zhang/p/7693416.html
