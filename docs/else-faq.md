# FAQ

#### Does SQLite need username and password?

No

#### What is the installation method of SQLite in this project?

Make

#### How can I use CloudBeaver to manage SQLite databases?

CloudBeaver just only manage database in the directory: */data/apps/cloudbeaver/volumes*

#### Is there a web-base GUI database management tool?

Yes, CloudBeaver is included. Visit by *http://Server's Internet IP:9090*.

#### How to change the permissions of filesystem?

Change owner(group) or permissions as below:

```shell
chown -R apache.apache /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a series of software to the server in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference. All refer to cloud servers. They are the different terminology used by manufacturers.