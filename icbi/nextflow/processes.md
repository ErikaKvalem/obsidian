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

### Script

### Input 
### Output 
### When 
### Directives 
