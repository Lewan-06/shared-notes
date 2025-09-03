## Reductions
- fold, reduce and aggregate
### Computations
- Iterate through collection and **combines** neighbouring elements
- Fold vs foldleft: foldleft can take two different types of inputs and fold always takes two of same inputs
- Aggregate: kind of combination of foldleft and fold
## Pair RDDs
- In large data, it is very likely that we use key-value pairs
### Transformations
- Example functions: groupByKey, reduceByKey, join, mapValues, keys, leftOuterJoin/rightOuterJoin
- groupBy:
	![[Screenshot 2025-07-20 115400 1.png]]
- groupByKey: 
	![[Screenshot 2025-07-20 115544.png]]
- reduceByKey: faster than groupByKey and then reduce
	- instead of moving all elements to one terminal then reducing them, we reduce them at each node and then combine results
	![[Screenshot 2025-07-20 120335.png]]
- join: always joined on keys
	- So it allows for (val1, val2) and (val1, (val2, val3,...))
### Action
- Example functions: countByKey
![[Screenshot 2025-07-20 120230 1.png]]