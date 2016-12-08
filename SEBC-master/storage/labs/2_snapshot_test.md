```sh
=========================================================================
CREATE HDFS PRECIOUS DIRECTORY
=========================================================================
sudo -u hdfs hdfs dfs -mkdir /user/hdfs/precious
```


```sh
=========================================================================
PUT A ZIP FILE INTO THE PRECIOUS DIRECTORY
=========================================================================
sudo -u hdfs hdfs dfs -cp /user/oozie/share/lib/lib_20161206101418/spark/pyspark.zip /user/hdfs/precious
```


```sh
=========================================================================
REMOVE PRECIOUS DIRECTORY
=========================================================================
[centos@ip-172-31-5-138 ~]$ sudo -u hdfs hdfs dfs -rmdir /user/hdfs/precious
rmdir: `/user/hdfs/precious': Directory is not empty
[centos@ip-172-31-5-138 ~]$

rmdir: `/user/hdfs/precious': Directory is not empty
```


```sh
=========================================================================
REMOVE ZIP FILE
=========================================================================
 [centos@ip-172-31-5-138 ~]$ sudo -u hdfs hdfs dfs -rm 
/user/hdfs/precious/pyspark.zip
16/12/07 22:14:48 INFO fs.TrashPolicyDefault: Moved: 'hdfs://nameservice1/user/hdfs/precious/pyspark.zip' to trash at: hdfs://nameservice1/user/hdfs/.Trash/Current/user/hdfs/precious/pyspark.zip1481148888939
```
