# VCR

[![Go Report](https://goreportcard.com/badge/github.com/apibillme/vcr)](https://goreportcard.com/report/github.com/apibillme/vcr) [![GolangCI](https://golangci.com/badges/github.com/apibillme/vcr.svg)](https://golangci.com/r/github.com/apibillme/vcr) [![Travis](https://travis-ci.org/apibillme/vcr.svg?branch=master)](https://travis-ci.org/apibillme/vcr#) [![codecov](https://codecov.io/gh/apibillme/vcr/branch/master/graph/badge.svg)](https://codecov.io/gh/apibillme/vcr) ![License](https://img.shields.io/github/license/apibillme/vcr.svg) ![Maintenance](https://img.shields.io/maintenance/yes/2018.svg) [![GoDoc](https://godoc.org/github.com/apibillme/vcr?status.svg)](https://godoc.org/github.com/apibillme/vcr)


Save your API requests for testing in fixtures.

## Features
* Easy to use
* Works with net/http - fasthttp support upcoming

## Example

Simple:
```go
package examples

import (
  "github.com/apibillme/vcr"
  "net/http"
  "testing"
)

func TestSomeFeature(t *testing.T) {
  // This will automatically create a cassette file at ./fixtures/vcr/my_feature.json
  vcr.Start("my_feature", nil)
  defer vcr.Stop()

  resp, _ := http.Get("http://google.com/")
  if resp.StatusCode != 200 {
    t.Fatalf("Status code is not 200!")
  }
}
```
