# 图形化工具

本部署方案中预装 SQLite 数据库管理工具 `CloudBeaver` 。  

下面我们完成的介绍如何使用可视化工具管理 SQLite。

## 准备

1. 使用 SSH 连接 SQLite 所在的服务器，在 */data/apps/cloudbeaver/volumes* 目录下创建一个数据库
   ```
   # 创建数据库
   cd /data/apps/cloudbeaver/volumes
   sqlite3 testDB.db
   
   # 增加表
   sqlite> CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
   )
   ```

2. 登录云控制台，开启服务器 [安全组 9090 端口](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

3. 完成 [CloudBeaver 初始化](https://support.websoft9.com/docs/cloudbeaver/zh/stack-installation.html)安装


## 配置

完成上述准备工作后，我们开始连接 SQLite 数据库：  

1. 登录 CloudBeaver 控制台，打开：【Connection】>【Manual】，选择 **SQLite**
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/cloudbeaver/cloudbeaver-openconn-websoft9.png)

2. 参考下面的建议，设置连接信息，然后点击【Save】

   - Driver 保持默认的 SQLite
   - Connection Name 设置为一个便于识别的名字即可
   - Database 为 SQLite 数据库文件的路径，路径前缀必须是：**/opt/cloudbeaver/workspace/**，再接上文件名称

   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/cloudbeaver/cloudbeaver-openconnsqlite-websoft9.png)

3. 设置信息保存后，使用这个 SQLite 连接，输入数据库的账号和密码
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/cloudbeaver/cloudbeaver-conlogin-websoft9.png)

4. 成功连接到 SQLite，发现可以看到之前创建的 Company 表
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/cloudbeaver/cloudbeaver-listtable-websoft9.png)