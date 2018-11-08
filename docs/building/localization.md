# Building Applications - Localization

The following rules/standards should be adhered to in order to ensure the applications function properly across different locales.

### Dates

When saving dates and times to the server, they should be converted from the user's local timezone to UTC. This can be achieved using the `moment` library:

```js
moment()
  .utc()
  .format('YYYY-MM-DDTHH:mm:ssZ')
```

The reverse is true when displaying dates from the server. Since they will be returned as UTC, they will need to be converted to the user's local timezone. We currently "guess" the user's timezone until we have a more robust way to set the timezone:

```js
const tz = moment.tz.guess()
moment(date, 'YYYY-MM-DDTHH:mm:ssZ').tz(tz)
```
