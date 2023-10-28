---
tags:
  - Column_Databases
  - Databases
---
### Disclaimer:
Probably not relevant material for exam, just know that it's the inspiration of Columnar Databases.

# Google Bigtable

Google Bigtable (GBT) is a NoSQL database used mainly by Google for their large data applications. Released in 2005, it distinguishes itself from other database models of the time by using a wide-column store, simply put, a two-dimensional key-value storage.

E.g
```json
{"key1":
	{
		"subkey1":"value1"
	},
"key2":
	{
		 "subkey2":"value2",
		 "subkey3":"value3"
	}
}
```

Originally it was private service, usable only by Google, and thus it spawned various open-source alternatives such as [[Cassandra]], among others...

More Examples of Bigtable:
[[CBD_07_Column.pdf#page=15&selection=0,0,4,13|CBD_07_Column, page 15]]