# Building Applications - Feature Flags/Toggles

Feature flags allow developers to turn on/off functionality on various platforms and should be used to disable functionality that is either under development or not yet ready for production. To support the use of feature flags, we are using this library for react [garbles/flag](https://github.com/garbles/flag).

In order to use feature flags in your app, you will need to do the following:

1. Add a the new environment variable to each file in the the `env` directory in the root of the application
1. [constants.js](/src/constants.js) Add a new string to the `featureFlagNames` array and set it's value to `process.env.YOUR_ENVIRONMENT_CONSTANT_FROM_STEP_ONE.
1. Add a new `<Flag name={featureFlagNames.YOURFLAGNAME}>` component to wrap the feature that you'd like to enable/disable with your feature.

The [Console](/src/console/views/Console) component utilizes the `FlagsProvider` which passes all of the defined feature flags down to the console apps.

## Feature Flags Example in Referrals

The initial app that is using feature flags is referrals.

- [ReferralSnapshot](/src/referrals/views/ReferralsSnapshot/index.js): This is a sample component that is using the `referralsCreateSelfReferral` flag. This is used to turn a button on/off on the ui.

```jsx
// env file
REFERRALS_CREATE_SELF_REFERRAL = true
```

```jsx
// constants
export const featureFlags = {
  [featureFlagNames.REFERRALS_CREATE_SELF_REFERRAL]: JSON.parse(
    process.env.REFERRALS_CREATE_SELF_REFERRAL
  )
}
```

```jsx
// Component File
<Flag name={featureFlagNames.REFERRALS_CREATE_SELF_REFERRAL}>
  <Button
    label="Enter Referral To Track"
    size="medium"
    theme="primary"
    className="mr-1"
    onClick={this.handleSendSelfReferralClick}
  />
</Flag>
```
