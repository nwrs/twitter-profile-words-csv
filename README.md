### Twitter user profile word frequencies

A CSV file of 50,000 word frequencies, rankings and inverse document frequencies sourced from 2,688,101 English language Twitter user profiles.

Motivation: To assist with extracting interesting features from Twitter user profiles.

#### Loading with Spark
```
val sc = SparkSession.builder().master("local[*]").getOrCreate()
val freq = sc.read.option("header","true").csv("twitter-profiles-word-frequency.csv")
freq.show(25, truncate=false)
 
+----+-------+------------------+----+
|word|rawFreq|invDocFreq        |rank|
+----+-------+------------------+----+
|and |504906 |1.672218002006345 |0   |
|the |464628 |1.7553531899253145|1   |
|of  |381172 |1.9533395585156375|2   |
|a   |372714 |1.975778905838013 |3   |
|i   |324818 |2.113325249870728 |4   |
|to  |323909 |2.116127663196839 |5   |
|in  |261871 |2.3287382592451626|6   |
|my  |247995 |2.383181690670484 |7   |
|for |226785 |2.4725878432416275|8   |
|is  |225562 |2.4779952096218723|9   |
|you |177751 |2.7162065807953333|10  |
|me  |143888 |2.927555056169742 |11  |
|on  |134152 |2.9976167898970933|12  |
|love|132346 |3.0111705700193543|13  |
|im  |125701 |3.0626842043278617|14  |
|with|125494 |3.064332326677879 |15  |
|all |104110 |3.25114224285524  |16  |
|be  |99789  |3.2935323185400844|17  |
|life|96090  |3.3313050230527255|18  |
|are |95935  |3.3329193965318393|19  |
|at  |94902  |3.343745495132495 |20  |
|not |91950  |3.3753453242915716|21  |
|your|86518  |3.436237790566757 |22  |
|it  |86190  |3.440036113682594 |23  |
|just|75260  |3.5756414901766105|24  |
+----+-------+------------------+----+
only showing top 25 rows
```
