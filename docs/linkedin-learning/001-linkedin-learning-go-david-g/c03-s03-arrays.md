# Store Ordered Values in Arrays

## Arrays in Go

- An array is an ordered collection of values or references.
- Arrays are useful for storing small amounts of data, but they have limitations (e.g., no built-in methods to sort or add/remove items).
- It's generally recommended to use slices instead of arrays for ordered collections of values.

## Declaring and Assigning to Arrays

- Declare an array with the number of items in brackets followed by the type of values.
- Explicitly set each individual value using the equals operator (no colon equals).
- Array index starts at 0, not 1.
- Example:
  - `colors := [3]string` declares a new variable named colors and assigns it an array of three strings.

## Declaring Arrays in a Single Statement

- Declare an array with a single statement using the syntax: `[n]type = value`.
- Example:
  - `numbers := [5]int = {1, 2, 3, 4, 5}` declares and assigns an array of five integers.

## Accessing Array Elements

- Use array index to access individual elements (e.g., `colors[0]` returns the first element).
- Example:
  - `fmt.Println(colors[0])` prints "red".

## Array Length

- Use the built-in `len()` or `length()` function to get the number of items in an array.
- Example:
  - `fmt.Println(len(colors))` prints 3.

## Arrays as Objects

- In Go, arrays are objects that can be passed to functions.
- A copy is made of the array when it's passed to a function.
- However, this limits the functionality of arrays (e.g., no built-in methods to sort or add/remove items).

## Sample Code

```go
package main

import "fmt"

func main() {
	var colors [3]string
	colors[0] = "Red"
	colors[1] = "Green"
	colors[2] = "Blue"
	fmt.Println(colors)
	fmt.Println(colors[0])

	var numbers = [5]int{5, 3, 2, 1, 4}
	fmt.Println(numbers)

	fmt.Println("Number of colors:", len(colors))
	fmt.Println("Number of numbers:", len(numbers))
}
```
