# KW UI Kit - Code Guidelines

### Input Standards

If you are creating or modifying a user input, the following standards should be followed:

**Required Props**

The following props are required for all inputs:

| Prop       | Description                                                                      |
| :--------- | :------------------------------------------------------------------------------- |
| `name`     | Unique identifier for the input, typically aligns to a data property             |
| `value`    | The value of the input, typically stored in state                                |
| `onChange` | Callback that should pass back the `name` and `value` of the input in that order |

**Options Array**

Many inputs allow the user to select from a variety of options, the array should take the following form:

```js
const options = [
  { label: 'My Option 1', value: 'my_option_1' },
  { label: 'My Option 2', value: 'my_option_2' }
]
```

The label is displayed to the user whereas the value is what is actually stored in state or saved to the server.
