# LocationsApi

All URIs are relative to *https://api.myptv.com/geocoding-batch/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createLocationsByAddresses**](LocationsApi.md#createlocationsbyaddresses) | **POST** /locations/by-addresses |  |
| [**createLocationsByPositions**](LocationsApi.md#createlocationsbypositions) | **POST** /locations/by-positions |  |
| [**createLocationsByTexts**](LocationsApi.md#createlocationsbytexts) | **POST** /locations/by-texts |  |
| [**deleteLocationsByAddresses**](LocationsApi.md#deletelocationsbyaddresses) | **DELETE** /locations/by-addresses/{id} |  |
| [**deleteLocationsByPositions**](LocationsApi.md#deletelocationsbypositions) | **DELETE** /locations/by-positions/{id} |  |
| [**deleteLocationsByTexts**](LocationsApi.md#deletelocationsbytexts) | **DELETE** /locations/by-texts/{id} |  |
| [**getLocationsByAddresses**](LocationsApi.md#getlocationsbyaddresses) | **GET** /locations/by-addresses/{id} |  |
| [**getLocationsByAddressesStatus**](LocationsApi.md#getlocationsbyaddressesstatus) | **GET** /locations/by-addresses/{id}/status |  |
| [**getLocationsByPositions**](LocationsApi.md#getlocationsbypositions) | **GET** /locations/by-positions/{id} |  |
| [**getLocationsByPositionsStatus**](LocationsApi.md#getlocationsbypositionsstatus) | **GET** /locations/by-positions/{id}/status |  |
| [**getLocationsByTexts**](LocationsApi.md#getlocationsbytexts) | **GET** /locations/by-texts/{id} |  |
| [**getLocationsByTextsStatus**](LocationsApi.md#getlocationsbytextsstatus) | **GET** /locations/by-texts/{id}/status |  |



## createLocationsByAddresses

> IdResponse createLocationsByAddresses(addressesRequest, countryFilter, language, totalScoreType)



Creates a search request for locations based on a list of structured address inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { CreateLocationsByAddressesRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // AddressesRequest
    addressesRequest: ...,
    // Array<string> | A comma-separated list of country codes according to [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) or [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) if referring to a subdivision. The search will only consider data from countries with these codes. If no filter is specified, all countries are taken into account. However, empty values are not allowed.     If a given subdivision code is not supported, only the first two digits referring to the country are considered in the search and a **warningCode** `GEOCODING_COUNTRY_FILTER_MODIFIED` is returned with the response. (optional)
    countryFilter: ["DE","FR"],
    // string | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. (optional)
    language: en,
    // TotalScoreType | Defines how Location.quality.totalScore is calculated.    * `INPUT_AND_RESULT_BASED` - The total score is calculated by comparing the result against the input.    * `RESULT_BASED` - The total score is calculated by classifying result attributes.      This parameter is experimental and may change at any time in the future. (optional)
    totalScoreType: ...,
  } satisfies CreateLocationsByAddressesRequest;

  try {
    const data = await api.createLocationsByAddresses(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **addressesRequest** | [AddressesRequest](AddressesRequest.md) |  | |
| **countryFilter** | `Array<string>` | A comma-separated list of country codes according to [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) or [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) if referring to a subdivision. The search will only consider data from countries with these codes. If no filter is specified, all countries are taken into account. However, empty values are not allowed.     If a given subdivision code is not supported, only the first two digits referring to the country are considered in the search and a **warningCode** &#x60;GEOCODING_COUNTRY_FILTER_MODIFIED&#x60; is returned with the response. | [Optional] |
| **language** | `string` | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. | [Optional] [Defaults to `undefined`] |
| **totalScoreType** | `TotalScoreType` | Defines how Location.quality.totalScore is calculated.    * &#x60;INPUT_AND_RESULT_BASED&#x60; - The total score is calculated by comparing the result against the input.    * &#x60;RESULT_BASED&#x60; - The total score is calculated by classifying result attributes.      This parameter is experimental and may change at any time in the future. | [Optional] [Defaults to `undefined`] [Enum: INPUT_AND_RESULT_BASED, RESULT_BASED] |

### Return type

[**IdResponse**](IdResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createLocationsByPositions

> IdResponse createLocationsByPositions(positionsRequest, language, minimumPopulation)



Creates a search request for locations based on a list of positions.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { CreateLocationsByPositionsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // PositionsRequest
    positionsRequest: ...,
    // string | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. (optional)
    language: en,
    // number | If specified, the response contains only the nearest city or town with at least the given population. The **locationType** of this result will be _LOCALITY_, street information will not be returned.  This parameter is in an experimental state and may change at any time. (optional)
    minimumPopulation: 50000,
  } satisfies CreateLocationsByPositionsRequest;

  try {
    const data = await api.createLocationsByPositions(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **positionsRequest** | [PositionsRequest](PositionsRequest.md) |  | |
| **language** | `string` | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. | [Optional] [Defaults to `undefined`] |
| **minimumPopulation** | `number` | If specified, the response contains only the nearest city or town with at least the given population. The **locationType** of this result will be _LOCALITY_, street information will not be returned.  This parameter is in an experimental state and may change at any time. | [Optional] [Defaults to `undefined`] |

### Return type

[**IdResponse**](IdResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createLocationsByTexts

> IdResponse createLocationsByTexts(textsRequest, countryFilter, language, cleanInput)



Creates a search request for locations based on a list of single-field text inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { CreateLocationsByTextsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // TextsRequest
    textsRequest: ...,
    // Array<string> | A comma-separated list of country codes according to [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) or [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) if referring to a subdivision. The search will only consider data from countries with these codes. If no filter is specified, all countries are taken into account. However, empty values are not allowed.     If a given subdivision code is not supported, only the first two digits referring to the country are considered in the search and a **warningCode** `GEOCODING_COUNTRY_FILTER_MODIFIED` is returned with the response. (optional)
    countryFilter: ["DE","FR"],
    // string | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. (optional)
    language: en,
    // boolean | If set to `true`, the service will try (for certain countries) to clean the input in a pre-processing step. This helps to expedite processing if the input is a free-form text that may contain garbage. This flag may influence the scores in the response. For more details see the corresponding [concept](./concepts/clean-input).      This parameter is experimental and may change at any time in the future. (optional)
    cleanInput: true,
  } satisfies CreateLocationsByTextsRequest;

  try {
    const data = await api.createLocationsByTexts(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **textsRequest** | [TextsRequest](TextsRequest.md) |  | |
| **countryFilter** | `Array<string>` | A comma-separated list of country codes according to [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) or [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) if referring to a subdivision. The search will only consider data from countries with these codes. If no filter is specified, all countries are taken into account. However, empty values are not allowed.     If a given subdivision code is not supported, only the first two digits referring to the country are considered in the search and a **warningCode** &#x60;GEOCODING_COUNTRY_FILTER_MODIFIED&#x60; is returned with the response. | [Optional] |
| **language** | `string` | The preferred language for the response formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. By default the service uses the language spoken in the country or region of the result. In case the given preferred language is not available in the data, the default language is used. | [Optional] [Defaults to `undefined`] |
| **cleanInput** | `boolean` | If set to &#x60;true&#x60;, the service will try (for certain countries) to clean the input in a pre-processing step. This helps to expedite processing if the input is a free-form text that may contain garbage. This flag may influence the scores in the response. For more details see the corresponding [concept](./concepts/clean-input).      This parameter is experimental and may change at any time in the future. | [Optional] [Defaults to `false`] |

### Return type

[**IdResponse**](IdResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteLocationsByAddresses

> deleteLocationsByAddresses(id)



Deletes the results of a locations search based on a list of structured address inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { DeleteLocationsByAddressesRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteLocationsByAddressesRequest;

  try {
    const data = await api.deleteLocationsByAddresses(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteLocationsByPositions

> deleteLocationsByPositions(id)



Deletes the results of a locations search based on a list of positions.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { DeleteLocationsByPositionsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteLocationsByPositionsRequest;

  try {
    const data = await api.deleteLocationsByPositions(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteLocationsByTexts

> deleteLocationsByTexts(id)



Deletes the results of a locations search based on a list of single-field text inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { DeleteLocationsByTextsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteLocationsByTextsRequest;

  try {
    const data = await api.deleteLocationsByTexts(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByAddresses

> LocationsSearchResponse getLocationsByAddresses(id)



Retrieves the results of a locations search based on a list of structured address inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByAddressesRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByAddressesRequest;

  try {
    const data = await api.getLocationsByAddresses(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchResponse**](LocationsSearchResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByAddressesStatus

> LocationsSearchStatusResponse getLocationsByAddressesStatus(id)



Retrieves the status of a locations search based on a list of structured address inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByAddressesStatusRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByAddressesStatusRequest;

  try {
    const data = await api.getLocationsByAddressesStatus(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchStatusResponse**](LocationsSearchStatusResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByPositions

> LocationsSearchResponse getLocationsByPositions(id)



Retrieves the results of a locations search based on a list of positions.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByPositionsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByPositionsRequest;

  try {
    const data = await api.getLocationsByPositions(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchResponse**](LocationsSearchResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByPositionsStatus

> LocationsSearchStatusResponse getLocationsByPositionsStatus(id)



Retrieves the status of a locations search based on a list of positions.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByPositionsStatusRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByPositionsStatusRequest;

  try {
    const data = await api.getLocationsByPositionsStatus(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchStatusResponse**](LocationsSearchStatusResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByTexts

> LocationsSearchResponse getLocationsByTexts(id)



Retrieves the results of a locations search based on a list of single-field text inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByTextsRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByTextsRequest;

  try {
    const data = await api.getLocationsByTexts(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchResponse**](LocationsSearchResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLocationsByTextsStatus

> LocationsSearchStatusResponse getLocationsByTextsStatus(id)



Retrieves the status of a locations search based on a list of single-field text inputs.

### Example

```ts
import {
  Configuration,
  LocationsApi,
} from '';
import type { GetLocationsByTextsStatusRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new LocationsApi(config);

  const body = {
    // string | The id of the batch geocoding request.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetLocationsByTextsStatusRequest;

  try {
    const data = await api.getLocationsByTextsStatus(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The id of the batch geocoding request. | [Defaults to `undefined`] |

### Return type

[**LocationsSearchStatusResponse**](LocationsSearchStatusResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

