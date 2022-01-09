# Hello World Go

[Based on Official Tutorial](https://go.dev/doc/tutorial/getting-started)

```bash
go mod init example/hello
touch hello.go
```
Paste into `hello.go`

```bash
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

`go run .`

Should output the following:

```
ec2-user:~/environment/GoCloud/hello (main) $ go run .
Hello, World!
```
