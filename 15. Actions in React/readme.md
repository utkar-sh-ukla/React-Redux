#  React-Redux Actions

### Folder Structure

```
src
+|__redux
    +|__cake
        +|__cakeActions.js
        +|__cakeTypes.js

```

### cakeTypes

```
export const BUY_CAKE = 'BUY_CAKE'
```

### cakeActions

```
import {BUY_CAKE} from './cakeTypes'
export const buyCake = () => {
  return(
    type: BUY_CAKE
  )
}
```