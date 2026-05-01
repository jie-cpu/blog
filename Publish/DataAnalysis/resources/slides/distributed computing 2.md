# link


# Summary 

- in memory processing
     - allow data analysis in real time
     - RAM cheaper
     - iteration taks
     - caching  --- working set is small
     - replication --- 
     - prefetching --- patterns are predictable
- [[Apache Spark]]
     - fast engine for large scale data processing 
          -  spark SQL
          - streaming
          - graphX
          - MLLib --- for machine learning
      - can be accessed by previous tools like apache hadoop
      - can run standalone or in cluster mode 
             - standalone----- run by itself, with everything you need within the system ----driver/manager/workers
             - cluster mode ----rely on other recourse manager or cluster manager to schedule everything
 - differences between HPC and Big Data scheduling
		 - HPC scheduling ---slurm
		     - resource-centered computing platform,
		     - How many CPUs/GPUs do I need to run this computation?
		     - C/C++
		- Bid Data scheduling --- hadoop
		    - data-centered scheduling platform,
		    - I need to process this data — how can I schedule resources to finish it as efficiently as possible?
		    - java 
- [[stream processing]]
- Constantly evolving software frameworks to support analytics scenarios
-  Incorporating more hardware capabilities: in-memory processing
- Reflection on more demand for stream processing
- Development of extended software ecosystem for data analytics, e.g. Spark, Flink as successor project to Hadoop/MapReduce
- Nowadays more convergence of Big Data and HPC ecosystem
- Spark and Flink are increasingly being deployed on HPC clusters, using resource managers such as Slurm or Kubernetes.
---

# Related Concepts

*  [[distributed computing 1]]
