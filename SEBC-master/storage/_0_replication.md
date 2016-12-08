
=======================================================================================================
TERAGEN CREATE FILE
=======================================================================================================
sudo -u hdfs hadoop fs -ls


cd /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/share/doc/hadoop-0.20-mapreduce/examples
HADOOP_USER_NAME=hdfs hadoop jar hadoop-examples.jar teragen 5242880 /user/hdfs/sch1
[centos@ip-172-31-5-138 h]$ cd /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/share/doc/hadoop-0.20-mapreduce/examples
[centos@ip-172-31-5-138 examples]$ HADOOP_USER_NAME=hdfs hadoop jar hadoop-examples.jar teragen 5242880 /user/hdfs/sch1
16/12/07 08:03:11 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-5-137.ap-southeast-1.compute.internal/172.31.5.137:8032
16/12/07 08:03:12 INFO terasort.TeraSort: Generating 5242880 using 2
16/12/07 08:03:12 INFO mapreduce.JobSubmitter: number of splits:2
16/12/07 08:03:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481081119832_0004
16/12/07 08:03:12 INFO impl.YarnClientImpl: Submitted application application_1481081119832_0004
16/12/07 08:03:12 INFO mapreduce.Job: The url to track the job: http://ip-172-31-5-137.ap-southeast-1.compute.internal:8088/proxy/application_1481081119832_0004/
16/12/07 08:03:12 INFO mapreduce.Job: Running job: job_1481081119832_0004
16/12/07 08:03:19 INFO mapreduce.Job: Job job_1481081119832_0004 running in uber mode : false
16/12/07 08:03:19 INFO mapreduce.Job:  map 0% reduce 0%
16/12/07 08:03:28 INFO mapreduce.Job:  map 100% reduce 0%
16/12/07 08:03:28 INFO mapreduce.Job: Job job_1481081119832_0004 completed successfully
16/12/07 08:03:28 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=248158
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=167
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=14877
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=14877
                Total vcore-seconds taken by all map tasks=14877
                Total megabyte-seconds taken by all map tasks=15234048
        Map-Reduce Framework
                Map input records=5242880
                Map output records=5242880
                Input split bytes=167
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=202
                CPU time spent (ms)=14590
                Physical memory (bytes) snapshot=750841856
                Virtual memory (bytes) snapshot=3185340416
                Total committed heap usage (bytes)=848297984
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=11257830824958050
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=524288000


=======================================================================================================
distCp
=======================================================================================================

[centos@ip-172-31-5-138 h]$ HADOOP_USER_NAME=hdfs hadoop distcp hdfs://172.31.5.138/user/snowbite_test12 hdfs://172.31.13.100/user/hdfs/eugene12
16/12/07 07:10:53 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://172.31.5.138/user/snowbite_test12], targetPath=hdfs://172.31.13.100/user/hdfs/eugene12, targetPathExists=false, filtersFile='null'}
16/12/07 07:10:53 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-5-137.ap-southeast-1.compute.internal/172.31.5.137:8032
16/12/07 07:10:54 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
16/12/07 07:10:54 INFO tools.SimpleCopyListing: Build file listing completed.
16/12/07 07:10:54 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
16/12/07 07:10:54 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
16/12/07 07:10:54 INFO tools.DistCp: Number of paths in the copy list: 4
16/12/07 07:10:54 INFO tools.DistCp: Number of paths in the copy list: 4
16/12/07 07:10:54 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-5-137.ap-southeast-1.compute.internal/172.31.5.137:8032
16/12/07 07:10:54 INFO mapreduce.JobSubmitter: number of splits:3
16/12/07 07:10:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481081119832_0003
16/12/07 07:10:55 INFO impl.YarnClientImpl: Submitted application application_1481081119832_0003
16/12/07 07:10:55 INFO mapreduce.Job: The url to track the job: http://ip-172-31-5-137.ap-southeast-1.compute.internal:8088/proxy/application_1481081119832_0003/
16/12/07 07:10:55 INFO tools.DistCp: DistCp job-id: job_1481081119832_0003
16/12/07 07:10:55 INFO mapreduce.Job: Running job: job_1481081119832_0003
16/12/07 07:11:01 INFO mapreduce.Job: Job job_1481081119832_0003 running in uber mode : false
16/12/07 07:11:01 INFO mapreduce.Job:  map 0% reduce 0%
16/12/07 07:11:06 INFO mapreduce.Job:  map 33% reduce 0%
16/12/07 07:11:13 INFO mapreduce.Job:  map 67% reduce 0%
16/12/07 07:11:16 INFO mapreduce.Job:  map 100% reduce 0%
16/12/07 07:11:32 INFO mapreduce.Job: Job job_1481081119832_0003 completed successfully
16/12/07 07:11:32 INFO mapreduce.Job: Counters: 33
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=381417
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=524289570
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=56
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=13
        Job Counters
                Launched map tasks=3
                Other local map tasks=3
                Total time spent by all maps in occupied slots (ms)=49685
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=49685
                Total vcore-seconds taken by all map tasks=49685
                Total megabyte-seconds taken by all map tasks=50877440
        Map-Reduce Framework
                Map input records=4
                Map output records=0
                Input split bytes=348
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=218
                CPU time spent (ms)=11100
                Physical memory (bytes) snapshot=734859264
                Virtual memory (bytes) snapshot=4773552128
                Total committed heap usage (bytes)=1055391744
        File Input Format Counters
                Bytes Read=1222
        File Output Format Counters
                Bytes Written=0
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=524288000
                BYTESEXPECTED=524288000
                COPY=4





=======================================================================================================
HDFS FSCK SOURCE DIRECTORY
=======================================================================================================



[centos@ip-172-31-5-138 examples]$ sudo -u hdfs hdfs fsck /user/hdfs/sch1
Connecting to namenode via http://ip-172-31-5-138.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.5.138 for path /user/hdfs/sch1 at Wed Dec 07 08:08:27 UTC 2016
...Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Wed Dec 07 08:08:27 UTC 2016 in 3 milliseconds


The filesystem under path '/user/hdfs/sch1' is HEALTHY
[centos@ip-172-31-5-138 examples]$






=======================================================================================================
HDFS FSCK TARGET SOURCE DIRECTORY
=======================================================================================================

[centos@ip-172-31-5-138 examples]$ sudo -u hdfs hdfs fsck hdfs://172.31.5.138/user/snowbite_test12
Connecting to namenode via http://ip-172-31-5-138.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.5.138 for path hdfs://172.31.5.138/user/snowbite_test12 at Wed Dec 07 08:09:42 UTC 2016
FSCK ended at Wed Dec 07 08:09:42 UTC 2016 in 2 milliseconds
Invalid path name Invalid file name: hdfs://172.31.5.138/user/snowbite_test12


Fsck on path 'hdfs://172.31.5.138/user/snowbite_test12' FAILED
[centos@ip-172-31-5-138 examples]$ sudo -u hdfs hdfs fsck /user/snowbite_test12
Connecting to namenode via http://ip-172-31-5-138.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.5.138 for path /user/snowbite_test12 at Wed Dec 07 08:10:44 UTC 2016
...Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Wed Dec 07 08:10:44 UTC 2016 in 1 milliseconds


The filesystem under path '/user/snowbite_test12' is HEALTHY
[centos@ip-172-31-5-138 examples]$
