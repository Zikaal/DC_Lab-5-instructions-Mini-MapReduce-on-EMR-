# Lab 5 - MapReduce on Amazon EMR

## Dataset
Wikipedia Simple English corpus from: https://github.com/LGDoor/Dump-of-Simple-EnglishWiki

## How to Run

1. Upload dataset to HDFS:
```bash
   hdfs dfs -put corpus.txt /user/hadoop/input/
```

2. Run MapReduce job:
```bash
   hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar \
     -input /user/hadoop/input/corpus.txt \
     -output /user/hadoop/output/wordcount \
     -mapper mapper.py \
     -reducer reducer.py \
     -files mapper.py,reducer.py
```

3. View results:
```bash
   hdfs dfs -cat /user/hadoop/output/wordcount/part-00000 | head -50
```

## Experiments
- Scenario B with large, medium and small datasets
