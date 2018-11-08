# Redux - Reducers

Since the [actions](actions.md) describe "what happened", reducers specify how the application's state changes in response to what happened. A reducer is a pure function that takes in two arguments - `state` and `action`. Each reducer own's a portion of the global Redux store.

To simplify state updates and prevent side-effects, we make the redux state [immutable](https://facebook.github.io/immutable-js/). Immutable data structures work well with reducers since they don't allow state to be mutated directly.

A complete `reducer.js` will resemble the following:

```js
import { fromJS } from 'immutable'

import { MY_ACTION_TYPE } from './constants'

const initialState = fromJS({
    foo: 'bar',
    isFetching: false,
    someArray: []
})

function myAwesomeReducer(state = initialState, action) => {
    switch(action.type) {
        case MY_ACTION_TYPE:
            return state.set('foo', action.newValue)
        default
            return state
    }
}

export default myAwesomeReducer
```
