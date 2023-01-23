### DSL2
Specify the syntax extension
```
nextflow.enable.dsl=2
```
### Functions

Custom functions: 

```
def <function name> ( arg1, arg, .. ) {
    <function body>
}
```
Example: 
```
def hello_world() {
	"Hello world"
}

def bar(alpha, omega) {
	alpha +omega
}
```
Function hello_world, returns the string "hello world" and function bar reutrns the sum of the two parameters. 

```return```
Keyword to explicit exit a function and return specific value 

### [[processes]]
Separated: 
- Definition of a process (see  [[processes]])
- Invocation of a process 

Process definition
Process composition
Process output 
Process named output
Process named stdout

#### Workflows

Workflow allows to define sub-workflow components that call [[processes]] & [[operators]]
```

workflow my_pipeline {
    foo()
    bar( foo.out.collect() )
}
```

Example: Workflow name "my_pipeline"

Workflow Parameters: 
- Can access any variable/ parameters defined outside the workflow 
```
params.data = "/some/data/file"
workflow my_pipeline {
	if (params.data)
		bar(params.data)
	else
		bar(foo())
}
```
Workflow Input
Workflow Output 
Workflow named Output 
Workflow entrypoint
Workflow composition

#### Modules 

Module inclusion
Module directory
Module inclusions
Module aliases
Module parameters
Module templates 
Module 