---
title: check activated apache config
date: 'Fri, 1 Mar 2019 10:41:52 +0900'
stacks:
    - apache
---

```console
$ # ロード中の設定ファイル
$ httpd -t -D DUMP_CONFIG 2>/dev/null | grep '# In' | awk '{print $4}'

$ # ロード中の設定
$ httpd -t -D DUMP_CONFIG 2>/dev/null | grep -v '#'
```


