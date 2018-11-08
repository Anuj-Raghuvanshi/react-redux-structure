# Redux - API Middleware

We utilize [Redux Axios Middleware](https://github.com/svrcekmichal/redux-axios-middleware) to simplify HTTP requests when using Axios and Redux.

### Adding the Middleware to the Store

You will need to configure the store to utilize the middleware:

```js
// Import the middleware
import axiosMiddleware from 'redux-axios-middleware'

// Import the commandAxios instance for use with the middleware
import { commandAxios } from 'kw-utils'

// Where you initialize your store with middleware, add the axios middleware
const createStoreWithMiddleware = applyMiddleware(
  axiosMiddleware(commandAxios)
  // .other middlewares here (i.e. thunk)
)(createStore)
```

### Usage

The package's docs provide more in-depth usage instructions, but you can create an action creator similar to this in order to use the middleware:

```js
export const myAPIRequestAction = someValue => ({
  types: [LOAD_TYPE, SUCCES_TYPE, FAIL_TYPE],
  payload: {
    request: {
      url: '/path/to/api',
      method: 'get'
    },
    someValue
  }
})
```

> LOAD_TYPE will be dispatched on start, then SUCCESS_TYPE or FAIL_TYPE after request result

You can simplify the naming of the types by passing a single `type` property at which time the middleware handles creating the additional types:

```js
export const myAPIRequestAction = someValue => ({
  type: MY_AWESOME_TYPE,
  payload: {
    request: {
      url: '/path/to/api',
      method: 'get'
    },
    someValue
  }
})
```

This would create 2 additional types automatically based on the original constant:

- `MY_AWESOME_TYPE + '_SUCCESS'`
- `MY_AWESOME_TYPE + '_FAIL'`

We provide utility functions for utilizing these in a reducer:

```js
import { failure, success } from 'utilities/redux'
import { MY_AWESOME_TYPE } from './constants'

// in the reducer switch:
switch (action.type) {
  case MY_AWESOME_TYPE:
  // for the start of the request
  case success(MY_AWESOME_TYPE):
  // for when the request succeeds
  case failure(MY_AWESOME_TYPE):
  // for when the request fails
}
```
