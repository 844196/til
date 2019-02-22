---
title: Frame to MilliSeconds
date: 'Fri, 22 Feb 2019 16:47:40 +0900'
stacks:
    - typescript
---

```ts
const MOVIE_FPS = 60;

const frameToMSec = (frame: number) => {
  const sec = Math.floor(frame / MOVIE_FPS);
  const msec = frame % MOVIE_FPS * (1.0 / MOVIE_FPS);
  return sec + msec;
};
```


