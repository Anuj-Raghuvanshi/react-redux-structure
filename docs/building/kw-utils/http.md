# KW Utilities - HTTP Requests

### Standard Requests

The bulk of all API requests sent out of the front end applications should use the `commandAxios` utility. This utility creates an instance of [axios](https://github.com/axios/axios) with the `Authorization` header already applied and the base URL for the Keller Cloud.

It is used the same way as the default `axios` instance:

```
import { commandAxios } from 'kw-utils'

commandAxios.post('/contacts', {
    first_name: 'Gary',
    last_name: 'Keller'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

### Debounced Requests

When performing certain taxing actions such as searches or auto-saving, it's more appropriate to debounce the API request. Debouncing limits the rate at which a function can actually execute. Each debounced function uses the base `commandAxios` instance described above.

There are four debounced utilities included:

* `debounceHttpGet(endpoint, onSuccess, onError)`
* `debounceHttpPatch(endpoint, payload, onSuccess, onError)`
* `debounceHttpPost(endpoint, payload, onSuccess, onError)`
* `debounceHttpPut(endpoint, payload, onSuccess, onError)`

These functions differ slightly from the above in terms of resolving the `Promise`. You cannot chain `.then()` or `.catch()` onto the debounced functions. They provide `onSuccess` and `onError` callbacks.
