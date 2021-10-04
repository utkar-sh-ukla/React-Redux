#   Actions

-   Only way your app can interact with the store.
-   Carry some information from your `app` -> `redux store`.
-   Plain Javascript Object.
-   Have a `type` property that indicate the type of actions being performed. This type property typically defined as `string constants`.

```
//Initialized Action
const BUY_CAKE = 'BUY_CAKE';

//Action Creator 
function buyCake() {
  return {
    type: BUY_CAKE,
    info: 'First Redux Action',
  };
}

```