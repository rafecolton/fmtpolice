fmtpolice
=========

gofmt and golint checking script to be used as part of Go tests

Example `fmtpolice` usage:

```yaml
---
# .travis.yml
language: go
install:
- go get -t ./...
- curl -sLO https://raw.githubusercontent.com/rafecolton/fmtpolice/master/fmtpolice && chmod +x fmtpolice
script:
- go test ./...
- ./fmtpolice
```

Example `coverage` usage with [`goveralls`](https://github.com/mattn/goveralls):

```yaml
---
# .travis.yml
language: go
install:
- go get -t ./...
- curl -sLO https://raw.githubusercontent.com/rafecolton/fmtpolice/master/coverage && chmod +x coverage
- go get -u code.google.com/p/go.tools/cmd/cover || go get -u golang.org/x/tools/cmd/cover
- go get -u github.com/axw/gocov/gocov github.com/mattn/goveralls
script:
- go test ./...
- ./coverage
- ${GOPATH%%:*}/bin/goveralls -coverprofile=gover.coverprofile -repotoken <your-repo-token>
```
