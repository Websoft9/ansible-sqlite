# 故障处理

此处收集使用 SQLite 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### 如何查看错误日志？

日志文件路径为：`/data/logs`。检索关键词 **Failed** 或者 **error** 查看错误

#### SQLite服务使用？

服务无法使用最常见的问题包括：磁盘空间不足，内存不足，配置文件错误。  
建议先通过命令进行排查  

```shell
# 查看磁盘空间
df -lh

# 查看内存使用
free -lh
```

#### CloudBeaver 无法连接 SQLite 数据库？

确保 SQLite 数据库文件存放在： */data/apps/cloudbeaver/volumes* 目录下，如果不在此目录，CloudBeaver 便无法管理。
