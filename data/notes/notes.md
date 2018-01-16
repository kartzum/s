# Spark

## Code

### Csv

```
val df = spark.read.option("header", "false").option("delimiter", ";").csv("data.csv")
```
