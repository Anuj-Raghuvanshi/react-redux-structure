# KW Utilities - User Session

If you need to work with the current user session, the following utilities are available:

### Retrieve the current user session

Retrieves the current user session out of storage and includes the `expires_at` timestamp.

```jsx
import { getUserSession } from 'kw-utils'

getUserSession()

{
    "access_token": "foo",
    "expires_in": 216000,
    "expires_at": 1524978874519,
    "token_type": "Bearer",
    "refreshToken": "bar",
    "refresh_token": "bar"
}
```

### Save a new user session

Saves a user session into storage and adds the `expires_at` timestamp to the object based on the `expires_in` time.

```jsx
import { getUserSession } from "kw-utils";

saveUserSession({
  access_token: "foo",
  expires_in: 216000,
  token_type: "Bearer",
  refreshToken: "bar",
  refresh_token: "bar"
});
```
