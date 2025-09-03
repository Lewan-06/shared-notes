## Structured vs unstructured

### Data
![[Screenshot 2025-07-22 202750.png]]
### Computations
- Spark can't look at operations that we want to do for functional operations vs in databases, transformations are declarative (fixed set)
- This means that in spark we need to optimise our own computations
## Spark SQL
-  Get optimisations from SQL databases in our code
- Goals: relational processing, high performance and support new data sources (semi-structured and databases)
![[Screenshot 2025-07-22 203539.png]]
### DataFrame
- Untyped
- VS RDD\[\<type>]
#### Reading from source
- spark.read.json("\<path>")
#### Spark session object
- Spark contexts version for SQL
#### Cleaning 
- Drop unwanted values or replace values with columns
- drop() removes rows with null or NaN values
- drop("all") removes rows that contain null or NaN in all column
- drop(Array("id", "name")) removes rows that contain null or NaN values in specified columns
- fill(\<specified_value>) replace all null or Nan with specified values
- fill(Map("\<col_name>) -> \<specified_value>) replaces all occurances of null or Nan in specified col with specified value
- replace(Array("id"), Map(1234, -> 8976)) replaces specified value in specified column with specified replace value
- show() displays first 20 rows 
- joins: no keys so we must specify value to join on
#### Optimisations
- Reorder computations
- Reduce amount of data to be read
- Remove unnecessary partitions
- Tungsten (Spark SQL's encoder)
	- Highly specialised encoder
	- Column based: grab only a column (instead of all rows when we only need one column)
	- Garbage collection overhead on the main memory
#### Limitations
- Untyped
	- Unknown types can't because by the compiler
- Limited data types
	- Data can only be expressed by case classes/Products and standard Spark SQL data types
- Requires semi-structured+ data
### Datasets
- Solve the dataframe problem of: not having normal int types, but special sql types
	- Compromise between RDDs & DataFrames: type safety, optimisations
- Data frame is a Dataset\[Row\]
- Require encoders (because they must be able to get sent efficiently)
	- Automatically
- r.getAs\[String]("\<column>) to go from df to ds
#### Creating
- From DataFrame
	- \<dataframe>.toDS
- From RDD
	- \<RDD>.toDS
- Reading from file
	- spark.read.json("\<jsonfile_path>).as\[<type]
- From scala type
	- list("bla", "blabla").toDS
#### Types column
- "\<name\>".as\[\<data_type>]
#### Transformations
- Returns new Datasets
	- map 
	- flatMap
	- filter
	- distinct
	- groupByKey
	- coalesce
	- repartition
	- select(\<projection>)
#### Aggregations
- reduceGroups: reduce function on each of the elements of a group
- agg:  avg
- mapGroups: applies map function on each group of data (requires shuffling)
- flatMapGroups: flatten version of above
##### Custom aggregators
- new Aggregator\[IN, BUF, OUT]
	- IN=input
	- BUF=intermeidate
	- OUT=output
- Must implement: zero (initial val), reduce, merge and finish, bufferEncoder, outputEncoder
#### Actions
- Collect, count, first, foreach, reduce, show, take
## Use cases
- Datasets (actually built on top of RDDs)
	- structured/semi-structured
	- typesafety
	- function APIs
	- performance is good
- Dataframes (actually built on top of RDDs)
	- structure-semi-structured
	- best performance
- RDD
	- unstructured data
	- fine-tune low level computations
	- complex data types
#### Limitations
- Functional filter operations can't be optimsed by Catalyist (optimiser)
	- E.g: ds.filter(x => x.column == val)
		- Spark does not know it only needs x.column
		- Relational alternative that can be optimsied
			- ds.filter($"column".as\[data_type] == val)
				- Spark knows it only requires accessing "column" in order to perform this operation (filter)
- \#data_types are limited
- requires structured/semi-structured data