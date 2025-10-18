# Param ID decorator

```ts title="src/common/decorators/param-id.decorator.ts"
import { Param, ParseIntPipe } from "@nestjs/common"

export const ParamId = () => Param("id", ParseIntPipe)
```
