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
- R