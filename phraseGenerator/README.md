1.  Install go: `make setup-go`
2.  add go to path: `PATH=/usr/local/go/bin:$PATH`
3.  install:

```bash
go mod init example/phraseGen
go get gopkg.in/urfave/cli.v1
go install
```
