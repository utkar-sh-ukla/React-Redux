#  React-Redux Store

### Folder Structure

```
src
|__redux
    |__cake
    |    |__cakeActions.js
    |    |__cakeReducer.js
    |    |__cakeTypes.js
   +|__store.js

```

### store

```
import {createStore} from 'redux'
import cakeReducer from './cake/cakeReducer'

const store = createStore(cakeReducer)
export default store
```


> To provide access of `redux-store` to `react` we use `Provider` component.


### In App

```
import {Provider} from 'react-redux'
import store from './redux/store'
...

function App () {
  return (
    <Provider store={store}>
      <div className='App'>

        // components

      </div>
    </Provider>
  )
}

export default App
