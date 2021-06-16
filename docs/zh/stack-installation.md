# 初始化验证

在云服务器上部署 SQLite 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:9090** 端口是否开启
3. 若想用域名访问 SQLite，请先到 **域名控制台** 完成一个域名解析

## SQLite 初始化验证

1. 使用 SSH 工具，连接到服务器

2. 运行 `sqlite3` 命令，显然类型下面的结果，即表明运行正常
   ```
   [root@VM-0-11-centos ~]# sqlite3
   SQLite version 3.29.0 2019-07-10 17:32:03
   Enter ".help" for usage hints.
   Connected to a transient in-memory database.
   Use ".open FILENAME" to reopen on a persistent database.
   sqlite>
   ```

3. 验证 [SQLite 可视化](/zh/solution-gui.md)管理工具

> 需要了解更多 SQLite 的使用，请参考官方文档：[SQLite Documentation](https://www.sqlite.com/documentation.html)

## SQLite 入门向导

现在开始针对于如何使用 SQLite 创建和管理数据库，进行完整的说明：

## 常见问题

#### 浏览器打开IP地址，无法访问 SQLite（白屏没有结果）？

您的服务器对应的安全组 9090 端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### SQLite 有系统服务吗？

没有
