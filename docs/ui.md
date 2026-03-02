# UI Coding Standards

## Component Library

**Only shadcn/ui components are permitted in this project.**

- Do NOT create custom UI components
- Do NOT use any other component libraries (e.g. Radix primitives directly, MUI, Chakra, etc.)
- All UI must be built by composing shadcn/ui components
- If a shadcn/ui component does not yet exist in the project, add it via the CLI: `npx shadcn@latest add <component>`

## Date Formatting

All date formatting must use **date-fns**.

Dates must be displayed in the following format:

```
1st Sep 2025
2nd Aug 2025
3rd Jan 2026
4th Jun 2024
```

Use the `do MMM yyyy` format string with `format` from `date-fns`:

```ts
import { format } from "date-fns";

format(date, "do MMM yyyy"); // e.g. "1st Sep 2025"
```
