fmtpolice
=========

gofmt and golint checking script to be used as part of Go tests

**Example `fmtpolice` usage:**

```yaml
---
# .travis.yml
language: go
install:
- go get -t ./...
- curl -sLOf https://raw.githubusercontent.com/rafecolton/fmtpolice/master/fmtpolice
script:
- go test ./...
- bash fmtpolice
```

**Example `coverage` usage with [`goveralls`](https://github.com/mattn/goveralls):**

```yaml
---
# .travis.yml
language: go
install:
- go get -t ./...
- curl -sLOf https://raw.githubusercontent.com/rafecolton/fmtpolice/master/coverage
- go get -u code.google.com/p/go.tools/cmd/cover || go get -u golang.org/x/tools/cmd/cover
- go get -u github.com/axw/gocov/gocov github.com/mattn/goveralls
script:
- go test ./...
- bash coverage
- ${GOPATH%%:*}/bin/goveralls -coverprofile=gover.coverprofile -repotoken <your-repo-token>
```
