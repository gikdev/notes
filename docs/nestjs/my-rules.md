---
sidebar_position: 3
---

# My Rules

Some rules I try to follow...

- **Version** the endpoint (`@Version('1')`)
- Write a desc (`@ApiOperation()` or `@ApiSummary()`)

- Think of the controller/endpoints authn/authz (`"bearer"` or `"none"` and user's **role**)

- For DTOs:
  - Have `BaseBookReqDto` (`base-book-req.dto.ts`)
  - Have `CreateBookReqDto` and extend from the base one
  - Have `BooksResDto` (`books-res.dto.ts`)
    - Also `@Expose()` the props!
    - Use `plainToInstance(Dto, raw, options)` to return it!

    ```ts
    // npm i class-transformer

    return plainToInstance(
      UserResponseDto,
      users,
      getDefaultClassTransformOptions() // or { excludeExtraneousValues: true }
    )
    ```
