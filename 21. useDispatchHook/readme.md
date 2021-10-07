#  useDispatch()

- This hook returns a reference to the dispatch function from the Redux store. You may use it to `dispatch` actions as needed.

```
const dispatch = useDispatch()
```

### HooksCakeContainer

```
import {   , useDispatch} from 'react-redux'
import { buyCake } from '../redux'


function HooksCakeContainer() {
  ...
  const dispatch = useDispatch()
  return (
    <div>
      ...
      <button onClick = {() => dispatch(buyCake())}>Buy Cake</button>
    </div>
  )
}

...
```

