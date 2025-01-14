---
title: C - 0689
date: 2023-07-16
---

# C - 0689

## 基本信息

<table>
<tr>
<td><b>题目出处</b></td><td>2019 陕西省大学生程序设计竞赛</td>
</tr>
<tr>
<td><b>队伍通过率</b></td><td>15/111 (13.5%)</td>
</tr>
</table>

## 题解

先假设字符串里只有 $0$ 和 $8$。

如果我们要翻转区间 $[l, r]$，而 $s_l = s_r$，那么翻转 $[l, r]$ 的结果和翻转 $[l + 1, r - 1]$ 的结果是一样的。因此我们只考虑满足 $s_l \ne s_r$ 的区间 $[l, r]$。

考虑两个区间 $[l_1, r_1]$ 和 $[l_2, r_2]$ 满足 $r_1 < r_2$，翻转这两个区间的结果一定是不同的。这是因为如果翻转 $[l_1, r_1]$，则 $s_{r_2}$ 将保持不变；而翻转 $[l_2, r_2]$ 会让 $s_{r_2}$ 发生变化。同理，如果 $l_1 < l_2$，翻转两个区间的结果也一定不同。

因此答案就是满足 $s_l \ne s_r$ 的区间 $[l, r]$ 的数量。

把 $6$ 和 $9$ 加回来，解法仍然是一样的。答案就是左右端点不是 $00$、$88$、$69$、$96$ 的区间数量。

这里有一个细节问题：满足上述条件的区间，翻转的结果一定和原字符串不同。但如果存在一个区间，翻转的结果和原字符串相同，最终答案还要再加上 $1$。这里我们进行分类讨论。

* 如果原字符串存在 $0$ 和 $8$，那么只要翻转这个长度为 $1$ 的区间，仍然还是原字符串。
* 否则，如果原字符串里都是 $6$，那么翻转任何一个区间都会把 $6$ 变成 $9$，不可能得到原字符串。原字符串都是 $9$ 的情况同理。
* 剩下的情况就是原字符串由 $6$ 和 $9$ 组成。这样的字符串一定存在子串 $69$ 或者 $96$，翻转这个长度为 $2$ 的区间，仍然还是原字符串。

复杂度 $\mathcal{O}(n)$。

## 参考代码

```c++ linenums="1"
#include <bits/stdc++.h>
#define MAXN ((int) 1e6)
using namespace std;

char s[MAXN + 10];
long long ans;

void solve() {
    scanf("%s", s + 1);

    ans = 0;
    int cnt[10] = {0};
    for (int i = 1; s[i]; i++) {
        int x = s[i] - '0';
        cnt[x]++;
        // R0L0
        if (x == 0) ans += i - cnt[0];
        // R6L9
        else if (x == 6) ans += i - cnt[9];
        // R8L8
        else if (x == 8) ans += i - cnt[8];
        // R9L6
        else ans += i - cnt[6];
    }

    // 检查是否存在一个区间，翻转之后仍然是原字符串
    int flag = 0;
    for (int i = 1; s[i]; i++) {
        if (s[i] == '6') flag |= 1;
        else if (s[i] == '9') flag |= 2;
        else flag = 3;
    }
    printf("%lld\n", ans + (flag == 3 ? 1 : 0));
}

int main() {
    int tcase; scanf("%d", &tcase);
    while (tcase--) solve();
    return 0;
}
```
