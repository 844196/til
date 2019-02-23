---
title: Array.prototype.filter with user defined typeguard
date: 'Sun, 24 Feb 2019 06:41:21 +0900'
stacks:
    - typescript
---

```ts
type One = 1;
type Two = 2;
type OneOrTwo = One | Two;

let nums: OneOrTwo[];

nums.filter((n) => n === 1);
// => OneOrTwo[]

nums.filter((n): n is One => n === 1);
// => One[]

const isOne = (x: OneOrTwo): x is One => x === 1;
nums.filter(isOne);
// => One[]
```


