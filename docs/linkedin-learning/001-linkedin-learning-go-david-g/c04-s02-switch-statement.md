# Go Switch Statement

* The Go switch statement serves the same purpose as an if-else statement, but its syntax expands on other C-style languages.
* The switch statement is written as `switch expression { ... }`
* The expression can be a simple value or a more complex statement
* The switch statement can include multiple cases, each with a specific value
* The default case is optional and is used to handle values that do not match any of the other cases
* The break statement is not required in Go, but can be used to prevent falling through to other cases
* The `fallthrough` keyword can be used to intentionally fall through to the next case

## Example Code

```go
switch dow := rand.Intn(7) + 1; dow {
case 1:
  result = "Sunday"
case 2:
  result = "Monday"
case 3:
  result = "Tuesday"
case 4:
  result = "Wednesday"
case 5:
  result = "Thursday"
case 6:
  result = "Friday"
case 7:
  result = "Saturday"
default:
  result = "Some other day"
}
```

## Key Takeaways**

* The Go switch statement is a powerful tool for handling multiple cases
* The break statement is not required in Go, but can be used to prevent falling through to other cases
* The fall through keyword can be used to intentionally fall through to the next case
* The switch statement can include multiple cases, each with a specific value
* The default case is optional and is used to handle values that do not match any of the other cases.
