## Lecture html pages
### Tools and technologies
- Unix: small(er) data 
- Spark: batch processing (deal with data in groups, scheduled)
- Flink: stream processing (deal with data immediately)
- Spark + custom code: graphs (structured data with connections such as social media user connections)
- Bash: automated data processing
- Scala: high performance data processing
### What is big data? 
- "Data too large to be efficiently processed on a single computer"
- "Massive amounts of diverse, unstructured data produced by high-performance applications"
### Challenges of big data? 
#### Main by Doug Laney
- Volume
- Variety: different forms and diverse sources
- Velocity: content changing quickly (near-real time generation)
#### Added over time
- Value: how can we derive value from data? 
- Validity: how accurate the data is
- Veracity: trustworthiness, reliability and quality of data 
- Volatility: how long does the data need to be stored? 
- Visibility: integrate diverse sources in a unified way
- Virality: how quickly data spreads/ is shared
### Desired properties of a BDPS (big data processing system)
- Robustness and fault-tolerance: ability to function even on hardware/software failures (data replicas and error detection etc.)
- Low latency updates and reads: quickly read and update data 
- Scalability: maintain performance when number of users grows
- Generalisation: flexibility to support a wide range of apps and not only one specific one 
- Extensibility: features must be able to be added easily
- Ad hoc queries: ability to run spontaneous queries (instead of scheduled)
- Minimal maintenance: little intervention to operate smoothly
- Debuggability: possibility to trace and diagnose problems quickly 
### Programming languages
#### Scala
- Data intensive systems
- Functional programming and object oriented
- Compiled: translated to byte code (runs very fast)
#### Python
- Used for data analytics 
- Object oriented and imperative programming (explicitly tell computer how to perform tasks)
- Interpreted: executed line by line and interpreter directly runs code (quick development but low performance)
### Basic coding knowledge:
https://burcuku.github.io/cse2520-bigdata/intro-to-langs.html