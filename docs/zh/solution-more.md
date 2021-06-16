# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 程序连接

开发需要连接 SQLite，首先需要保证已经安装了对应的 SQlite 连接模块：

* PHP 默认安装并启用了 SQLite 扩展
* Python  默认安装了 SQLite 模块
* Java 需自行安装[SQLite JDBC Driver](https://github.com/xerial/sqlite-jdbc/releases)

下面是一个典型的 PHP 连接 SQLite 的程序段：

```
<?php
   class MyDB extends SQLite3
   {
      function __construct()
      {
         $this->open('test.db');
      }
   }
   $db = new MyDB();
   if(!$db){
      echo $db->lastErrorMsg();
   } else {
      echo "Opened database successfully\n";
   }
?>
```