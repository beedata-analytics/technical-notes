# How to check region consistency and table integrity problems on HBase

HBaseFsck (hbck) is a tool for checking for region consistency and table integrity problems and repairing a corrupted HBase. It works in two basic modes — a read-only inconsistency identifying mode and a multi-phase read-write repair mode.

To check to see if your HBase cluster has corruptions, run hbck against your HBase cluster:

```bash
$ hbase hbck
```

At the end of the commands output it prints OK or tells you the number of INCONSISTENCIES present. You may also want to run hbck a few times because some inconsistencies can be transient (e.g. cluster is starting up or a region is splitting). Operationally you may want to run hbck regularly and setup alert if it repeatedly reports inconsistencies . A run of hbck will report a list of inconsistencies along with a brief description of the regions and tables affected. The using the `-details` option will report more details including a representative listing of all the splits present in all the tables.

```bash
$ hbase hbck -details
```

If you just want to know if some tables are corrupted, you can limit hbck to identify inconsistencies in only specific tables. For example the following command would only attempt to check table TableFoo and TableBar. The benefit is that hbck will run in less time.

```bash
$ hbase hbck powerConsumption_6161024077_devices
```

To repair a table run:

```bash
$ sudo -u hbase hbase hbck -repair powerConsumption_6161024077_devices
```

