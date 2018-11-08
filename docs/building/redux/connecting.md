# Redux - Connecting Components

In order to gain access to the Redux actions and store within a component, you will need to connect the component to the Redux store. From there we can specify what actions and state we want that component to be able to access.

```js
import React from 'react'
import { func, string } from 'prop-types'

// `connect` is the Higher Order Component we will use when exporting the component
import { connect } from 'react-redux'

// `createStructuredSelector` will allow us to map our component props to redux state
import { createStructuredSelector } from 'reselect'

// Import any selectors you want from their respective module
import { getContactName } from 'path/to/modules/module/selectors'

// Import any actions you want from their respective module
import { updateContactName } from 'path/to/modules/module/actions'

class MyContactComponent extends React.Component {
  handleNameChange = event => {
    this.props.updateContactName(event.target.value)
  }
  render() {
    const { name } = this.props
    return (
      <div>
        <label>Name: {name}</label>
        <input onChange={this.handleNameChange} value={name} />
      </div>
    )
  }
}

MyContactComponent.propTypes = {
  name: string.isRequired, // Provided from mapStateToProps below
  updateContactName: func.isRequired // Provided from the second argument of connect below
}

// Using the selectors we imported, we can map a prop to the data from the redux store
const mapStateToProps = createStructuredSelector({
  name: getContactName()
})

// We then export the component by connecting it to redux and passing the state mapping
// and redux actions as arguments
export default connect(
  mapStateToProps,
  { updateContactName }
)(MyContactComponent)
```
