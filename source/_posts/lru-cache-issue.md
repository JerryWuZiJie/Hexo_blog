---
title: lru_cache issue
tags:
  - Python
  - issue
categories:
  - - programming
    - Python
  - issue
description: Cache not deleted when object is deleted
date: 2022-08-15 21:56:38
---

when using the ```lru_cache``` from the ```functools``` module, many like to set ```maxsize=None```. However, when decorating a method with ```lru_cache```, the caches wouldn't get destroyed when the object is deleted by the garbage collector. This would create the problem that the cache would keep growing and growing.

The reason behind this is the decorator makes the method a callable class attribute. Therefore it will only get deleted when the class is deleted, not the object. To avoid this, one can create a private method, and create a callable instance attribute when initializing by the following code:

```python
self.method_name = functools.lru_cache(maxsize=None)(self._method_name)
```

## Reference

- <https://www.youtube.com/watch?v=sVjtp6tGo0g&ab_channel=anthonywritescode>
