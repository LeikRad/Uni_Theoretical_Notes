---
tags:
  - Databases
  - DataBase_Type
  - Column_Databases
---
# Concept

Data storage and processing is handled by columns, in contrast to normal databases which is handled by rows. 

E.g:
A normal database will most likely store it by row such as :
`ID : 1 ; name : JohnDoe ; email JohnDoe@abc.xyz || ID : 2 ; name : JaneDoe ; email JaneDoe@abc.xyz`

While a column database will store it as such:
`ID : 1 , 2 || name : JohnDoe , JaneDoe || email : JohnDoe@abc.xyz , JaneDoe@abc.xyz`

# Pros VS Cons

## Pros

Data Compression

Query Performance

Scalability

## Cons

Queries that might've been standard in other DBs, will not execute in Column Databases.

Writing is slower in general compared to other DBs.

# Use Cases

Problems with flat data with similar schemas, i.e. event logging, content management systems, blogs.

Problems that will need large batch processing operations

# Examples

[[Cassandra]], [Apache HBase](https://hbase.apache.org/), [Apache Accumulo](https://accumulo.apache.org/), [[Google BigTable]], [HyperTable](https://hypertable.org/).

