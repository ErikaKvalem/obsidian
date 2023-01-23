Besic processing primitive to execute a script. 

process + processname + {processbody}

The processbody --> Contains a string which represents the commend/ script that is executed by it. 

```
process sayHello {
"""
echo "Hello World" > file
"""
}
```

Process definition blocks: 
- Directives
- Inputs
- Outputs
- When clause
- Process script 
```
process < name > {

  [ directives ]

  input:
    < process inputs >

  output:
    < process outputs >

  when:
    < condition >

  [script|shell|exec]:
    < user script to be executed >

}
```
#### Process composition
Process with matching input-output can exist. 
Process 1 --> output --> Input -->  Next Process

#### Process output 
Acces process output with ```.out```
```
workflow {
    foo()
    bar(foo.out)
    bar.out.view()
}
```

When a process defines 2/more output channels. Each can be accesed like:
out[0]
out[1] 

#### Processes named output 
To assing a name to the output of the process use the option "emit". 
This name can be used later to reference the channel in the workflow 

```
process foo {
  output:
    path '*.bam', emit: samples_bam

  '''
  your_command --here
  '''
}

workflow {
    foo()
    foo.out.samples_bam.view()
}
```
#### Process named stdout 

Same, "emit" can be used to call the stdout 
 ```
process sayHello {
  input:
    val cheers
  output:
   stdout emit:verbiag
  '''
  your_command --here
  '''
}

workflow {
    foo()
    foo.out.samples_bam.view()
}
```
### Script

### Input 
### Output 
### When 
### Directives 
