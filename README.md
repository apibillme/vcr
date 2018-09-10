# VCR

Save your API requests for testing in fixtures.

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
