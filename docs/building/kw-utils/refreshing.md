# KW Utilities - Token Refreshing

When the user first logs in, the session is stored with an `expired_at` property added to the response that is a timestamp of when the token expires.

Every API request made with the `commandAxios` utility, including debounced utilities, check to see if that token has or will expire within the next five minutes and should be refreshed.

In the event that a user was sitting idle in the application and the token completely expired, the `commandAxios` utility will catch the 401 error that gets thrown when they return and begin making requests again and attempt to refresh it.

Any error caught when attempting to refresh the token will result in logging the user out of the application. They will be sent to the log in page with a `redirectTo` query paramter appended to the URL to send them back to where they were after logging back in.
