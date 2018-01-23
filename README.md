# Docker-Keepalived-Nginx
利用docker快速构建Nginx+Keepalived双主集群实现负载均衡

**目录结构：**

- node_1 
  - docker-compose.yml
  - Dockerfile
  - keepalived.conf
  - nginx.conf
- node_2 同上

分别用于部署在两台不同的服务器上

**使用简介：**

- nginx.conf

  配置nginx以实现负载均衡，node_1和node_2一般情况下相同

- keepalived.conf

  默认使用双BACKUP，nopreempt非抢占模式，根据需要修改

  - interface
  - auth_pass
  - unicast_peer
  - virtual_ipaddress

- docker-compose

  修改宿主机和nginx容器的端口映射

拷贝修改后的node_1和node_2到宿主机，进入目录执行

```shell
docker-compose up
```







