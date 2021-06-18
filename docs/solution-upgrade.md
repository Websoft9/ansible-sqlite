# Update & Upgrade

To update and upgrade is one of the main task for system maintenance. Like buildings without maintenance for a long time, programs without upgrading will age faster, lose functionality until they are unavailable.

Get to know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Patching operating system is **Updating**, while Ubuntu16.04 to Ubuntu18.04 means **Upgrading**.
- MySQL5.6.25 to MySQL5.6.30 means **Updating**, yet MySQL5.6 to MySQL5.7 means **Upgrading**.

Maintenance for SQLite includes the following two tasks.

- Update system (Operating System and Runtime) 
- Upgrade SQLite

## Update System 

Run a command to complete updating the system:

``` shell
#For Ubuntu&Debian
sudo apt update && apt upgrade -y

#For Centos&Redhat
sudo yum update -y --skip-broken
```
> This deployment package is pre-configured with a scheduled task for automatic updating. If you want to remove the automatic updating, please delete the corresponding Cron.

## Upgrade SQLite

If there no newer rpm/deb package for you SQLite, you should update it as below steps:  

> You should complete an image or snapshot backup for instance before upgrade

1. Access the [Download](https://www.sqlite.org/chronology.html) URL of SQLite

2. Run these commands
   ```
   # Download sources of SQLite, the URL below only for your reference
   wget https://www.sqlite.org/2019/sqlite-autoconf-3290000.tar.gz

   # Make it
   tar zxvf sqlite-autoconf-3290000.tar.gz 
   cd sqlite-autoconf-3290000/
   ./configure --prefix=/usr/local
   make && make install
   
   # Replace the old version
   mv /usr/bin/sqlite3  /usr/bin/sqlite3_old
   ln -s /usr/local/bin/sqlite3   /usr/bin/sqlite3
   echo "/usr/local/lib" > /etc/ld.so.conf.d/sqlite3.conf
   sudo echo "/usr/local/lib" |tee /etc/ld.so.conf.d/sqlite3.conf
   ldconfig
   sqlite3 -version
   ```
