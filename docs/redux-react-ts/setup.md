# Setup

Set Redux up in a React + TS project.

```sh
npm i react-redux @reduxjs/toolkit
```

- Create `src/store/index.tsx`

- Make the `rootReducer`

```tsx title="src/store/index.tsx"
const rootReducer = combineReducers({
  // ...
})
```

- Make the `store`

```tsx title="src/store/index.tsx"
const store = configureStore({
  reducer: rootReducer,
})
```

- Make the `AppStoreProvider`

```tsx title="src/store/index.tsx"
export const AppStoreProvider = (p: PropsWithChildren) => (
  <Provider store={store}>{p.children}</Provider>
)
```

- Get the types & hooks

```tsx title="src/store/index.tsx"
export type AppStore = typeof store
export const useAppStore = useStore.withTypes<AppStore>()

export type AppState = ReturnType<typeof rootReducer>
export const useAppSelector = useSelector.withTypes<AppState>()

export type AppDispatch = typeof store.dispatch
export const useAppDispatch = useDispatch.withTypes<AppDispatch>()
```
