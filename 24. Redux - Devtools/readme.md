# Redux-Devtools

- Redux DevTools for debugging application's state changes.

### Setup & Configuration

- Add `Redux DevTools` on your browser.
- Add  its npm-package by running `npm install --save redux-devtools-extension`.

### Use Code 
```js
import { createStore, applyMiddleware } from 'redux';
import { composeWithDevTools } from 'redux-devtools-extension';

const store = createStore(reducer, composeWithDevTools(
  applyMiddleware(...middleware),
  // other store enhancers if any
));
```

### store

```js
...
import { composeWithDevTools } from 'redux-devtools-extension';

const store = createStore(rootReducer, composeWithDevTools(applyMiddleware(logger)))

...
```