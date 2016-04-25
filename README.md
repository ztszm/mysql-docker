![logo](https://www.mysql.com/common/logos/logo-mysql-170x115.png)

# What is MySQL Shell?

MySQL Shell is a new command line client that supports interaction with MySQL Server through Javascript, Python and SQL. It covers the same area of usage as the `mysql` command line client, so you can use it to to perform classical relational SQL operations, while introducing a whole new area of functionality to query, update and manage MySQL as a document store, using popular scripting languages. More information about MySQL's new document store functionality is available at https://dev.mysql.com/doc/refman/5.7/en/document-store.html

MySQL Shell is currently in alpha, and this Docker image is meant only for the purpose of previewing upcoming features.

# Enabling the mysqlx plugin on the MySQL server

The new document store features of MySQL are implemented as a plugin to MySQL Server. This plugin needs to be enabled on the server before you can use the shell to access the new functionality. This needs to be done only once: the server will remember this setting on restart.

Invoke the shell as follows:

    docker run -it -e MYSQL_HOST=<hostname> mysql-shell init

You will be asked to enter the password for the server's root user. You should see a message that the mysqlx plugin has been installed.

# Connecting to mysqlx-enabled server

To connect to the server, simply run the mysql-shell image the same way you would start a normal MySQL client:
 
    docker run -it mysql-shell -u <username> -h <hostname>

Once logged in, if you run `\status`, the shell should respond with `Session type: X`.

# Using MySQL Shell

For information on how to use MySQL Shell, refer to the user guide at https://dev.mysql.com/doc/refman/5.7/en/mysql-shell.html

# Supported Docker Versions

These images are officially supported by the MySQL team on Docker version 1.11. Support for older versions (down to 1.0) is provided on a best-effort basis, but we strongly recommend running on the most recent version, since that is assumed for parts of the documentation above.

# User Feedback

We welcome your feedback! For general comments or discussion, please drop us a line in the Comments section below. For bugs and issues, please submit a bug report at http://bugs.mysql.com under the category "MySQL Package Repos and Docker Images".
