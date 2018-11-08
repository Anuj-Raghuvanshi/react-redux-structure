# Building Applications - Permissioning

We utilize [CASL](https://github.com/stalniy/casl) as a way of restricting or providing access to various parts of the application.

### Can Component

There is a `Can` component available in the `src/common/components` directory available for use to conditionally show or hide content based on a user's permissions. It should only be used when rendering components.

```jsx
<Can I="access" a="contact_management">
  <ContactManagement/>
</Can>

<Can not I="access" a="contact_management">
  <AnotherComponent/>
</Can>
```

### Ability Utility

The ability utility can be used outside of rendering a React component. It is available through the `src/common/utilities` directory.

```js
import Ability from 'path/to/common/utilities/ability'

if (Ability.can('access', 'dashboard')) {
  // Can access the dashboard
}

if (!Ability.can('access', 'dashboard')) {
  // Cannot access the dashboard
}
```

### Determining Permissions

Currently, a user's abilities are determined from a Roles API which we map to CASL abilities. The API provides a response similar to this:

```json
{
  "data": {
    "UpdatedAt": "2018-05-25T20:02:27+00:00",
    "Command": {
      "Access": true,
      "SketchHouse": true,
      "DealManagement": false,
      "Contacts": true,
      "LeadAccelerator": true,
      "SmartPlans": true
    },
    "Connect": {
      "Access": true,
      "Referrals": true
    },
    "Version": "1.0.8",
    "Kwuid": 556396,
    "Kelle": {
      "Access": true,
      "Contacts": true,
      "Referrals": true,
      "Calendar": true,
      "Listings": true,
      "LocalInsights": true
    },
    "CreatedAt": "2018-02-01T23:19:31+00:00"
  }
}
```
