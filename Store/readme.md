#   Store

One Store for entire application.

Responsibilities:

-   Holds Application state.
-   Allows access to *state* via `getState()`.
-   Allows state to be *updated* via `dispatch(action)`.
-   Register *listener* via `subscribe(listener)`.
-   Handles unregistering of listeners via the function return by *subscribe(listener)*. 

```

const redux = require('redux')
const createStore = redux.createStore

.....
.....

const store = createStore(reducer)
console.log('Initial State ', store.getState())
const unsubscribe = store.subscribe(() => console.log('Updated State ', store.getState()))
store.dispatch(buyCake())
store.dispatch(buyCake())
store.dispatch(buyCake())
unsubscribe()

```