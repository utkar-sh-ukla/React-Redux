#   Middleware

-   It's the suggested way to extend redux with custom functionality.
-   Provides a third-party extension point between dispatching an action & the moment it reaches the reducer.
-   Use Middleware for logging, crash reporting, performing asynchronous tasks etc.

Let's try to implement a middleware -

First install this dependency.

> npm install redux-logger

```
const reduxLogger = require("redux-logger");
const applyMiddleware = redux.applyMiddleware;
const logger = reduxLogger.createLogger();
...
    //  Actions & Reducers
...
const store = createStore(rootReducer, applyMiddleware(logger));

```

### Complete Code

```

const redux = require("redux");
const reduxLogger = require("redux-logger");

const createStore = redux.createStore;
const combineReducers = redux.combineReducers;
const applyMiddleware = redux.applyMiddleware;

const logger = reduxLogger.createLogger();

const BUY_CAKE = "BUY_CAKE";
const BUY_ICECREAM = "BUY_ICECREAM";

function buyCake() {
  return {
    type: BUY_CAKE,
    info: "First redux action"
  };
}

function buyIcecream() {
  return {
    type: BUY_ICECREAM,
    info: "Second redux action"
  };
}

const initialCakeState = {
  numOfCakes: 10,
};

const initialIcecreamState = {
  numOfIcecream: 20
};


const cakeReducer = (state = initialCakeState, action) => {
  switch (action.type) {
    case BUY_CAKE:
      return {
        numOfCakes: state.numOfCakes - 1
      };
    default:
      return state;
  }
};

const iceCreamReducer = (state = initialIcecreamState, action) => {
  switch (action.type) {
    case BUY_ICECREAM:
      return {
        numOfIcecream: state.numOfIcecream - 1
      };
    default:
      return state;
  }
};

const rootReducer = combineReducers({
  cake: cakeReducer,
  iceCream: iceCreamReducer
});

const store = createStore(rootReducer, applyMiddleware(logger));
console.log("Initial State ", store.getState());
const unsubscribe = store.subscribe(() => {}
);
store.dispatch(buyCake());
store.dispatch(buyCake());
store.dispatch(buyCake());
store.dispatch(buyIcecream());
store.dispatch(buyIcecream());
unsubscribe();

```

### Output

![middleware](https://user-images.githubusercontent.com/61664827/136095467-b0802aac-1f08-4018-8849-15664de95c17.png)
