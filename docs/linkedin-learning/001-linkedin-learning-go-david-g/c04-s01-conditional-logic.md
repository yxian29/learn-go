# Program conditional logic

- Go's if statement syntax is similar to C and Java, but does not require parentheses around the Boolean condition.
- The if statement is written as `if condition { ... }`
- The condition can be a simple expression or a more complex statement
- The opening brace of a code block must be on the same line as the preceding statement
- The if statement can also include an initial statement that is part of the if statement, used to initialize variables
- The initial statement is written as `if condition { ...; ... }`
- The initial statement can be used to initialize variables before the condition is evaluated

## Example Code

```go
if answer < 0 {
  result = "less than zero"
} else if answer == 0 {
  result = "equals zero"
} else {
  result = "greater than zero"
}
```

## Key Takeaways

Go's if statement syntax is similar to C and Java, but with some key differences
The opening brace of a code block must be on the same line as the preceding statement
The if statement can also include an initial statement that is part of the if statement, used to initialize variables