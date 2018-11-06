# Data/Spark/ML

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

## https://stepik.org/course/326/syllabus
### Notes

[Математическим ожиданием случайной величины называется сумма произведений всех возможных значений случайной величины на вероятности этих значений.](http://sernam.ru/book_tp.php?id=21)

[Дисперсией случайной величины  называется матемйтическое ожидание квадрата разности случайной величины  и ее математического ожидания.
(т. е. математическое ожидание квадрата соответствующей центрированной, случайной величины)..](http://edu.sernam.ru/book_p_math2.php?id=151)

[Функция распределения](http://sernam.ru/book_tp.php?id=17)

[На шахматную доску случайным образом поставлены две ладьи. Какова вероятность, что они не будут бить одна другую](https://www.matburo.ru/ex_tv.php?p2=klass4)

[Теория вероятностей](http://hijos.ru/izuchenie-matematiki/algebra-11-klass/6-teoriya-veroyatnosti/) 

http://elar.urfu.ru/bitstream/10995/48459/1/978-5-9544-0079-3_2017.pdf

[Многоугольник и функция распределения дискретной случайной величины](http://mathprofi.ru/funkcia_raspredeleniya_dsv.html)

[Математическое ожидание характеризует среднее значение случайной величины.](https://studfiles.net/preview/1438520/)

## Links

* [supervised-learning](https://ru.coursera.org/learn/supervised-learning/)
* [machine-learning-data-analysis](https://ru.coursera.org/specializations/machine-learning-data-analysis)
* [Классификация данных методом опорных векторов](https://habrahabr.ru/post/105220/)
* [Программирование на Python — курс для желающих узнать о нём больше или изучить ещё один язык программирования](https://habrahabr.ru/company/spbau/blog/280426/)
* [pythonworld](https://pythonworld.ru/kursy/free.html)
* [Введение в машинное обучение с помощью Python. Руководство для специалистов по работе с данными](http://www.ozon.ru/context/detail/id/140891479/)
* [Построение систем машинного обучения на языке Python (!)](http://www.ozon.ru/context/detail/id/33850948/)
* [Python и анализ данных (!)](http://www.ozon.ru/context/detail/id/139599513/)
* [Построение систем машинного обучения на языке Python (!)](http://www.ozon.ru/context/detail/id/139907968/)
* [Python для сложных задач. Наука о данных и машинное обучение](http://www.ozon.ru/context/detail/id/142007330/)
* [Spark for Python Developers](http://www.ozon.ru/context/detail/id/135288375/)
* [scala](https://ru.coursera.org/specializations/scala)
