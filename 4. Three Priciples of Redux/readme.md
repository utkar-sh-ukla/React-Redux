#   Three Principle For Redux

### First Principle

`The state of your whole application is stored in an object tree within a single store`

-   Maintain over application state in a single object which would be managed by the redux store.

e.g. Remember our previous Cake Shop Example.Let's assume we are tracking the number of cakes on the shelf.

```
{
     numOfCakes: 10
}

```

### Second Principle

`The only way to change the state is to dispatch an action; an object describing what happened`

-   To update the state of your application, you need to let redux know about that with an action.
-   Not allowed to directly update the state object.

e.g. Let the shopkeeper know about our action `BUY_CAKE`

```
{
    type: BUY_CAKE
}

```
### Third Principle

`To Specify how the state tree is transformed by action; you write pure Reducers`

-   Reducers - (previousState, action) => newState

e.g. Reducer for the Cake Shop

```
const reducer = (state, action) => {
  switch(action.type){
    case 'BUY_CAKE': return {
      ...state, 
      numOfCakes = state.numOfCakes - 1
    }
  }
}

```

### OverView

![redux](https://user-images.githubusercontent.com/61664827/135830365-ea1e4347-eede-40f1-a75a-1c5e6507e3e9.png)


