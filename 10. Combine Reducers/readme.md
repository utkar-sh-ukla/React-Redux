
# Multiple Reducers

```

const redux = require("redux");
const createStore = redux.createStore;
const combineReducers = redux.combineReducers;

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

const store = createStore(rootReducer);
console.log("Initial State ", store.getState());
const unsubscribe = store.subscribe(() =>
  console.log("Updated State ", store.getState())
);
store.dispatch(buyCake());
store.dispatch(buyCake());
store.dispatch(buyCake());
store.dispatch(buyIcecream());
store.dispatch(buyIcecream());
unsubscribe();


```

### Output

![combine Reducers](https://user-images.githubusercontent.com/61664827/136090885-5efce288-9aeb-4df6-a287-57ba766bb83f.png)

