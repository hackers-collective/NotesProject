# Go / Golang

## Example

```go
package main

import "fmt"

func main() {

 fmt.Println("ScriptKKiddie's Notes")
}
```

## Formatting

The Go development tools include a command ```go fmt```, which automatically reformats the code to match the standard format.

- Enhanced version of ```go fmt``` available called ```goimports``` that also cleans up the import statements. \(```go install golang.org/x/tools/cmd/goimports@latest```\)
- ```goimports -l -w``` \; The ```-l``` flag tells ```goimports``` to print the files with incorrect formatting to the console. The ```-w``` flag tells ```goimports``` to modify the files in-place.

### The Semicolon Insertion Rule

## Linting and Vetting

- ```golint``` | golint ./
- ```go vet``` | go vet ./

- ```golangci-lint``` | golangci-lint run
