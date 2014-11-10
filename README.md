fmtpolice
=========

gofmt and golint checking script to be used as part of Go tests

Example usage:

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
