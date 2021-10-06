#  Connect 



### Folder Structure

```
src
|__redux
    |__cake
    |    |__cakeActions.js
    |    |__cakeReducer.js
    |    |__cakeTypes.js
    |__store.js
   +|__index.js

```

### cakeContainer

```
import React from 'react'
import { connect } from 'react-redux'
import { buyCake } from '../redux'

function CakeContainer (props) {
  return (
    <div>
      <h2>Number of cakes - {props.numOfCakes} </h2>
      <button onClick={props.buyCake}>Buy Cake</button>
    </div>
  )
}

const mapStateToProps = state => {
  console.log(state)
  return {
    numOfCakes: state.numOfCakes
  }
}

const mapDispatchToProps = dispatch => {
  return {
    buyCake: () => dispatch(buyCake())
  }
}

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(CakeContainer)

```

### index 

```
export { buyCake } from './cake/cakeActions'

```