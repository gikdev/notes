# Slice

Create a slice in your app.

- Define the shape of the state

```tsx title="src/features/counter/store.ts"
interface CounterState {
  count: number
}
```

- Define the initial state

```tsx title="src/features/counter/store.ts"
const initialState: CounterState = {
  count: 0,
}
```

- Create & export the slice

```tsx title="src/features/counter/store.ts"
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

```tsx title="src/store/index.tsx"
const rootReducer = combineReducers({
  counter: counterSlice.reducer,
})
```
