# Redux - Selectors

Selectors provide us a convenient way of retrieving data out of the Redux store. We use the [reselect](https://github.com/reduxjs/reselect) library to make this possible.

Assuming the following Redux store...

```json
{
  "contacts": {
    "contactList": [],
    "isFetching": false
  },
  "another": {
    "data": {},
    "isFetching": false
  }
}
```

If we wanted to create selectors to pull out the `contacts.contactList` and `contacts.isFetching` state, we would create the following in `selectors.js`

```js
import { createSelector } from 'reselect'

const selectContactReducer = () => state => state.get('contact')

export const getContactList = () =>
  createSelector(selectContactReducer(), state => {
    return state.get('contactList').toJS()
  })

export const getIsFetching = () =>
  createSelector(selectContactReducer(), state => {
    return state.get('isFetching')
  })
```

Some things to note:

- The `getContactList` selector chains the `toJS()` method to the end of the getter. This is an immutability helper that converts the immutable `List` back to a standard `Array`
- The `getIsFetching` selector grabs the data from `contacts.isFetching` not `another.isFetching`. This is because we use the `createSelector` utility to scope the selector to the `contacts` state.
