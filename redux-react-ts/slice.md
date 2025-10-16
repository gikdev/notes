# Redux React TypeScript Slice

- Define the shape of the state

```tsx
interface CounterState {
  count: number
}
```

- Define the initial state

```tsx
const initialState: CounterState = {
  count: 0,
}
```

- Create & export the slice

```tsx
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
