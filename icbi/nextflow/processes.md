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
### Script

### Input 
### Output 
### When 
### Directives 
