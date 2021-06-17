# FAQ

#### SQLite 是否支持用户名和密码验证？

不支持

#### 本项目中 SQLite 采用何种安装方式？

采用编译安装

#### 是否可以通过命令行修改SQLite后台密码？

可以，`sqlitectl change_password  admin newpassword`

#### 是否有可视化的数据库管理工具？

有，内置 CloudBeaver，访问地址：*http://服务器公网IP:9090*

#### 如何才能使用 CloudBeaver 管理 SQLite 数据库？

只要 SQLite 数据库文件存放在 */data/apps/cloudbeaver/volumes* 目录下，CloudBeaver 就可以管理到它们。

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R apache.apache /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
