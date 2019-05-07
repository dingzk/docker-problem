##### 症状
####### docker rm -fv pcweb
####### Error response from daemon: Driver overlay2 failed to remove root filesystem b8ff7b0d7abbe95de77bf743f867a7093c05d92f0660eb44f8af4168833dba35: remove /var/lib/docker/overlay2/bcfde8e8651781b3162ffc2fd2cd5a7cfcf29ee2b68919eca36be9fce412b640/merged: device or resource busy 

##### 挂载文件没有删除干净
-  查看所有挂载的设备: grep docker /proc/*/mountinfo
-  grep docker /proc/*/mountinfo |grep bcfde8e8651781b3162ffc2fd2cd| awk -F':' '{print $1}' | awk -F'/' '{print $3}'
- kill掉该pid
- ref : https://blog.csdn.net/m0_37886429/article/details/81700433


