# Building Applications - Building Components

### Type Checking with props

Define [`propTypes`](https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes) and [`defaultProps`](https://reactjs.org/docs/typechecking-with-proptypes.html#default-prop-values) where applicable.

```js
import { number, string } from 'prop-types'

MyComponent.propTypes = {
  foo: string.isRequired,
  bar: bool
}
MyComponent.defaultProps = {
  bar: false
}
```

### Styling Components

When adding CSS to components, you should create a `styles.scss` file adjacent to the component file:

```
.
└── MyComponent
    ├── MyComponent.js
    └── styles.scss
```

Create any SCSS rules in that file you need, and then import the file into your component with:

```jsx
import styles from './styles.scss'
```

In your JSX, you reference your classes from that styles object with camelCase. For example:

```css
.my-classname {
  foo: bar;
}
```

```jsx
<div className={styles.myClassname} />
<div className={`${styles.myClassname} not-scoped-classname`} />
```

This type of importing ensures that the CSS is scoped to that component only to prevent conflicts in the global namespace.

We also include the [classnames](https://github.com/JedWatson/classnames) library with the stack. This allows you to apply classes more easily - including conditionally:

```js
import cx from 'classnames'

<div className={cx(styles.firstClass, styles.secondClass)}/>
```

In order to facilitate maintainable CSS, you should utilize the [Block Element Modifier (BEM)](http://getbem.com/naming/) naming convention.

The result is a class name that resembles the following structure:

```
.block__element--modifier
```

```
<form class="form form--blue-theme">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit"
  />
</form>
```

> We use an autoprefixer, so there is no need to add vendor/browser specific prefixes for rules!
