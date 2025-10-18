# API Summary decorator

```ts title="src/common/decorators/api-summary.decorator.ts"
import { ApiOperation } from "@nestjs/swagger"

export const ApiSummary = (summary: string) => ApiOperation({ summary })
```