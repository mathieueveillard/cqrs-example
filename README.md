# cqrs-example

```typescript
// WriteModel
type WriteModel = {
  value: number;
};

// WriteModel -> ReadModel synchronization
const synchronize =
  (value: number) =>
  ({ count, sum }: ReadModel): ReadModel => ({
    count: count + 1,
    sum: sum + value,
  });

// ReadModel
type ReadModel = {
  count: number;
  sum: number;
};

const computeAverage = ({ count, sum }: ReadModel): number => sum / count;
```
