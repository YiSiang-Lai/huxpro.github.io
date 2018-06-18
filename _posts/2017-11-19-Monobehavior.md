---
layout:     post
title:      "初探Noise"
date:       2018-06-19
author:     "Ren"
header-img: "img/post-bg-miui6.jpg"
tags:
    - Unity
    - GameMath
---

## <b>Value Noise</b>

## <b>Perlin Nois</b>  
<!--數學算式寫法參考
https://goessner.github.io/markdown-it-texmath/markdown-it-texmath-demo.html
-->

``` csharp
fixed3 hash33(fixed3 p)
{
    fixed3 mod = fixed3(0.1031, 0.11369, 0.13787);

    p = frac(p * mod);
    p += dot(p, p.yxz + 19.19);

    return -1.0 + 2.0 * frac(fixed3((p.x + p.y) * p.z, (p.x + p.z) * p.y, (p.y + p.z) * p.x));
}
```
 $$c^2+\sqrt{1+2}$$ (1)
  
 $E = m\cdot{c^2}$
 
 $ E = m\cdot{c^2}$
