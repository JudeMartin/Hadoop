# Hadoop

Sqoop: To transfer Relational data to Hadoop File System
        First check if you have SQL running.

    Step 1: Grant all permissions to the user in MySql
            command : GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION; // root is the username
    
    Step 2: Get the Ip address of the machine: 
            ifconfig  => copy the ipaddress./
    
    Step 3: Transfer data;
         command: sqoop import --connect jdbc:mysql://x.x.x.x:3306/employees --username root --table contacts 
         database name : employees
         database user name : root
         table name : contacts
         
         
