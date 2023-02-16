# mysql_master

**#Create user on docker mysql master**

`CREATE USER 'USER'@'%' IDENTIFIED WITH mysql_native_password BY 'PASSWORD';`

`GRANT ALL PRIVILEGES ON *.* TO 'USER'@'%';`

`FLUSH PRIVILEGES;`

`show grants for 'USER'@'%';`

#execute command on mysql master

`SHOW MASTER STATUS;`

**File          |      Position**

**binlog.000001 |      156	**




**#execute command on  mysql slave**

`docker exec -it mysql_slave bash`

`mysql -uroot -p `

`stop slave;`

`CHANGE MASTER TO MASTER_HOST='IP_Server_Master', MASTER_PORT=Port_Mysql, MASTER_USER='USER', MASTER_PASSWORD='PASSWORD', MASTER_LOG_FILE='mysql-bin.000001', MASTER_LOG_POS=156;`

`start slave;`

`show slave status\G`
