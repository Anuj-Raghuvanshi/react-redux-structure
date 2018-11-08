# Redux - Thunk

The default Redux actions return an object. This limits the ability to perform other functions within the action - enter [Redux Thunk](https://github.com/reduxjs/redux-thunk). Thunk allows you to return a function from your action instead of an object.

```js
import axios from 'axios'

import { MY_ACTION_TYPE, ANOTHER_ACTION } from './constants'

export function myAsyncAction() => {
    return (dispatch, getState) => {
        axios.get('foo/bar').then((resp) => {
            dispatch({
                type: MY_ACTION_TYPE,
                payload: resp
            })
        }).catch((err) => {
            dispatch({
                type: ANOTHER_ACTION,
                payload: err
            })
        })
    }
}
```

Some functions provided by Thunk:

- `dispatch` allows you to fire actions at any point in the execution.
- `getState` allows you to retrieve data out of the Redux store
