# IceCream __redux

Redux Implementation of IceCream Container.

### Folder Structure

```
src
|__components
|  +|__IceCreamContainer.js
|
|__redux
   +|__iceCream
    |   +|__iceCreamActions.js
    |   +|__iceCreamReducer.js
    |   +|__iceCreamTypes.js
    |
   +|___rootReducer.js
```

### iceCreamActions

```
import { BUY_ICECREAM } from './iceCreamTypes'

export const buyIceCream = () => {
  return {
    type: BUY_ICECREAM
  }
}
```

### iceCreamReducer
```
import { BUY_ICECREAM } from './iceCreamTypes'

const initialState = {
  numOfIceCream: 20
}

const iceCreamReducer = (state = initialState, action) => {
  switch (action.type) {
    case BUY_ICECREAM: return {
      ...state,
      numOfIceCream: state.numOfIceCream - 1
    }

    default: return state
  }
}

export default iceCreamReducer
```

### iceCreamTypes

```
export const BUY_ICECREAM = 'BUY_ICECREAM'
```

### rootReducer

```
import {combineReducers} from 'redux'
import cakeReducer from './cake/cakeReducer'
import iceCreamReducer from './iceCream/iceCreamReducer'

const rootReducer = combineReducers({
  cake: cakeReducer,
  iceCream: iceCreamReducer,
})

export default rootReducer
```

### IceCreamContainer

```
import React from 'react'
import { connect } from 'react-redux'
import { buyIceCream } from '../redux'

function IceCreamContainer (props) {
  return (
    <div>
      <h2>Number of iceCream - {props.numOfIceCream} </h2>
      <button onClick={props.buyIceCream}>Buy Cake</button>
    </div>
  )
}

const mapStateToProps = state => {
  console.log(state)
  return {
    numOfIceCream: state.iceCream.numOfIceCream
  }
}

const mapDispatchToProps = dispatch => {
  return {
    buyIceCream: () => dispatch(buyIceCream())
  }
}

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(IceCreamContainer)
```