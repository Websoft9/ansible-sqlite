# CLI

SQLite 提供了强大的的命令行工具 `sqlite3`  

## 程序命令行

```
# 创建数据库
sqlite3 testDB.db

# 查看帮助
sqlite3 --help

# 查看版本
sqlite3 --version
```

## 交互式命令行

以 `sqlite3 testDB.db` 命令，进入 SQLite 运行状态后，开始使用数据库交互式命令行

```
# 获取帮助
sqlite> .help

# 查询数据库列表
sqlite> .database

# 附件一个数据库。
# 数据库名称 main 和 temp 被保留用于主数据库和存储临时表及其他临时数据对象的数据库，不可用于附加
sqlite> ATTACH DATABASE 'myDB.db' as 'TEST'

# 创建表
sqlite> CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
)

# 查询表
sqlite> .tables

```