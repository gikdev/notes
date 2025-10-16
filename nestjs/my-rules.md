# NestJS My Rules

- **Version** the endpoint (`@Version('1')`)
- Write a desc (`@ApiOperation()` or `@ApiSummary()`)
- Return instance of a dto...

```ts
// npm i class-transformer

return plainToInstance(
  UserResponseDto,
  users,
  getDefaultClassTransformOptions() // or { excludeExtraneousValues: true }
)
```

- Think of the controller/endpoints authn/authz (`"bearer"` or `"none"` and user's **role**)

- Have `Base*Dto`s, then extend `Create*Dto`, `Update*Dto` and others from the base one...

- Have `*ResponseDto`s! have props and `@Expose()` them! (`npm i class-transformer`)
  - or `*Rdto`s
  - or `*Rto`s
  - just make sure to config the NestJS's auto swagger plugin
