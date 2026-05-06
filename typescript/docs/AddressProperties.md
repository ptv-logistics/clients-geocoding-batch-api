
# AddressProperties


## Properties

Name | Type
------------ | -------------
`country` | string
`state` | string
`locality` | string
`postalCode` | string
`street` | string
`houseNumber` | string

## Example

```typescript
import type { AddressProperties } from ''

// TODO: Update the object below with actual values
const example = {
  "country": null,
  "state": null,
  "locality": null,
  "postalCode": null,
  "street": null,
  "houseNumber": null,
} satisfies AddressProperties

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AddressProperties
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


