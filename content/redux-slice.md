+++
title = "Redux Slice"
date = 2025-11-08
+++

Create a slice in your app.

- Define the shape of the state

```ts
interface CounterState {
  count: number
}
```

- Define the initial state

```ts
const initialState: CounterState = {
  count: 0,
}
```

- Create & export the slice

```ts
export const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    inc: state => void state.count++,
    dec: state => void state.count--,
    changeTo(state, action: PayloadAction<number>) {
      state.count = action.payload
    },
  },
})
```

- Import it in the `rootReducer`

```ts
const rootReducer = combineReducers({
  counter: counterSlice.reducer,
})
```
