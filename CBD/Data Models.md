---
tags:
  - CBD
---
# What are they?
The start of any development of a Database starts at the Data Model, which is an abstract model of the real world problem we want to solve.
Depending on the inputs and outputs needed for the problem, the Data Model will influence everything about what Database service we use to how the code will be written.

# What do they aim to solve?
The increasing data production is simply so large that standard technologies that were state of the art before simply cannot keep up. While we are producing more data, the data we're producing is becoming even more interconnected and complex further exacerbating the problem.

There's also a lot of problems that arise when trying to converting from the data stored in the DB to data store in running code, this is know as impedance mismatch.

Impedance Mismatch rundown:
1. **Data Representation Differences:** Object-oriented programming languages organise data in the form of objects, which have attributes and methods. Relational databases, on the other hand, store data in tables with rows and columns. Mapping objects to tables and vice versa can be complex.
    
2. **Complexity in Mapping Relationships:** Object-oriented models allow complex relationships and inheritance hierarchies, which might not directly align with the relational model. Translating these structures to relational database schemas can be challenging.
    
3. **Query Language Mismatch:** Object-oriented languages use methods and object references to access and manipulate data, whereas databases use SQL (Structured Query Language). Bridging the gap between the two often requires translation or adaptation of the queries.
    
4. **Performance Overhead:** Inefficient mappings or translations between the two paradigms can lead to performance issues as they might require extra processing, queries, or transformations.

Visual example:
[[CBD_02_DataModels.pdf#page=12&selection=0,0,4,7|CBD_02_DataModels, page 12]]

# Where are we now? 
To fix the aforementioned problem
# Model Types
- Flat Model 
- Hierarchical Model
- Network Model
- Relational Model
- Object-Relational Model
- Object-role Model
- Star Schema
- Among many others...


