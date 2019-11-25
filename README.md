#Goals
+ Run Spark in Docker container  :)
+ Configure Livy to run spark-submit from bash
+ Create DAG to schedule WordCount application
+ Launch WordCount onto Spark cluster
+ Run WordCount via AirFlow


`curl -H "Content-Type: application/json" -X POST -d resources/livyWordCount.json spark-master:8998/batches`

`curl -H "Content-Type: application/json" -X POST -d @/data/resources/livyWordCount.json localhost:8998/batches`

`curl -H "Content-Type: application/json" -X POST -d '{
   "className": "thoughtworks.wordcount.WordCount",
   "name": "Word Count Livy",
   "file": "/data/resources/tw-pipeline_2.11-0.1.0-SNAPSHOT.jar",
   "args": [
     "/data/resources/words.txt",
     "/data/resources/output/"
   ]
 }' localhost:8998/batches`
 
 
