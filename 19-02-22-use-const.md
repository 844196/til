---
title: use const
date: 'Fri, 22 Feb 2019 17:45:04 +0900'
stacks:
    - php
---

```php
<?php declare(strict_types = 1);

namespace App {
    const DB_USERNAME = '844196';
}

namespace App\Xxx {
    use const App\DB_USERNAME;

    echo DB_USERNAME . \PHP_EOL;
    // => 844196
}
```


