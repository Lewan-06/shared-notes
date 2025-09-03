## Shuffling
- Moving data between nodes
- Must be avoided due to latency 
### GroupByKey vs reduceByKey
-  GroupByKey must have one key-value pair. So all values must be moved to one node
- reduceByKey can be summed only once to minimise data sent over network
## Partitioning
- When you already have existing key-value pairs, but you create less key-value pairs by merging them
- Create partition: cogroup, groupWith, join, leftOuterJoin, rightOuterJoin, groupByKey, reduceByKey, foldByKey, cmbineByKey, partitionBy, sort, mapValues, flatMapValues, filter
- Map changes key, if we want to access key-value pairs using their key, we then need to reshuffle across all devices
### Optimisations
#### Hash partitions
- Group data based on hash(key) % numPartitions
#### Range partitions
- Group data per range (total/partitions)
#### Pre-partitions
- If pre partition a large data set, then we only have 1 time partitioning cost and we can join small data sets only at the cost of shuffling the small data set
## Wide vs narrow dependencies
- Particular transformation are more expensive than others
- Data can be restored using the dependencies
### Narrow
- Parent partition only max one leads to one child partition
- Fast fault tolerance
- Example functions: map, filter, union, join (with pre-partition)
### Wide
- Parent partition leads to multiple child
- Fault tolerance slow, because we need to check multiple parents
- Example functions: groupByKey, join (without pre-partition)
