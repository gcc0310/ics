# hw1参考答案

## 2.88

这个题目有一定歧义，不同理解下得到的答案都算对。

| 格式A       |                      | 格式B                      |                                     |
| ----------- | -------------------- | -------------------------- | ----------------------------------- |
| 值          | 位                   | 值                         | 位                                  |
| 1 01110 001 | $\cfrac{-9}{16}$     | 1 0110 0010                | $\cfrac{-9}{16}$                    |
| 0 10110 101 | $13\times 2^4 = 208$ | 0 1110 1010                | $13\times 2^4 = 208$                |
| 1 00111 110 | $-7\times 2^{-10}$   | 1 0000 0111                | $-7\times 2^{-10}$                  |
| 0 00000 101 | $5\times 2^{-17}$    | 0 0000 0001 or 0 0000 0000 | $1\times 2^{-10}$ or $0$            |
| 1 11011 000 | $-2^{12} = -4096$    | 1 1110 1111 or 1 1111 0000 | $-31\times 2^3 = -248$ or $-\infty$ |
| 0 11000 100 | $3\times2^8 = 768$   | 0 1111 0000                | $+\infty$                           |

## 2.91

### A

$11.0010010000111111011011_2$

### B

$11.(001)_2$

### C

第9位

## 2.93

只要功能正确即可

```c
float_bits float_absval(float_bits f) {
    unsigned exp = (f >> 23) & 0xFF;
    unsigned frac = f & 0x7FFFFF;
    if(exp == 0xFF &&  frac != 0) {
        return f; // NaN
    }
    return f & (0x7FFFFFFF);
}
```
