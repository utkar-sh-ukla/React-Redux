#  React-Redux Reducer

### Folder Structure

```
src
|__redux
    |__cake
        |__cakeActions.js
       +|__cakeReducer.js
        |__cakeTypes.js

```

### cakeReducer

```
import {BUY_CAKE} from './cakeTypes'

const initialState = {
  numOfCakes: 10
}

const cakeReducer = (state = initialState, action) => {
  switch(action.type){
    case BUY_CAKE: {
      return {
        ...state,
        numOfCakes: state.numOfCakes - 1
      }
    }
    default: return state
  }
}

export default cakeReducer;
```