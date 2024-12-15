# Create loops with for statements

* The Go for statement is used to iterate through collections of values.
* There are three types of for statements in Go:
  * The basic for statement, which is similar to the for statement in C and Java.
  * The for range statement, which is used to iterate through arrays, slices, and maps.
  * The for loop with a boolean condition, which is used to loop as long as a boolean expression returns true.

## Basic For Statement

* The basic for statement has the following syntax: `for init; condition; post { ... }`
* The init statement is used to initialize a counter variable.
* The condition statement is used to evaluate a boolean expression.
* The post statement is used to update the counter variable.

## For Range Statement

* The for range statement has the following syntax: `for variable := range collection { ... }`
* The variable is used to store the index or value of the current element in the collection.
* The collection is the array, slice, or map being iterated over.

## For Loop with Boolean Condition

* The for loop with a boolean condition has the following syntax: `for condition { ... }`
* The condition is a boolean expression that is evaluated at the beginning of each iteration.

## Break and Continue Statements

* The break statement is used to jump to the end of the current code block.
* The continue statement is used to start back at the beginning of the current code block.

## Goto Statement

* The goto statement is used to jump to a label in the code.
* Labels are declared using the `:` character, and are used to identify a location in the code.

## Example Code

```go
for i := 0; i < len(colors); i++ {
  fmt.Println(colors[i])
}

for _, color := range colors {
  fmt.Println(color)
}

for i, color := range colors {
  fmt.Println(color)
}

for value := 1; value < 10; value++ {
  fmt.Println(value)
  value++
}

sum := 0
for sum < 1000 {
  sum += sum
  fmt.Println(sum)
  if sum > 200 {
    goto end
  }
}

end:
fmt.Println(sum)
```
