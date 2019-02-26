---
title: nominal typing
date: 'Sun, 24 Feb 2019 05:57:08 +0900'
stacks:
    - typescript
---

プリミティブ型のエイリアスを定義する

```ts
type AdventDay = number;
type Yen = number;
```

`AdventDay` と `Yen` は名前は違うが構造が同じため、相互に代入可能

```ts
const day: AdventDay = 123;
const yen: Yen = day; // は？
```

インターフェイスで適当なプロパティをでっち上げて、エイリアスを定義したいプリミティブ型と構造を変える

> `_` プレフィックスと `Brand` サフィックスを使用する規約を強くお薦めします(そして、[TypeScriptチームに採用されている規約です][1])。
>
> [Nominal Typing - TypeScript Deep Dive 日本語版][2]

```ts
interface AdventDay extends Number {
  _adventDayBrand: number;
}
interface Yen extends Number {
  _yenBrand: number;
}
```

代入しようとすると構造が異なる（＝型が違う）ため怒られる

```ts
const day: AdventDay = 123 as any;
const yen: Yen = day;
// => Property '_yenBrand' is missing in type 'AdventDay' but required in type 'Yen'.
```

[1]: https://github.com/Microsoft/TypeScript/blob/7b48a182c05ea4dea81bab73ecbbe9e013a79e99/src/compiler/types.ts#L693-L698
[2]: https://typescript-jp.gitbook.io/deep-dive/main-1/nominaltyping#intafsuno



