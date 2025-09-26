# Vue + TypeScript + Element Plus Project Setup

Specific patterns and configurations for Vue 3 + TypeScript + Element Plus projects.

## 🔧 CLAUDE.md Additions

### Mandatory Validation Steps
```bash
# Always run both commands after changes
pnpm lint && pnpm type-check
```

### Vue/TypeScript Best Practices

#### Pinia Store Conventions
```typescript
// ✅ CORRECT: Use verifyResponseBody for API responses
const { data, error } = useFetchScheduler(url, {
  async afterFetch(ctx) {
    const parsed = await verifyResponseBody(
      ctx.data,
      z.array(SomeSchema),
      'Schema validation error message'
    );
    ctx.data = parsed;
    return ctx;
  }
});

// ✅ CORRECT: Use shallowRef for simple values
const status = shallowRef<StatusType>('');
const sortOrder = shallowRef<SortOrder>(SortOrder.enum.ASC);

// ✅ CORRECT: Use enum values, not strings
SortOrder.enum.ASC // not 'ASC'
InvocationStatus.enum.PENDING // not 'PENDING'
```

#### Vue Computed Properties - CRITICAL MUTATION RULES
```typescript
// ✅ CORRECT: Prevent Array.sort() mutation with spread
data: computed(() => {
  const items = data.value ?? [];
  return [...items].sort((a, b) => ...); // Spread prevents mutation
}),

// ❌ WRONG: Direct sort mutates original array
data: computed(() => {
  const items = data.value ?? [];
  return items.sort((a, b) => ...); // Corrupts original data!
}),
```

#### Element Plus Integration Patterns
```typescript
// ✅ CORRECT: Empty string for "All" option (Element Plus pattern)
const statusOptions = [
  { label: 'All', value: '' }, // Empty string works with Element Plus
  { label: 'Pending', value: SomeEnum.enum.PENDING }
];

// ✅ CORRECT: Override Element Plus width with !important
class="w-42!" // ! flag overrides Element Plus defaults

// ✅ CORRECT: Use storeToRefs for reactive binding
const { status, sortOrder } = storeToRefs(store);
```

### Performance & Reactivity Patterns

#### URL-Based Reactivity
```typescript
// ✅ CORRECT: Use computed URL with refetch: true
const url = computed(() => {
  const params = new URLSearchParams({
    page: page.value.toString(),
    pageSize: pageSize.value.toString()
  });

  if (status.value) {
    params.set('status', status.value);
  }

  return `api/endpoint?${params.toString()}`;
});

// URL changes automatically trigger refetch with refetch: true
```

#### Polling Patterns
```typescript
// ✅ CORRECT: Reactive polling interval
const pollingIntervalSeconds = shallowRef(10);

useIntervalFn(
  () => execute(),
  () => pollingIntervalSeconds.value * 1000,
  { immediate: true }
);
```

### Error Handling & Logging

```typescript
// ✅ CORRECT: Use consola for logging
import { consola } from 'consola';
consola.info('Debug message');

// ✅ CORRECT: Use ElMessage for user notifications
import { ElMessage } from 'element-plus';
ElMessage.warning('User-friendly warning');

// ✅ CORRECT: Proper error transformation for UI
error: computed(() => {
  if (!error.value) return null;
  return typeof error.value === 'string' ? error.value : 'An error occurred';
})
```

## 📂 File Organization

### Standard Structure
- **Stores**: `src/pages/[feature]/[feature]-store.ts`
- **Components**: `src/pages/[feature]/index.vue`
- **Types**: `src/pages/[feature]/index.ts`

### Import Order
1. Vue imports
2. Third-party libraries (Element Plus, VueUse, etc.)
3. Internal utilities/services
4. Local component imports
5. Type imports

### Naming Conventions
- **Stores**: `useFeatureStore`
- **Components**: PascalCase for components, kebab-case for files
- **Types**: PascalCase
- **Enums**: PascalCase with `.enum` property access

## 🚨 Critical Anti-Patterns

❌ **Array mutations in computed properties**
❌ **Creating new types when existing ones exist**
❌ **Using string literals instead of enum values**
❌ **Skipping lint/type-check validation**
❌ **Missing verifyResponseBody for API responses**
❌ **Using `any` type (strictly forbidden)**
❌ **Inline styles instead of Tailwind classes**

## Development Commands

```bash
# Development
pnpm dev

# Quality checks (run after every change)
pnpm lint && pnpm type-check

# Testing
pnpm test:unit

# Build
pnpm build
```

## Quality Gates

Before completing any feature:
- [ ] All lint warnings resolved
- [ ] All TypeScript errors resolved
- [ ] Existing patterns followed
- [ ] Enums used instead of string literals
- [ ] Array mutations prevented in computed properties
- [ ] API responses validated with verifyResponseBody
- [ ] Error handling implemented properly