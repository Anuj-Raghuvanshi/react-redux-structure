# KW Utilities - Cookies

The following utilities are available for working with cookies. These utilities base the cookie on `.command.kw.com` domain name, so they can be used across any subdomains of that base.

### Save cookie

```jsx
import { setDomainCookie } from 'kw-utils'

setDomainCookie(name, value)
```

### Get data from a cookie

```jsx
import { getDomainCookie } from 'kw-utils'

getDomainCookie(name)
```

### Remove the cookie

```jsx
import { removeDomainCookie } from 'kw-utils'

removeDomainCookie(name)
```

### Default Available Cookies

You can build your applications assuming the following cookies exist and can be retrieved:

```jsx
const userDetails = getDomainCookie('user_details')

{
  "first_name": "Nicole",
  "last_name": "Burton",
  "email": "kelle@kw.com",
  "username": "",
  "kwuid": "556396"
}
```

```jsx
const commandSession = getDomainCookie('command_session')

{
  "access_token": "foo",
  "expires_in": 216000,
  "token_type": "Bearer",
  "refreshToken": "bar",
  "refresh_token": "bar",
  "expires_at": 1528355411747
}
```
