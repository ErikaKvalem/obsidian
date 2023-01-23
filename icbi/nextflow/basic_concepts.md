source: https://www.nextflow.io/docs/latest/basic.html

##  Basic concepts
- ### Processes and channels 
	Process: WHAT COMMAND/SCRIPT has to be executed. 
	Processes are executed independently, isolated from each other.
		- The way processes communicate is via asynchronous FIFO queues called channels. 
		- Any process : 1 or more channes as input/output 

Example of script. 
```
// Declare syntax version
nextflow.enable.dsl=2
// Script parameters
params.query = "/some/data/sample.fa"
params.db = "/some/path/pdb"

process blastSearch {
  input:
    path query
    path db
  output:
    path "top_hits.txt"

    """
    blastp -db $db -query $query -outfmt 6 > blast_result
    cat blast_result | head -n 10 | cut -f 2 > top_hits.txt
    """
}

process extractTopHits {
  input:
    path top_hits

  output:
    path "sequences.txt"

    """
    blastdbcmd -db $db -entry_batch $top_hits > sequences.txt
    """
}

workflow {
   def query_ch = Channel.fromPath(params.query)
   blastSearch(query_ch, params.db) | extractTopHits | view
}
```

2 processes: 
- blastSearch
- extractTopHits 
Order:  ``` blastSearch(query_ch, params.db) | extractTopHits```
Given by the pipeline 
When the first process emits a value --> the second process receive it. 

Creates 2 processes & 1 channel ```query_ch```
- Both process start at the same time 
- They get input from the respective channels

### Execution abstraction 

Executor: How the script given by the process is actually run on the target system. 
Where? Define the target execution platform (your computer, a grid platform, or the cloud)

- Batch schedulers. (e.g SLURM)
- Cloud platforms (e.g AWS, Google Clout Platform, Kubernetes)

### Script language
Powerful scripting DSL 
Extension of Groovy programming language --> Super set of Java p.l 

### Configuration options
Pipeline configuration properties. 
For specify executor, process env. variables, parameters of pipeline etc 

```nextflow.config```

```
process {
  executor='sge'
  queue = 'cn-el6'
}
```


