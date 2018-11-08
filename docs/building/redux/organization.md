# Redux - File Organization

The file organization we use is loosely based on the [Ducks proposal](https://github.com/erikras/ducks-modular-redux). All Redux assets are stored in a **modules** directory.

A **Module** consists of:

1.  [Reducer](reducers.md)
1.  [Actions](actions.md)
1.  [Constants](constants.md)
1.  [Selectors](selectors.md)

The purpose of this structure is to de-couple the Redux state from the component structure and [treat it more like a database](https://hackernoon.com/shape-your-redux-store-like-your-database-98faa4754fd5). It makes it easy to access the state from multiple places within the application.

The remainder of the application should be sorted into two different directories:

- **common** - an application-specific styleguide, components that are independent and reusable (e.g. FormGroup)
- **views** - components that are specific to the application and are used to structure (e.g. TopBar, Sidebar)

---

When following the above, the application directory should resemble:

```
.
└── src
    └── myApp
        ├── common
        ├── modules
        │   ├── module1
        │   │   ├── actions.js
        │   │   ├── constants.js
        │   │   ├── reducer.js
        │   │   └── selectors.js
        │   └── module2
        │       ├── actions.js
        │       ├── constants.js
        │       ├── reducer.js
        │       └── selectors.js
        ├── views
        ├── index.js
        └── reducer.js
```

---

### Shared Constants / Actions

There may be a use-case where an action/constants needs to update multiple reducers. To handle this scenario, two additional files should be created in the `modules` directory:

- `commonActions.js`
- `commonConstants.js`

Those actions can then be imported to the components as usual, and the constants can be imported into each reducer that will need access.

> If those files already exist, any additional constants or actions should be added to the existing files

The result will look something like:

```
.
└── src
    └── myApp
        ├── common
        ├── modules
        │   ├── commonActions.js
        │   ├── commonConstants.js
        │   ├── module1
        │   └── module2
        ├── views
        ├── index.js
        └── reducer.js
```
