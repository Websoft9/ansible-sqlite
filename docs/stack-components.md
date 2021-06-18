# Parameters

The SQLite deployment package contains a sequence of software (referred to as "components") required for SQLite to run. Below list the important information, the component name, installation directory path, configuration file path, port, version, etc.

## Path

This solution use Docker to deploy all service, you can run the command `docker ps` to list them  

### SQLite

SQLite bin file:  */usr/bin/sqlite3*  
SQLite db file path:  */data/apps/cloudbeaver/volumes*  

> SQLite db file can anywhere, but only */data/apps/cloudbeaver/volumes* can managed by GUI tool

### CloudBeaver

CloudBeaver is a web-based GUI tool for database, it installed by Docker  

CloudBeaver directory：*/data/apps/cloudbeaver*  
CloudBeaver docker compose file：*/data/apps/cloudbeaver/docker-compose.yml* 

### Docker

Docker root directory: */var/lib/docker*  
Docker image directory: */var/lib/docker/image*   
Docker daemon.json: please create it when you need and save to to the directory */etc/docker*   

## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet.  

You can run the cmd `netstat -tunlp` to check all related ports.  

The following are the ports you may use:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 9090 | HTTP to access CloudBeaver | Optional |

## Version

You can see the version on product pages at Marketplace. However, after being deployed to your server, the components will be updated automatically, resulting in a certain change in the version number. Therefore, run the command on the server to view the exact version number. 

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Docker Version
docker -v

# SQLite version
sqlite3 --version
```