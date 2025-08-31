## Unit Test Setup
[← Return to Home](readMe.md)

---
Add Unit Test Setup

```bash
npm install --save-dev vitest @vitejs/plugin-react jsdom @testing-library/react @testing-library/dom
npm install --save-dev @testing-library/user-event
npm install --save-dev vite-tsconfig-paths
npm install --save-dev @vitest/coverage-v8
```

Create `vitetest.config.mts`
```javascript
import { defineConfig } from 'vitest/config'
import react from '@vitejs/plugin-react'

export default defineConfig({
    plugins: [react()],
    test: {
        environment: 'jsdom',
        coverage: {
            reporter: ['text', 'json', 'html'],
        },
    },
})
```

Add a test option to the list of scripts in `package.json`:
```json
{  "scripts": {
    "test": "vitest --coverage",
  },}
```

Create the most basic test file `things.test.ts`:
The file name needs to contain `.test.`
```typescript
import { describe, test } from "vitest";

describe("things", () => {
    test("works", () => {
        console.log("it works");
    });
});
```

Run the test script:
```bash
npm test
```