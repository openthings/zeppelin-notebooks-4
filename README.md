# zeppelin-notebooks

This example Zeppelin notebook provides a visualization of tweets on Trump from a Twitter stream. 

1. Install Apache Zeppelin.
Grab the `bin-all` download available [here](The https://zeppelin.apache.org/download.html) and expand it into a local directory. 

2. Download the project [zip file](https://github.com/robmoore/zeppelin-notebooks/archive/master.zip). You can copy the contents of the `zeppelin-notebooks-master` directory into the `notebook` directory under the Zeppelin directory you created. From the Zeppelin directory, the notebook file should be located in `./notebook/2C6XWDSQ1/note.json`. Alternatively, you can also import the notebook from within Zeppelin once you have it running.

3. Assuming you have java installed and are on Linux or a Mac, you can start it by running `bin/zeppelin-daemon.sh start`.

4. Open your browser to http://localhost:8080/#/notebook/2C6XWDSQ1 and run each paragraph. Note, you'll need to enter your Twitter API credentials in the provided form in the 4th paragraph.

*Please note*: When running `sql` paragraphs, you may encounter the following error:
```
java.lang.NoSuchMethodException: org.apache.spark.io.LZ4CompressionCodec.<init>(org.apache.spark.SparkConf)
	at java.lang.Class.getConstructor0(Class.java:3082)
	at java.lang.Class.getConstructor(Class.java:1825)
	at org.apache.spark.io.CompressionCodec$.createCodec(CompressionCodec.scala:72)
	at org.apache.spark.io.CompressionCodec$.createCodec(CompressionCodec.scala:66)
	at org.apache.spark.sql.execution.SparkPlan.org$apache$spark$sql$execution$SparkPlan$$decodeUnsafeRows(SparkPlan.scala:265)
	at org.apache.spark.sql.execution.SparkPlan$$anonfun$executeTake$1.apply(SparkPlan.scala:351)
	at org.apache.spark.sql.execution.SparkPlan$$anonfun$executeTake$1.apply(SparkPlan.scala:350)
	at scala.collection.IndexedSeqOptimized$class.foreach(IndexedSeqOptimized.scala:33)
	at scala.collection.mutable.ArrayOps$ofRef.foreach(ArrayOps.scala:186)
	at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:350)
	at org.apache.spark.sql.execution.CollectLimitExec.executeCollect(limit.scala:39)
	at org.apache.spark.sql.Dataset$$anonfun$org$apache$spark$sql$Dataset$$execute$1$1.apply(Dataset.scala:2183)
	at org.apache.spark.sql.execution.SQLExecution$.withNewExecutionId(SQLExecution.scala:57)
	at org.apache.spark.sql.Dataset.withNewExecutionId(Dataset.scala:2532)
	at org.apache.spark.sql.Dataset.org$apache$spark$sql$Dataset$$execute$1(Dataset.scala:2182)
	at org.apache.spark.sql.Dataset.org$apache$spark$sql$Dataset$$collect(Dataset.scala:2189)
	at org.apache.spark.sql.Dataset$$anonfun$head$1.apply(Dataset.scala:1925)
```
In this event, simply attempt to run the paragraph again. Usually the issues will resolve itself on repeated executions. 
A [ticket](https://issues.apache.org/jira/browse/ZEPPELIN-1799) is open on this issue if you'd like to learn more.	

