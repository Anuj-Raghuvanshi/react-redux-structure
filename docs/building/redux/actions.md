# Redux - Actions

Reducer's update their state in response to actions. Actions are simple JavaScript functions that return an object which, at a minimum, has a `type` property. The `type` of the action should be referencing a defined [constant](constants.md). Actions should describe "what happened".

The most basic `action.js` will resemble:

```js
import { MY_ACTION_TYPE } from './constants'

export function myReduxAction = () => {
    return {
        type: MY_ACTION_TYPE
    }
}
```

---

You can optionally pass additional information with the action in the form of other object properties:

```js
import { MY_ACTION_TYPE } from './constants'

export function myReduxAction = () => {
    return {
        type: MY_ACTION_TYPE,
        foo: 'bar',
        another: true
    }
}
```

Need to perform async operation in your action? Check out [thunk](thunk.md).
