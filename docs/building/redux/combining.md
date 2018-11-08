# Redux - Combining Reducers

In order to combine all the reducers to pass into the the Redux `<Provider>` as the store, we use the `combineReducers` utility.

Sinec we're using **Immutable** data structures, we need to use the Immutable version of `combineReducers`

```js
// reducer.js - in app root

import { combineReducers } from 'redux-immutable'

import FirstReducer from './modules/FirstReducer/reducer'
import SecondReducer from './modules/SecondReducer/reducer'

const reducers = combineReducers({
  firstReducer: FirstReducer,
  secondReducer: SecondReducer
})

export default reducers
```
