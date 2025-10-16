# Redux React TypeScript Usage

- Get piece of state using a selector

```tsx
import { useAppDispatch, useAppSelector } from "../../store"
// ...
const count = useAppSelector(s => s.counter.count)
```

- Dispatch stuff

```tsx
function SomeBtn() {
  const dispatch = useAppDispatch()

  const changeTo5 = () => {
    const action = counterSlice.actions.changeTo(5)
    dispatch(action)
  }

  return <button onClick={changeTo5} />
}
```
