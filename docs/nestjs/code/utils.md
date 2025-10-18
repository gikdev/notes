# Utils.ts

```ts title="src/common/utils.ts
import { ClassTransformOptions } from "class-transformer"

export function getDefaultClassTransformOptions(
  options?: ClassTransformOptions,
) {
  return { excludeExtraneousValues: true, ...options }
}
```
