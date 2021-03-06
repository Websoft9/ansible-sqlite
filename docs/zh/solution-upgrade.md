# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：
- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- MySQL5.6.25-->MySQL5.6.30 常称之为**更新**，MySQL5.6->MySQL5.7 称之为**升级**

SQLite 完整的更新升级包括：系统级更新（操作系统和运行环境）和 SQLite 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级（包含SQLite小版本更新）更新：

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y --skip-broken
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron


## SQLite 升级

如果系统仓库中的 SQLite 版本比较低，又想升级到指定的版本，可以参考如下教程： 

> 升级之前请确保您已经完成了服务器的镜像（快照）备份

1. 找到所需 SQLite 目标版本的[下载地址](https://www.sqlite.org/chronology.html)

2. 分别运行如下的升级命令
   ```
   # 下载 SQLite 源码（自行替换）
   wget https://www.sqlite.org/2019/sqlite-autoconf-3290000.tar.gz

   # 编译
   tar zxvf sqlite-autoconf-3290000.tar.gz 
   cd sqlite-autoconf-3290000/
   ./configure --prefix=/usr/local
   make && make install
   
   # 替换旧版本
   mv /usr/bin/sqlite3  /usr/bin/sqlite3_old
   ln -s /usr/local/bin/sqlite3   /usr/bin/sqlite3
   echo "/usr/local/lib" > /etc/ld.so.conf.d/sqlite3.conf
   ldconfig
   sqlite3 -version
   ```