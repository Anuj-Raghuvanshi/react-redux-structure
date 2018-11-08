# Redux - Constants / Types

In order to determine whether or not a reducer should act upon a certain action, we define the action `type`. We build these `types` in the form of JavaScript constants. The constants should be a **string equal to the path of the current directory** to scope them to that reducer.

For example, if you had the following structure:

```
.
└── src
    └── myApp
        ├── common
        ├── modules
        │   └── myAwesomeModule
        │       ├── actions.js
        │       ├── constants.js
        │       ├── reducer.js
        │       └── selectors.js
        ├── views
        ├── index.js
        └── reducer.js
```

The `constants.js` file would contain the following path:

```js
export const MY_ACTION_TYPE = 'src/myApp/modules/myAwesomeModule/MY_ACTION_TYPE'
export const ANOTHER_TYPE = 'src/myApp/modules/myAwesomeModule/ANOTHER_TYPE'
```
