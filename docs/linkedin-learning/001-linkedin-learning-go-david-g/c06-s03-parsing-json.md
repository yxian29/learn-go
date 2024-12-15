# Parsing JSON-formatted Text

* Use the `encoding/json` package to parse JSON-formatted text.
* Create a custom type to represent the structured data.
* Use the `json.Unmarshal` function to unmarshal the JSON data into the custom type.
* Use the `json.NewDecoder` function to create a decoder for the JSON data.

## Example Code

```go
package main

import (
  "encoding/json"
  "fmt"
  "strings"
)

type Tour struct {
  Name  string
  Price string
}

func toursFromJSON(content string) ([]Tour, error) {
  tours := make([]Tour, 0, 20)
  decoder := json.NewDecoder(strings.NewReader(content))
  err := decoder.Token()
  if err != nil {
    panic(err)
  }
  for more, err := decoder.Token(); err == nil; more, err = decoder.Token() {
    tour := Tour{}
    err = decoder.Decode(&tour)
    if err != nil {
      panic(err)
    }
    tours = append(tours, tour)
  }
  return tours, err
}

func main() {
  content := []byte(`{"name":"Tour 1","price":"$100.00"},{"name":"Tour 2","price":"$200.00"}`)
  tours, err := toursFromJSON(string(content))
  if err != nil {
    panic(err)
  }
  for _, tour := range tours {
    fmt.Println(tour.Name)
  }
}
```

## Key Takeaways

* Go has a JSON package that lets you easily create and read JSON-formatted text.
* Use the `encoding/json` package to parse JSON-formatted text.
* Create a custom type to represent the structured data.
* Use the `json.Unmarshal` function to unmarshal the JSON data into the custom type.
* Use the `json.NewDecoder` function to create a decoder for the JSON data.