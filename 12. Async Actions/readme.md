#   Async Actions

There are two types of action we use, 

-   Synchronous Actions
    *   As soon as an action was dispatched the state was immediately updated.
    *   If you dispatch the BUY_CAKE action, the numOfCake was right away decremented by 1.
    *   Same with BUY_ICECREAM  action as well.

-   Asynchronous Actions
    *   Asynchronous API calls to fetch data from an end point & use the data in your applications.


##  Our Application

Fetches a list of users from an API end point & stores it in Redux store.

-   State: ?
-   Actions: ?
-   Reducer: ?

####    State

```
state = {
    loading: true,
    data: [],
    error: ''
}
```

-   **loading**: display a loading spinner in your component.
-   **data**: list of user.
-   **error**:  displaying error of users.

####    Actions

```
FETCH_USERS_REQUEST - fetch list of users
FETCH_USERS_SUCCESS - fetched Successfully
FETCH_USERS_FAILURE - error in fetching the data
```

####    Reducers

```
case: FETCH_USERS_REQUEST
        loading: true
case: FETCH_USERS_SUCCESS
        loading: false
        users: data {from API}
case: FETCH_USERS_FAILURE
        loading: false
        error: error {from API}
```

### Complete Code

```
const redux = require("redux");
const createStore = redux.createStore;

const initialState = {
  loading: true,
  users: [],
  error: ''
}

const FETCH_USERS_REQUEST = 'FETCH_USERS_REQUEST'
const FETCH_USERS_SUCCESS = 'FETCH_USERS_SUCCESS'
const FETCH_USERS_FAILURE = 'FETCH_USERS_FAILURE'

const fetchUsersRequest = () => {
  return  {
      type: FETCH_USERS_REQUEST
  }
}

const fetchUsersSuccess = () => {
  return  {
      type: FETCH_USERS_SUCCESS,
      payload: users
  }
}

const fetchUsersFailure = () => {
  return  {
      type: FETCH_USERS_FAILURE,
      payload: error
  }
}

const reducer = (state = initialState, action) => {
  switch(action.type){
    case  FETCH_USERS_REQUEST:
      return{
        ...state,
        loading: true
      }
      case  FETCH_USERS_SUCCESS:
      return{
        loading: true,
        users: action.payload,
        error: ''
      }
      case  FETCH_USERS_FAILURE:
      return{
        loading: true,
        users: [],
        error: action.payload
      }
  }
}

const store = createStore(reducer);
```

