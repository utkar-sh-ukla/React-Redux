#  useSelector()

- Allows you to extract data from the Redux store state, using a selector function.

```
const result: any = useSelector(selector: Function, equalityFn?: Function)
```

- The selector is approximately equivalent to the `mapStateToProps` argument to `connect` conceptually.
- The selector will be called with the entire Redux store state as its only argument.
- The selector will be run whenever the function component renders (unless its reference hasn't changed since a previous render of the component so that a cached result can be returned by the hook without re-running the selector).
-  `useSelector()` will also subscribe to the Redux store, and run your selector whenever an action is dispatched.

### Folder Structure

```
src
|__container
      |__CakeContainer.js
     +|__HooksCakeContainer.js

```

### HooksCakeContainer

```
import React from 'react'
import {useSelector} from 'react-redux'

function HooksCakeContainer() {
  const numOfCakes = useSelector(state => state.numOfCakes)
  return (
    <div>
      <h2>Number of Cakes - {numOfCakes}</h2>
      <button>Buy Cake</button>
    </div>
  )
}

export default HooksCakeContainer;
```

