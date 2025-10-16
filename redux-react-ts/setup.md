# Redux React TypeScript Setup

- Install dependencies

```sh
npm i react-redux @reduxjs/toolkit
```

- Create `src/store/index.tsx`

- Make the `rootReducer`

```tsx
const rootReducer = combineReducers({
  // ...
})
```

- Make the `store`

```tsx
const store = configureStore({
  reducer: rootReducer,
})
```

- Make the `AppStoreProvider`

```tsx
export const AppStoreProvider = (p: PropsWithChildren) => (
  <Provider store={store}>{p.children}</Provider>
)
```

- Get the types & hooks

```tsx
export type AppStore = typeof store
export const useAppStore = useStore.withTypes<AppStore>()

export type AppState = ReturnType<typeof rootReducer>
export const useAppSelector = useSelector.withTypes<AppState>()

export type AppDispatch = typeof store.dispatch
export const useAppDispatch = useDispatch.withTypes<AppDispatch>()
```
