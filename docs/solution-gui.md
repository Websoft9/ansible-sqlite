# Web-based GUI

This deployment solution of SQLite includes web-based GUI tool `CloudBeaver`. 

We will show you how to manage SQLite by CloudBeaver below:  

## Prepare

1. Use **SSH** to connect SQLite instance and create a database at: */data/apps/cloudbeaver/volumes* 
   ```
   # Create database file
   cd /data/apps/cloudbeaver/volumes
   sqlite3 testDB.db
   
   # Add a table
   sqlite> CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
   )
   ```

2. Login your Cloud Platform, and Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:9090** is allowed.

3. Complete [CloudBeaver installation wizard](https://support.websoft9.com/docs/cloudbeaver/stack-installation.html)


## Connect Database

Let's start to connect SQLite if we complete preparation:  

1. Login to CloudBeaver console and open: 【Connection】>【Manual】, select **SQLite**
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/cloudbeaver/cloudbeaver-openconn-websoft9.png)

2. Configure it as below and click 【Save】 button

   - **Driver** is SQLite by default
   - **Connection Name** can by any name if you want
   - **Database** must use the path as: */data/apps/cloudbeaver/volumes*

   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/cloudbeaver/cloudbeaver-openconnsqlite-websoft9.png)

3. Start to enable SQLite connection, you may need to input database username and password
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/cloudbeaver/cloudbeaver-conlogin-websoft9.png)

4. You can see the table you created when you connect SQLite successfully
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/cloudbeaver/cloudbeaver-listtable-websoft9.png)