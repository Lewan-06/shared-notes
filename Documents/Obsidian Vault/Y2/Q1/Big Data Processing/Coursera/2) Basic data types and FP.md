https://burcuku.github.io/cse2520-bigdata/prog-big-data.html

### Functional programming
- Idea of all code existing within functions that always produce the same result for the same input
### Parallelism 
- In Scala, we can use shared memory to execute simultaneously 
	- Spark solves the issue that your data might not fit into main memory at once by splitting it and executing on multiple cores/available memory independently
### Why Spark over Hadoop?
1) More expressive: more data types and operations 
2) More performance: jobs run faster and more intuitive APIs and abstractions
	- Lower latency using functional programming
	- All data that is 1) immutable and 2) in memory
		- Instead of writing results to disk for every computation/function we do, spark executes all functions, remember which it did for recovery but only at the end persists to disk
3) Enables iterations over collections
### Map
- Usage: \<collection>.map(x => \<method>(x))
- One-to-one
- Vs flatmap: one-to-any
### Underscore
- E.g: \_._\_2 
	- This accesses the 2nd sub element 
### Distributed
- Different computers/nodes work on data in parallel 
- Watch out for non-associative reduction operations: .reduce() creates pairs but (a-b) - c != a - (b-c)
#### Problems
- Partial failure 
- Latency
- Both are mostly solved by spark
### Resilient distributed datasets
- This is sparks collection abstraction of a distributed data parallel model
#### Creating RDD
1) Transform existing: calling a map on a RDD
2) SparkContext/SparkSession: 
	1) Paralleize: creates RDD from scala collection
		1) Less likely because for it to be a scala collection, it already exists in memory and then the use case for spark is gone
	2) textFile: read text file to return RDD of strings (needs to be converted to integers for example)
#### Transformations
- Return new collections (RDD for spark) as results
	- map, filter, flatMap, groupBy
- Lazy: result not immediately computed (important for how spark handles network/latency)
#### Accessor (or action in spark)
- Returns single values as results => don't return RDD but another type such as array, long etc.
	- reduce, collect, count, take, reduce, foreach
- Eager: result immediately computed (important for how spark handles network/latency)

ONLY AFTER  CALLING AN ACTION ON A COLLECTIONS, ALL TRANSFORMATIONS WILL BE CALCUALTED
- Reason spark does this is because it can optimise the calculations. Some actions might not require all transformations to be done (this we would not know if we execute transformation immediately)
- If we use a val that is a transformation multiple times, it might be useful to use persist(). Otherwise it needs to be calculated every time we use it 
### Spark jobs
- Master (aka driver) that has spark context and workers that are executors
- Cluster manager does planning and spreading tasks to workers 
- Code will be executed on the worker nodes => for each will not be shown on the driver program
![[Screenshot 2025-08-10 132917.png]]