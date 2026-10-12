
# Api Error Response Exception

## Structure

`ApiErrorResponseException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TraceId` | `*string` | Optional | - |
| `Error` | [`*models.ApiErrorModel`](../../doc/models/api-error-model.md) | Optional | - |

## Example

```go
if err != nil {
    switch typedErr := err.(type) {
    case *errors.ApiErrorResponseException:
        log.Fatalln(typedErr)
    default:
        log.Fatalln(err)
    }
}
```

