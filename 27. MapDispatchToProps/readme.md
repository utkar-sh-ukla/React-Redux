# mapDispatchToProps

- `mapDispatchToProps` is used for dispatching actions to the store.

```js
function mapDispatchToProps(dispatch, ownProps?)
```

### Arguments 

- `dispatch`
  - For returning new functions that call `dispatch()` inside themselves, and either pass in a plain action object directly or pass in the result of an action creator.

- `ownProps`
  - Instead of re-binding new props to action dispatchers upon component re-rendering, you may do so when your component's props change.

### ItemContainer

```js

import React from 'react'
import { connect } from 'react-redux'
import { buyCake, buyIceCream } from '../redux'

function ItemContainer (props) {
  return (
    <div>
      <h2>Item - {props.item}</h2>
      <div>
        <button onClick={props.buyItem}>Buy Items</button>
      </div>
    </div>
  )
}

...

const mapDispatchToProps = (dispatch, ownProps) => {
  const dispatchFunction = ownProps.cake
    ? () => dispatch(buyCake())
    : () => dispatch(buyIceCream())
  return {
    buyItem: dispatchFunction
  }
}

export default connect(
  null,
  mapDispatchToProps
)(ItemContainer)

```
