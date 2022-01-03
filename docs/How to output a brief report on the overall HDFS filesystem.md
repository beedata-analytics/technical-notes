# How to output a brief report on the overall HDFS filesystem

**`hdfs dfsadmin -report`** outputs a brief report on the overall HDFS filesystem. It’s a useful command to quickly view how much disk is available, how many DataNodes are running, corrupted blocks etc.

```bash
sudo -u hdfs hdfs dfsadmin -report
```
