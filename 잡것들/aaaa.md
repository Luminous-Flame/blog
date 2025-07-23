





master_ip_failover_script=/masterha/scripts/master_ip_failover_tgzdb
master_ip_online_change_script=/masterha/scripts/master_ip_online_change_tgzdb


GRANT ALL PRIVILEGES ON *.* TO 'mha'@'10.3.4.60' IDENTIFIED BY 'anjffhgkfRk?' WITH GRANT OPTION; 


CHANGE MASTER TO MASTER_HOST='10.1.1.122', MASTER_PORT=3306, MASTER_LOG_FILE='mysql-bin.000009', MASTER_LOG_POS=374, MASTER_USER='repl', MASTER_PASSWORD='repl';

start slave;



CHANGE MASTER TO MASTER_HOST='10.1.1.121', MASTER_PORT=3306, MASTER_LOG_FILE='mysql-bin.000011', MASTER_LOG_POS=374, MASTER_USER='repl', MASTER_PASSWORD='repl';