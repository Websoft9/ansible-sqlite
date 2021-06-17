# 服务启停

使用由Websoft9提供的 SQLite 部署方案，可能需要用到的服务如下：

### CloudBeaver

```shell
sudo docker start cloudbeaver
sudo docker stop cloudbeaver
sudo docker restart cloudbeaver
sudo docker stats cloudbeaver
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

### Docker-compose 服务

```
#创建容器编排
sudo docker-compose up

#创建容器编排并重建有变化的容器
sudo docker-compose up -d

#启动/重启
sudo docker-compose start
sudo docker-compose stop
sudo docker-compose restart
```