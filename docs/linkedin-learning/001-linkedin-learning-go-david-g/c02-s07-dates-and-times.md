# Work with dates and times

## Notes

### Using the Time Package in Go

- The `time` package can be used to manage dates and times, including math operations, time zone management, and more.
- A variable declared with the `time` type encapsulates everything you need for both dates and times.

### Creating a Timestamp

- Add the `time` package to your import block.
- Create a variable `n` in the main function and get its value from `time.Now`.
- Output the string "I recorded this video at" with the timestamp `n`.

### Creating an Explicit Date/Time Value

- Create a variable `t` and use `time.Date` to create an explicit date/time value.
  - Parameters: year, month, day, hour, minute, second, nanosecond, location.
  - Example: `time.Date(2009, time.November, 10, 23, 0, 0, 0, time.UTC)`.
- Output the formatted date/time value with `Println` and `t.Format`.

### Formatting Options

- Use a layout string to control the formatting of the date/time value.
  - Example: `time.ANSIC` for a cleaner and easier-to-read format that includes the day of the week.

### Parsing a String

- Select a formatted string, copy it to the clipboard, and paste it into your code with quotes wrapped around it.
- Use `time.Parse` to get its value back as a time object.
  - Example: `time.Parse("2009-11-10 23:00:00 UTC", "I recorded this video at")`.
- Ignore the error object returned by `parse` using a comma underscore.

### Time Object Functions

- The `time` object has many useful functions, including:
  - Adding dates together
  - Special kinds of formatting
  - Patterns for complete flexibility in formatting date/time values.

## Sample Code

```go
package main

import (
	"fmt"
	"time"
)

func main() {

	n := time.Now()
	fmt.Println("I recorded this video at ", n)

	t := time.Date(2024, time.November, 10, 23, 0, 0, 0, time.UTC)
	fmt.Println("Go launched at ", t)
	fmt.Println(t.Format(time.ANSIC))

	parsedTime, _ := time.Parse(time.ANSIC, "Sun Nov 10 23:00:00 2024")
	fmt.Printf("The type of parsedTime is %v\n", parsedTime)
}
```