---
tags:
  - Databases
  - DataBase_Type
  - Column_Databases
  - CBD
---
# Concept

Data storage and processing is handled by columns, in contrast to normal databases which is handled by rows. 

E.g:
A "normal" database will most likely store it by row such as :
`ID : 1 ; name : JohnDoe ; email JohnDoe@abc.xyz || ID : 2 ; name : JaneDoe ; email JaneDoe@abc.xyz`

While a column database will store it as such:
`ID : 1 , 2 || name : JohnDoe , JaneDoe || email : JohnDoe@abc.xyz , JaneDoe@abc.xyz`

# Pros VS Cons

## Pros

- Data Compression
	Ex: Since data is store by columns, and every value in the column is of a similar type (all ints, all strings, etc), this allows for more efficient compression since we don't need to know the value type of each value.
<br>
- Query Performance
	Ex: Overall performance is better due to less memory being accessed (a side effect from the previous point), but depending on the queries, the column based structure actually helps even further, for example sum, avg, min, max functions are extremely fast compared to row DBs because they need to access only one column, compared to accessing every row individually.
<br>
- Scalability / Reliability ( When using Nodes )
	Ex: By employing key-hashing, column databases can be expanded nearly infinitely by spreading the data throughout cluster nodes, this is, a single node won't hold the full database information. Combining this concept with replication, this allows us to extend our databases horizontally offering a outage resilient database.
	
## Cons

- Queries that might've been standard in other DBs ([OLTP](CBD/OLTP)), will not execute in Column Databases.
	Ex: Due to the different structure of the DB, queries that often use joins and such operations are not possible. Also, incremental loading while possible is highly discouraged.
<br>
- Writing is slower in general compared to other DBs.
	Ex: Since columns are separated, saving a full record takes more time because you need to access N columns for N fields.
	
# Use Cases

- Problems with flat data with similar schemas, i.e. event logging, content management systems, blogs.
<br>
- Problems that will need large batch processing operations (User Prediction, Stock Analysis, etc...)

# Structure
[[CBD_07_Column.pdf#page=8&selection=0,0,0,10|CBD_07_Column, page 8]]

# Examples

[[Cassandra]], [Apache HBase](https://hbase.apache.org/), [Apache Accumulo](https://accumulo.apache.org/), [[Google Bigtable]], [HyperTable](https://hypertable.org/).

Next 