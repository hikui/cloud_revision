# Big data analysis

## Challenges 

* Reading and writing distributed datasets
* Preserving data in the presence of failing data nodes
* Supporting the execution of MapReduce tasks
* Being fault-tolerant (compute nodes)
* Coordinating the execution of tasks across a cluster

## HDFS

HDFS is the core of Hadoop. It's a fault tolerant file system that has been explicitly defined to span many computers.

The block size of HDFS is 128MB. Reasons:

* Reduced need for memory to store metadata
* Reduced need for seek operations in big files
* Efficient when most data of a block have to be processed
* More efficient use of the network (less number of connectons)

![](img/hdfs.png)

## Spark

### Why spark

* Hadoop can only perform relatively simple jobs on large dataets.
* Complex jobs are performed -> caching data in memory and finer-grained control on execution of jobs
* 
