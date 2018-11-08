# Building Applications - Responsive Design

With the exception of a few features, all applications should be mobile-friendly. We don't always receive responsive designs from the UI team, so some of this will require using your best judgement.

We offer a few components and utility classes to help make the applications responsive.

---

### Grid Components

The UI Kit comes with both a `Row` and a `Column` component based off of the [Flexbox Grid Library](http://flexboxgrid.com/).

The `Column` component accepts breakpoint props to adjust the size of the column based on the viewport. Usage is as follows:

```js
import { Column, Row } from 'kwuikit'

<Row>
    <Column xs={12} sm={16} md={4} lg={3}>Column content here!!</Column>
</Row>
```

---

### Utility Classes

The UI Kit comes with many utility classes that include a breakpoint syntax to adjust CSS properties based on viewport. Some common use-cases for these utilities are:

- [Spacing](http://kwuikit.s3-website-us-east-1.amazonaws.com/#spacing)
- [Display](http://kwuikit.s3-website-us-east-1.amazonaws.com/#display)
- [Flex](http://kwuikit.s3-website-us-east-1.amazonaws.com/#flex)

A few examples are:

```jsx
// Padding 1 on xs, padding 3 on sm and padding 5 on md
<div className="p-1 p-sm-3 p-md-5"></div>

// Display inline on small
<div className="d-sm-inline"></div>

// Flex row on md or higher, column on lower
<div className="d-flex flex-column flex-md-row"></div>
```
