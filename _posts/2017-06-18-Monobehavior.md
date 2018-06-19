---
layout:     post
title:      "初探Noise"
date:       2018-06-18
author:     "Ren"
header-img: "img/post-bg-miui6.jpg"
tags:
    - Unity
    - GameMath
---

<!-- TOC -->

- [**Preface**](#preface)
- [**Value Noise**](#value-noise)
- [**Perlin Noise**](#perlin-noise)

<!-- /TOC -->

## **Preface**
在閱讀場景消融相關文章時,看到其中有個做法是使用3D Noise的方式,來解決直接使用Noise texture,會在不同物體或面的接合處不連續的問題,以往都只是直接上網找texture來使用,決定透過這次機會了解Noise生成的基本原理。

>Dissolving The World  
>https://connect.unity.com/p/articles-dissolving-the-world-part-2

## **Value Noise**
Value Noise算法是基於Lattice的,每個pixel都會在其中一個Lattice中,然後透過對該lattice的所有頂點的顏色進行插直運算,結合緩和曲線,來計算出最後的結果。  
頂點的數量在n維會有$2^N$個頂點。

關於隨機值得部分,會需要當input相等時,隨機出來的也相等,所以可以透過Hash或數學的方式產生(ex: $pi$ or $sin$)。

``` csharp
fixed3 hash33(fixed3 p)
{
    fixed3 mod = fixed3(0.1031, 0.11369, 0.13787);

    p = frac(p * mod);
    p += dot(p, p.yxz + 19.19);

    return -1.0 + 2.0 * frac(fixed3((p.x + p.y) * p.z, (p.x + p.z) * p.y, (p.y + p.z) * p.x));
}
```

![Value Noise](https://renlai1992.github.io/img/in-post/2018-06-19-Noise/noise_value_noise_fade2.jpg)

## **Perlin Noise**

<!--數學算式寫法參考
https://goessner.github.io/markdown-it-texmath/markdown-it-texmath-demo.html
-->


>$c^2+\sqrt{1+2}$&emsp;**(1)**

>$c^2+\sqrt{1+2}$&emsp;**(1)**