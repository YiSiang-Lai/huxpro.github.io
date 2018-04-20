---
layout:     post
title:      " Unity MonoBehaviour Life Time"
date:       2018-04-20
author:     "Ren"
header-img: "img/post-bg-miui6.jpg"
tags:
    - Unity
---

### 資料結構

## List Stack Queue
* 內部Catch了一個T[0]陣列,供construct時沒指定Capcity時重複使用
* 一旦List size >= 1之後容量至少為4
* array中的資料設null才能GC

## Linked List
* 

1.FixedUpdate和Update

``` python
@requires_authorization
def somefunc(param1='', param2=0):
    '''A docstring'''
    if param1 > param2: # interesting
        print 'Greater'
    return (param2 - param1 + 1) or None
class SomeClass:
    pass
>>> message = '''interpreter
... prompt''
```