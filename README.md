# hexon-react-z

React adapter for **hexon** (DDD-lite core).

#### Features
- React hook for running use cases
- Loading / error / data state
- No domain logic
- No framework lock-in

#### Install
```bash
npm install hexon-react-z hexon
```

#### Usage

```ts
const activate = useUseCase(
  () => new ActivateAccount(repo)
)

await activate.run({ userId: "1" })
```

#### React is an adapter — hexon stays framework-agnostic.
```ts
const activateAccount = useUseCase(() =>
  new ActivateAccount(
    container.resolve(USER_REPO)
  )
)

<button
  onClick={() => activateAccount.run({ userId })}
  disabled={activateAccount.loading}
>
  Activate
</button>
```

#### License
MIT