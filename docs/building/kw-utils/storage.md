# KW Utilities - Local Storage

The following utilities are available for working with local storage. They should be used over the default JavaScript `localStorage` because they are supported by a wider range of browsers.

### Save data to local storage

```jsx
import { setLocalStorage } from 'kw-utils'

setLocalStorage(name, value)
```

### Get data from local storage

```jsx
import { getLocalStorage } from 'kw-utils'

getLocalStorage(name)
```

### Remove data from local storage

```jsx
import { removeLocalStorage } from 'kw-utils'

removeLocalStorage(name)
```
