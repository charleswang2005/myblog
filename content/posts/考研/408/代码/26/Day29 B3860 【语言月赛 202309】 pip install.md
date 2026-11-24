---
draft: false
series: 未分类
date: 2026-11-24T10:34:17+08:00
lastmod: 2026-11-24T10:36:12+08:00
tags:
title: Day29 B3860 【语言月赛 202309】 pip install
---
## 题目描述

`pip install` 是 Python 安装包的重要指令。Python 的包具有依赖关系，在安装某些包之前，需要先安装这些包的依赖。

假定一共有依次编号为 $1 \sim N$ 的 $N$ 个包，第 $i$ 个包共有 $K_i$ 个依赖。现在，小 F 想要安装编号为 $1$ 的包。在完成 $1$ 号包及其全部依赖的安装，一共安装了多少个包？

## 输入格式

输入共 $N+1$ 行。

输入的第一行为一个正整数 $N$。

接下来 $N$ 行，第 $i$ 行描述了编号为 $i$ 的包的依赖：

- 第 $i$ 行共有 $K_i+1$ 个数。
- 第一个数为 $K_i$。
- 接下来 $K_i$ 个数，描述了所依赖的包的编号。

## 输出格式

输出一行一个整数，表示安装的包的数量。

## 输入输出样例

### 输入

```
5
1 2
1 3
1 4
0
0
```

### 输出

```
4
```

## 说明/提示

对于 $100\%$ 的测试数据，$1 \le N \le 5000$，$0 \le K_i < N$，保证不会构成循环依赖。
## 代码
```C++
#include <bits/stdc++.h>
using namespace std;
#define int long long
bool g[5010][5010];
int n;
int cnt=0;
bool st[5010];
void dfs(int x)
{
    if(st[x]==true)
    {
        return;
    }
    if(!st[x])
    {
       st[x]=true;
       cnt++;
    }
    for(int i=1;i<=n;i++)
    {
        if(g[x][i]) dfs(i);
    }
}
signed main()
{
    cin>>n;
    for(int i=1;i<=n;i++)
    {
        int k;
        cin>>k;
        while(k--)
        {
            int x;
            cin>>x;
            g[i][x]=true;
        }
    }
    dfs(1);
    cout<<cnt<<endl;

    return 0;
}
//这一题都是安装依赖包1 所以就很简单 
```