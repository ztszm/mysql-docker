![logo](https://www.mysql.com/common/logos/logo-mysql-170x115.png)

# What is MySQL Shell?

MySQL Shell is the new client made to be used with MySQL's X Plugin, which enables MySQL to function as a document store. More information about this is available at https://dev.mysql.com/doc/refman/5.7/en/document-store.html

MySQL Shell is still in alpha, and this image is meant for previewing upcoming features.

# Enabling mysqlx plugin on server

To use the new features of the X Plugin it must first be enabled on the server

To use the Shell image to enable the plugin, it can be started with the init command:

 docker run -it -e MYSQL_HOST=mysqlhostname mysql-shell init

You will be asked to enter the password for the server's root user. You should see the a message
that the mysqlx plugin has been installed. This only needs to be done the first time.

# Connecting to mysqlx-enabled server

To connect to the server, simply run the mysql-shell image the same way you would start a normal MySQL client:
 
 docker run -it mysql-shell -u <username> -h mysqlhostname

Once logged in, if you run \status, you should see «Session type: X>

# Using MySQL Shell

For information on how to use MySQL Shell, refer to the user guide at htps://dev.mysql.com/doc/refman/5.7/en/mysql-shell.html

# Supported Docker Versions

These images are officially supported by the MySQL team on Docker version 1.9. Support for older versions (down to 1.0) is provided on a best-effort basis, but we strongly recommend running on the most recent version, since that is assumed for parts of the documentation above.

# User Feedback

We welcome your feedback! For general comments or discussion, please drop us a line in the Comments section below. For bugs and issues, please submit a bug report at http://bugs.mysql.com under the category "MySQL Package Repos and Docker Images".
