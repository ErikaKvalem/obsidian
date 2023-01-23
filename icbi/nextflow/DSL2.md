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

### Process [[processes]]

