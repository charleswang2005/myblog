---
draft: false
series: 未分类
date: 2026-11-27T00:34:10+08:00
lastmod: 2026-11-27T00:58:05+08:00
title: 十七届蓝桥杯大赛软件赛校赛C&C++
---
# 1. 放苹果
【题目描述】
小蓝家的苹果今年丰收了，总共收获了2023个苹果。小蓝要把苹果装箱，每个箱子有3层，每层可以放3行，每行放4个苹果。请问小蓝可以将自己家的苹果装满多少箱？请注意多余的不够一箱的苹果不能算一箱。
## 代码
```C++
#include<bits/stdc++.h>
using namespace std;
int main(){
  cout<<2023/(3*3*4)<<endl;
  return 0;
}
```
## 2. 成员划分
【题目描述】
蓝桥学院正在组织一场程序设计交流活动，总共有n名学生参加，每名学生有一个编号ai。为了促进交流，学院决定将这些学生按顺序划分成若干个连续的小组（即子区间），每个小组内必须满足奇数编号的学生个数等于偶数编号的学生个数，你必须保证每位学生都属于某一个小组。
现在，请你计算出最多能划分出多少个这样的小组。如果无法将所有学生划分成满足条件的小组，则输出-1。
## 代码
```c++
#include <bits/stdc++.h>
using namespace std;
#define int long long
int a[100010];
signed main()
{
	int n;
	cin >> n;
	int odd = 0, even = 0, ans = 0;
	for(int i = 1; i <= n; i++)
	{
		cin >> a[i];
		if(a[i] % 2 == 0) even++;
		else odd++;
		if(odd == even)
		{
			ans++;
			odd = 0;
			even = 0;
		}
	}
	if(odd == 0 && even == 0) cout << ans << endl;
	else cout << -1 << endl;
    return 0;
}
```
