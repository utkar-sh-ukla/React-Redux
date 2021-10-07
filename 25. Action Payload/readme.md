# Action Payloads

- We normally put any extra data needed to describe what's happening into the action.payload field. This could be a number, a string, or an object with multiple fields inside.

### Folder Structure

```
src
|__components
  +|__NewCakeContainer.js

```

### NewCakeContainer

```js

import React, { useState } from 'react'
import { connect } from 'react-redux'
import { buyCake } from '../redux'

function NewCakeContainer (props) {
  const [number, setNumber] = useState(1)
  return (
    <div>
      <h2>Number of cakes - {props.numOfCakes} </h2>
      <input type='text' value={number} onChange={e => setNumber(e.target.value)} />
      <button onClick={() => props.buyCake(number)}>Buy {number} Cakes</button>
    </div>
  )
}

const mapStateToProps = state => {
  return {
    numOfCakes: state.cake.numOfCakes
  }
}

const mapDispatchToProps = dispatch => {
  return {
    buyCake: number => dispatch(buyCake(number))
  }
}

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(NewCakeContainer)
```

### CakeAction

```js
import { BUY_CAKE } from './cakeTypes'

export const buyCake = (number = 1) => {
  return {
    type: BUY_CAKE,
    payload: number
  }
}
```