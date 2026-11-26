## 题目描述

小可可选修了基础生物基因学。教授告诉大家 Super Samuel 星球上 Kitty 猫的基因的长度都是 $2$ 的正整数次幂，全是由两种不同的基因单元组成的。这两种不同的基因单元分别记成 $0$ 和 $1$，于是 Kitty 猫基因可以写成一个 01 串表达式。

为了便于分析和降低数据存储量，教授发明了 ABC 编码规则。该编码规则是不断地按照

$$
T(s) = \begin{cases}
  \texttt A & \text{若 }s\text{ 串全是 }0  \\
  \texttt B & \text{若 }s\text{ 串全是 }1  \\
  \texttt C T(s_1) T(s_2) & \text{否则把 }s\text{ 串分成两个等长的子串 }s_1\text{ 和 }s_2
\end{cases}
$$

对 Kitty 猫基因 01 串表达式 $s$ 进行改写，直至最终被改写成只含有字符 $\texttt A$、$\texttt B$、$\texttt C$ 的符号串。

例如：

$$
\begin{align*}
&T(01001011) \\
&= \texttt C T(0100)T(1011) \\
&= \texttt{CC}T(01)T(00)\texttt C T(10)T(11) \\
&= \texttt{CCC}T(0)T(1)\texttt{ACC}T(1)T(0)\texttt B \\
&= \texttt{CCCABACCBAB}
\end{align*}
$$

请你编写程序帮助小可可求出 Kitty 猫基因的 ABC 编码以协助教授开展科研工作。

## 输入格式

文件中以一行的形式存放了一个 Kitty 猫基因的 01 串表达式。

## 输出格式

以一行的形式输出这个 Kitty 猫基因的 ABC 编码。

## 输入输出样例 #1

### 输入 #1

```
00
```

### 输出 #1

```
A
```

## 输入输出样例 #2

### 输入 #2

```
01001011
```

### 输出 #2

```
CCCABACCBAB
```

## 说明/提示

给出的 01 字符串长度 $\text{Len}\leq 256$。
## 代码
```C++
#include <bits/stdc++.h>
using namespace std;
bool check(string s,char v)
{
    for(int i=0;i<s.size();i++)
    {
        if(s[i]!=v) return false;  //是不等于！
    }
    return true;
}
string kt(string s)//递归搜索树 画
{
    if(check(s,'0')) return "A";//先写return条件
    if(check(s,'1')) return "B";
    string s1,s2;
    for(int i=0;i<s.size()/2;i++)//分割注意区间
    {
        s1+=s[i];
    }
    for(int i=s.size()/2;i<s.size();i++)
    {
        s2+=s[i];
    }
    return "C"+kt(s1)+kt(s2);//字符串才能+拼接 所以这里C要化成字符串
}
#define int long long
signed main()
{
    string s;
    cin>>s;
    cout<<kt(s)<<endl;
    return 0;
}
```