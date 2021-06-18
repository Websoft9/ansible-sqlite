# Initial Installation

If you have completed the SQLite deployment, follow the steps below to start a quick use.

## Preparation

1. Get the **Server's Internet IP** of Server on your Cloud Platform.
2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:9090** is allowed.
3. Make a domain resolution on your Cloud Console if you want to use domain for SQLite.

## SQLite Verification Wizard

1. Use **SSH** tool to connect Instance

2. Running the command `sqlite3`, you can see the below information
   ```
   [root@VM-0-11-centos ~]# sqlite3
   SQLite version 3.29.0 2019-07-10 17:32:03
   Enter ".help" for usage hints.
   Connected to a transient in-memory database.
   Use ".open FILENAME" to reopen on a persistent database.
   sqlite>
   ```
3. Verify [SQLite Web-based GUI](/solution-gui.md) tool

> More guide about SQLite, please refer to [SQLite Documentation](https://sqlite.org/docs.html).

## SQLite Setup wizard

Coming soon...

## Q&A

#### Can't visit the start page of SQLite GUI?

Your TCP:9090 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.

#### Is there system service for SQLite?  

No
