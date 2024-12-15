# Reference Values with Pointers

- Go supports pointers like C and similar languages:
  - Variables that store memory addresses of other variables
  - Declare a pointer with a type (e.g., -int), but don't have to point it at an initial variable
- Declaring a pointer:
  - `var p -int` declares a pointer to an integer
  - No asterisk means the pointer is nil (no memory address assigned)
- Assigning values to pointers:
  - If you only assign to `p`, it will be nil
  - To initialize a pointer, use `p = &x` where `x` is another variable
- Pointer syntax:
  - `&x` gets the memory address of `x`
  - `-p` dereferences a pointer (gets the value pointed to)
- Examples:
  - Declaring a pointer and initializing it with `&anInt`
  - Creating a new floating-point value `value1` and assigning its memory address to `pointer1`
  - Using pointers to output values
  - Modifying values through pointers and observing effects on original variables
- Pointers in Go are similar to those in Java, C#, C, and other similar languages:
  - Can be initialized with a value or set to point at another variable
  - Can be changed at runtime to point from one value to another

## Sample Code

```go
package main

import "fmt"

func main() {
	anInt := 42
	var p = &anInt
	fmt.Println("Value of p:", *p)

	value1 := 42.13
	pointer1 := &value1
	fmt.Println("Value1:", *pointer1)

	*pointer1 = *pointer1 / 31
	fmt.Println("Pointer 1:", *pointer1)
	fmt.Println("Value 1:", value1)
}
```