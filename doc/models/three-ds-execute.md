
# Three DS Execute

## Structure

`ThreeDSExecute`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Execute` | `*bool` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    threeDSExecute := models.ThreeDSExecute{
        Execute:              models.ToPointer(false),
    }

}
```

