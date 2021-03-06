1.  Install go: `make setup-go`
2.  add go to path: `PATH=/usr/local/go/bin:$PATH`
3.  install:

```bash
go mod init example/phraseGen
go get gopkg.in/urfave/cli.v1
touch phraseGenerator.go

```
paste code

```go
package main

import (
	"fmt"
	"gopkg.in/urfave/cli.v1" // imports as package "cli"
	"os"
)

func main() {
	app := cli.NewApp()
	app.Flags = []cli.Flag{
		cli.StringFlag{
			Name:  "phrase",
			Usage: "Print phrase",
		},
		cli.Int64Flag{
			Name:  "count",
			Usage: "Count to print a phrase",
		},
	}

	app.Action = func(c *cli.Context) error {
		sum := 0
		for i := 0; i < c.Int("count"); i++ {
			sum -= i
			fmt.Println(c.String("phrase"))
		}
		return nil
	}

	app.Run(os.Args)
}

```

run it:

```
ec2-user:~/environment/GoCloud/phraseGenerator (main) $ go run phraseGenerator.go --phrase "hello world" --count 5         
hello world
hello world
hello world
hello world
hello world
```


