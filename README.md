# Hadoop

Hadoop :Apache Hadoop is an open-source software framework written in Java for distributed storage and distributed                      processing of very large data sets on computer clusters built from commodity hardware.  


==========================================>Hadoop Installation
Download Hadoop: 

    Step 1: http://www.cloudera.com/content/cloudera/en/downloads/quickstart_vms/cdh-5-4-x.html
            Choose the required version of Hypervisor(VMware)
    
    Step 2: https://my.vmware.com/web/vmware/info/slug/desktop_end_user_computing/vmware_fusion/7_0
            Download fusion 
    
    Step 3: Unzip the cloudera VM 
    
    Step 4: Run the File : cloudera-quickstart-vm-5.4.0-0-vmware.vmx // open this file using fusion.
    
    Step 5: hadoop version in the termial to check if hadoop is installed 
    
    You have successfully installted the CentOS VM with Hadoop pre installed.
    
    
    
==============================================>Sqoop Installation

Sqoop: To transfer Relational data to Hadoop File System
        First check if you have SQL running.
        
    Step 1: Downloading Sqoop:
           link: https://archive.apache.org/dist/sqoop/1.4.5/
           Download the sqoop-1.4.5.bin__hadoop-2.0.4-alpha.tar.gz.
     
    Step 2: extract the compressed file and move sqoop to the folder /usr/lib/sqoop
            $tar -xvf sqoop-1.4.4.bin__hadoop-2.0.4-alpha.tar.gz
            $ su
            password://Specify your password here
           # mv sqoop-1.4.4.bin__hadoop-2.0.4-alpha /usr/lib/sqoop
           #exit 
    
    Step 3: Configuring bashrc: All the following lines to the file: ~/.bashrc 
           
            #Sqoop
            export SQOOP_HOME=/usr/lib/sqoop export PATH=$PATH:$SQOOP_HOME/bin
   
    Step 4: Configuring Sqoop
         
         $ cd $SQOOP_HOME/conf
         $ mv sqoop-env-template.sh sqoop-env.sh
         
         Open sqoop-env.sh and edit the following lines:
         
         export HADOOP_COMMON_HOME=/usr/local/hadoop 
         export HADOOP_MAPRED_HOME=/usr/local/hadoop
         
    Step 5: Download and Configure mysql-connector-java and  move the mysql-connector-java-5.1.30-bin.jar file to              /usr/lib/sqoop/lib
        Link: http://ftp.ntu.edu.tw/MySQL/Downloads/Connector-J/ 
        download : mysql-connector-java-5.1.30.tar.gz
   
    Step 6: Verify the version of Sqoop :
        $cd $SQOOP_HOME/bin
        $sqoop-version

=======================================>Transfering data from MySql to HDFS via Scoop Installation
    
    Mysql is running on the local host and Hadoop on the Virtual Machine
    
    Step 1: Grant all permissions to the user in MySql
            command : GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION; // root is the username
    Step 2: Get the Ip address of the machine: 
            ifconfig  => copy the ipaddress./
    Step 3: Transfer data
         command: sqoop import --connect jdbc:mysql://x.x.x.x:3306/employees --username root --table contacts 
         database name : employees
         database user name : root
         table name : contacts
         
         


  
