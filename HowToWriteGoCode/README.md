# How to write Go code

<https://golang.org/doc/code.html>

Package - source files in tyhe same directory. Functions, types, variables and constants.

A repo contains 1+ modules. Usually one one module, at the root. (So a bit like Terraform then...) Add a go.mod to declare the module path which is the import path prefix for all packages in the module. The import path prefix should also be where the repo is.

An import path to import a package.

Created hello.go, then ran `go install example.com/user/hello`.

Installed to $GOBIN.

```go
go env -w GOPATH=$HOME/go
go env -w GOBIN=$HOME/go/bin
go env -u GOBIN
```

Upper case functions are _exported_.

Using remote modules auto downloads then updates go.sum and go.mod.

Downloaded to $GOPATH/pkg/mod, e.g.:

```bash
/git/go/HowToWriteGoCode (master) $ ll ~/go/pkg/mod/github.com/google/
total 4
dr-x------ 3 richeney richeney 4096 Apr  8 16:28 go-cmp@v0.4.0
```

You can clear that cache out:

```bash
/git/go/HowToWriteGoCode (master) $ go clean -modcache
/git/go/HowToWriteGoCode (master) $ ll ~/go/pkg/
total 4
drwxr-xr-x 3 richeney richeney 4096 Apr  8 16:04 sumdb
```
