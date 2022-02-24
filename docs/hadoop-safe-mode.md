# How to leave Hadoop safe mode

The Hadoop cluster enters safe mode during the name node startup till the basic indicators are met and later in case of emergency, which means that the cluster enters read-only mode.

The client will immediately notice that the name node is in safe mode.

    $ hdfs dfs -copyFromLocal -f /var/log/syslog /logs/backup/
    copyFromLocal: Cannot create file/logs/backup/syslog._COPYING_. Name node is in safe mode.

Determine current `safe mode` status.

    $ hdfs dfsadmin -safemode get
    Safe mode is ON
    
Disable `safe mode`.

    $ hdfs dfsadmin -safemode leave
    Safe mode is OFF
