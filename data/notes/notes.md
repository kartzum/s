# Spark

## Code

### ntile

```
val df = spark.read.option("header", "false").option("delimiter", ";").csv("data.csv")
import org.apache.spark.sql.functions._
import org.apache.spark.sql.expressions.Window
val w = Window.partitionBy(col("_c0")).orderBy(col("_c0"))
val df1 = df.select(col("_c7"), ntile(100).over(w), rank().over(w)).sort("_c7")
df1.show(5)
```
