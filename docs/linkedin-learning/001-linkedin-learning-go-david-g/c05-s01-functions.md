
# Define and call functions

* Functions are a key component of Go programming.
* Functions can be used to perform specific tasks and can be called from other parts of the program.
* Functions can take arguments and return values.
* Functions can be used to organize code and make it more reusable.

## Function Syntax

* Function names are followed by parentheses and if no values are being returned, the parentheses can be empty.
* Function arguments are declared with a name and a type.
* If a function is going to return a value, the return type is declared after the function's closing parentheses.
* Functions can be called from other parts of the program using the function name and parentheses.

## Passing Arguments to Functions

* Arguments can be passed to functions using the function name and parentheses.
* Each argument must be declared with a name and a type.
* If a function is going to return a value, the return type is declared after the function's closing parentheses.

## Returning Multiple Values from Functions

* Functions can return multiple values by declaring a list of types wrapped in parentheses after the function's closing parentheses.
* The return statement can be used to return multiple values.

## Example Code

```go
func fourLoop() {
  fmt.Println("Doing something")
}

func addValues(value1 int, value2 int) int {
  return value1 + value2
}

func addAllValues(values ...int) int {
  total := 0
  for _, v := range values {
    total += v
  }
  return total
}

func main() {
  fmt.Println(fourLoop())
  some := addValues(5, 8)
  fmt.Println(some)
  multiSum := addAllValues(1, 2, 3)
  fmt.Println(multiSum)
  multiCount, _ := addAllValues(1, 2, 3)
  fmt.Println(multiCount)
}
```

Note: This is a summary of the transcript and may not be a complete or accurate representation of the code.
