#   Reducer

-   Specify how the application `state changes` in response to action send to store.
-   Function that accepts `state` & `action` as argument, & return the next state of the application.

> (prevState, action) => newState

```
//Initial state
const initialState = {
  numOfCakes: 10
}

//Reducer function
const reducer = (state = initialState, action) => {
  switch(action.type){
    case 'BUY_CAKE': return {
      ...state, 
      numOfCakes : state.numOfCakes - 1
    }
    default: return state
  }
}

```
