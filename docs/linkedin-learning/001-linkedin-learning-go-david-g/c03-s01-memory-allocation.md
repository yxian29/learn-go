# How Memory is Allocated and Managed

- When running a Go application, it depends on the Go runtime installed on your computer.
- The runtime operates in the background and manages memory for you.
- To initialize complex types like maps, use `make()` or `new()`.
  - `new()` allocates memory but doesn't initialize it.
  - `make()` both allocates and initializes memory.
- Example code:
  - Declare a map with `new()`: `M := make(map[string]int)`
  - Add an entry to the map: `M["theAnswer"] = 42`
  - Try to output the contents of the map, but it will crash due to zero memory storage
- Fix by wrapping the declaration in `make()`: `M := make(map[string]int)`
- The garbage collector automatically de-allocates memory:
  - Runs in the background and looks for objects out of scope or set to nil
  - Returns memory to the pool, reducing the need for manual memory management
- Go 1.5 introduced a rebuilt garbage collector with low latency to reduce pauses.
- Memory is unlikely to be noticeable even on slower computers due to the fast garbage collection process.
