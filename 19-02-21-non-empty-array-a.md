---
title: NonEmptyArray<A>
date: 'Thu, 21 Feb 2019 12:56:31 +0900'
stacks:
    - typescript
---

```ts
type NonEmptyArray<A> = [A, ...A[]];

const f = (xs: NonEmptyArray<number>) => xs[0];
```

```typescript
f([1, 2, 3]);
// => 1

f([]);
// => Property '0' is missing in type '[]' but required in type '[number, ...number[]]'.
```

`Array<A>` のスーパーセットというわけでもないので、大して便利じゃない。

```ts
const a = [1, 2];
f(a);
// => Property '0' is missing in type 'number[]' but required in type '[number, ...number[]]'.
```


