# Decommissioning datanodes in Hadoop cluster

Decommissioning process of the data node ensures that data is transferred to other nodes so that the existing replication factor is not disturbed.

## Update dfs.exclude file

    $ vi /etc/hadoop/conf/dfs.exclude
    bee2-vpn

## Run refreshNodes command

    $ sudo -u hdfs hdfs dfs -refreshNodes
