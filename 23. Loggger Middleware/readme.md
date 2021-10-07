# Logger Middleware

####  Setup: 

> npm install redux-logger

### store

```
import { , applyMiddleware } from 'redux'
import logger from 'redux-logger'


const store = createStore( , applyMiddleware(logger))

```