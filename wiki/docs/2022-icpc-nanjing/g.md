---
title: G - 邪恶铭刻
date: 2022-12-16
---

# G - 邪恶铭刻

## 基本信息

<table>
<tr>
<td><b>题目出处</b></td><td>2022 ICPC 亚洲区域赛南京站</td>
</tr>
<tr>
<td><b>队伍通过率</b></td><td>406/465 (87.3%)</td>
</tr>
</table>

## 题解

### 题意概括

首先简单总结一下本题的题意：您需要维护一个序列，序列里一开始只有一个 $1$。您要处理 $n$ 个事件，事件可能有以下三种：

* 往序列里添加一个 $1$。
* 从序列里拿出两个数，加起来再放回去。
* 从以上两种事件中自由选一个。

在每次都能从序列里拿出两个数的前提下，求序列平均值的最大值。

### 贪心策略

序列的平均值仅由序列中的元素和以及序列的元素数量决定。

进行第一种事件后，答案的分子和分母都加 $1$（由于答案总是大于等于 $1$，这种操作会让答案不变或变小）；进行第二种事件后，答案的分母减 $1$（也就是答案变大了）。

显然我们要在合法的前提下，尽可能进行第二种事件。除非接下来马上就要变成非法状态，才考虑将之前一次自由选择从事件二反悔成事件一。

模拟这个贪心策略即可，复杂度 $\mathcal{O}(n)$。具体实现详见参考代码。

## 参考代码

```c++ linenums="1"
#include <bits/stdc++.h>
using namespace std;

int n;

void solve() {
    scanf("%d", &n);
    // s：序列元素之和
    // c：序列元素数量
    // t：之前所有自由选择事件中，选了几次事件二
    int s = 1, c = 1, t = 0;
    bool failed = false;
    // 按顺序处理所有事件
    for (int i = 1; i <= n; i++) {
        int x; scanf("%d", &x);
        // 事件一
        if (x == 1) s++, c++;
        // 事件二
        else if (x == -1) {
            // 尝试直接执行
            if (c > 1) c--;
            // 无法直接执行，尝试反悔一次自由选择
            else if (t >= 1) t--, s++, c++;
            // 无法反悔，无解
            else failed = true;
        } else {
            // 自由选择事件，尽可能选择事件二
            if (c > 1) t++, c--;
            else s++, c++;
        }
    }
    if (failed) printf("-1\n");
    else {
        int g = gcd(s, c);
        printf("%d %d\n", s / g, c / g);
    }
}

int main() {
    int tcase; scanf("%d", &tcase);
    while (tcase--) solve();
    return 0;
}
```
