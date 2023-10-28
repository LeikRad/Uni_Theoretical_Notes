---
tags:
  - Column_Databases
  - Databases
---
# Introduction
Facebook's open source response to the unveiling of [Google's Bigtable](obsidian://open?vault=Uni_Theoretical_Notes&file=CBD%2FGoogle%20Bigtable), Cassandra was (and still is sadly) implemented in Java.

Created to handle Facebook's big data, it was tested on a 50TB subset of the actual data, spread around 150 nodes, it's performance was excellent and as such it was adopted. It also aims to not sacrifice its Write performance while being easy to scale.

Cassandra vs MySQL
[[CBD_07_Column.pdf#page=21&selection=0,0,0,18|CBD_07_Column, page 21]]

# Nomenclature

Node - A machine (unfortunate enough) that is running Cassandra
Data Center | Replication group - A collection of nodes
Cluster - A collection of collections of nodes (Collection of Data Centers :)). 
Note: All Datacenters will have a copy of all the data, thus each datacenter can be used for different processing tasks.

# System Architecture
Note: Those topics will be discussed more in detail in posterior lessons. In this phase, we will be only focusing in the data model. Pog

# Network Nodes Topology
Every node is organised in a ring, each node only has a part of the database, or at least it should. Any Node can answer any request, write, read, etc, hence there is no Master/Slave relationship

Image:
[[CBD_07_Column.pdf#page=25&selection=0,0,0,22|CBD_07_Column, page 2 5]]

# Data Model
## # Data store
In order of abstraction:
- Keyspace -> Essentially a namespace in other DBs, each node in a cluster contains one keyspace
- Table -> Created by a table schema, it's a collection of rows
- Rows -> It's a collection of columns identified by an unique primary key, each row in a table may not have the same number of columns ( see [[Google Bigtable]] JSON example)
- Column -> Value : Pair ?+ Optional 

Image:
[[CBD_07_Column.pdf#page=30&selection=0,0,0,31|CBD_07_Column, page 30]]

# Extra Info

Value types, Language syntax, Query examples, etc...
[[CBD_07_Column.pdf#page=32&selection=0,0,4,15|CBD_07_Column, page 32]]