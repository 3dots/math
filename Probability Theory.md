# 5:03pm 12.08.2018

# 7:54am 12.10.2018

# 6:45pm 12.10.2018

$A, B$ binary propositions.
$(A|B) := P(A|B)$

$S: (A|B) \mapsto (\overline A|B)$
$S\bigr((A|B)\bigl) = (\overline A|B)$

By product rule:
$(\overline AB|C) = (B|C)(\overline A|BC)$
$(A\overline B|C) = (A|C)(\overline B|AC)$

$$
(AB|C) = (A|C)(B|AC) = (B|C)(A|BC)$$$$
(A|C)S\bigl((\overline B|AC)\bigr) = 
(B|C)S\bigl((\overline A|BC)\bigr)$$$$
\tag{1}
(A|C)S\Biggl(\frac{(A\overline B|C)}{(A|C)}\Biggr) = (B|C)S\Biggl(\frac{(\overline AB|C)}{(B|C)}\Biggr)$$
Let $\overline A = BD \Rightarrow A\overline B = \overline B$ and $\overline AB = \overline A$.
Thus:
$$(A\overline B|C) = (\overline B|C) = 
S\bigl((B|C)\bigr)$$$$
(\overline AB|C) = (\overline A|C) = 
S\bigl((A|C)\bigr)$$
$$\tag{1}
(A|C)S\Biggl(
    \frac{S\bigl((B|C)\bigr)}{(A|C)}
\Biggr) = 
(B|C)S\Biggl(
    \frac{S\bigl((A|C)\bigr)}{(B|C)}
\Biggr)$$
Let $x = (B|C), y = (A|C)$ then:
$(\overline A|C) = S(y) = (BD|C) = 
(B|C)(D|BC) \le x,$ 
and:
$$\tag{1}
yS\Biggl(\frac{S(x)}{y}\Biggr) ={ 
xS\Biggl(\frac{S(y)}{x}\Biggr),
{\begin{matrix}\begin{align}
0 \lt & x \le 1,    \\
0 \lt & S(y) \le x, \\    
0 \lt & y \le 1     \\    
\end{align}\end{matrix}}}$$
Define:
$\begin{matrix}
    {S(x)\over y(q)} = 1 - e^{-q}           & 
    y(q) := {S(x)\over 1 - e^{-q}},\; 
    {\begin{align} 
    q & \gt 0, \\ 
    q & \ge -\ln(1-S(x)) \\ 
    \end{align}}                            \\
    \alpha(x) := \ln(\frac{-xS'(x)}{S(x)})   &
    {\begin{matrix}
        e^{-q} \le 1 - S(x) \\
        -q \le \ln(1-S(x))   \\
    \end{matrix}}                           \\
\end{matrix}$

First goal, show that:
${S(y(q))\over x} = 1 - e^{-(q + \alpha(x))} + 
O(e^{-2q})$ as $q \to \infty$

From Taylor theorem:
$f(x) = \sum_{k=0}^n \frac{f^{(k)}(a)}{k!}(x - a)^k + h_n(x),$ where
$\begin{align}
h_n(x) & = o(|x-a|^n)   \\
 & = O(|x-a|^n)         \\ 
 & = O(|x-a|^{n+1})     \\
\end{align}$
as $x \to a$

Define:
$\begin{matrix}
    e^{-q(u)} = u                           & 
    q(u) := -\ln(u),\;      
    {\begin{align} 
    0 \lt u & \lt 1, \\ 
    u & \le 1 - S(x) \\ 
    \end{align}}                            \\
    {S(x)\over y\bigl(q(u)\bigr)} = 1 - u   & 
    y\bigl(q(u)\bigr) = {S(x)\over 1 - u}   \\
\end{matrix}$

$q \gt 0,\; {S(x)\over 1 - u} \le 1$
$u \le 1 - S(x)$

$h(u) := {S\bigl(y\bigr(q(u)\bigl)\bigr)\over x} =
{1\over x}S\Bigl({S(x)\over 1 - u}\Bigr)$
$h(0) = {1\over x}S(S(x)) = 1$
$h'(u) = {S(x)\over x}S'\Bigl({S(x)\over 1 - u}\Bigr)
\frac{-1}{(1-u^2)}$
$h'(0) = -{S(x)\over x}S'(S(x)) = 
\frac{-S(x)}{xS'(x)} = -e^{-\alpha(x)}$
1 = $\partial_x[S(S(x))] = S'(S(x))S'(x)$
Since $q \to \infty $ as $ u \to 0^+,$ by Taylor's Theorem, the intended equation is true.

Goal 2,show that:
$J(q + \alpha(x)) - J(q) = 
\ln\Bigl({x\over S(x)}\Bigr) + \ln(1 - e^{-q}) + 
O(e^{-2q})$
as $q \to \infty$

$\begin{matrix}
    e^{-J(q)} = S(1 - e^{-q})               & 
    J(q) := -\ln(S(1 - e^{-q})),\; q \gt 0   \\
\end{matrix}$
$\ln(e^{J(q + \alpha(x)) - J(q)}) + 
\ln(\frac{S(x)}{x}) - \ln(1 - e^{-q}) =$ 
$\ln\Bigl(
    \frac{S(x)}{x}
    \frac{e^{-J(q)}}{e^{-J(q + \alpha(x))}}
    \frac{1}{1 - e^{-q}}
\Bigr) =: g(q)$

Goal is to show: $g(q) = O(e^{-2q})$
$e^{g(q)} = \frac{S(x)}{x}\frac{S(1-u)}{1-u}
\frac{1}{e^{-J(q + \alpha(x))}}
= \frac{y(q)}{x}S\biggl({ \frac{S(x)}{y(q)} }\biggr)
\frac{1}{S(1 - e^{-(q + \alpha(x))})} =$
$ = S\biggl({S\bigl(y(q)\bigr)\over x}\biggr)
\frac{1}{S(1 - e^{-(q + \alpha(x))})} = 
\frac{S\biggl(
    {1\over x}S\Bigl({S(x)\over 1 - e^{-q}}\Bigr)
\biggr)}{S(1 - e^{-(q + \alpha(x))})}
$


${\partial_y}(1):
S\Bigl(\frac{S(x)}{y}\Bigr) + 
yS'\Bigl(\frac{S(x)}{y}\Bigr)\frac{-S(x)}{y^2}
= xS'\Bigl(\frac{S(y)}{x}\Bigr)\frac{S'(y)}{x}$
$S'(y)S'\Bigl(\frac{S(y)}{x}\Bigr) +
\frac{S(x)}{y}S'\Bigl(\frac{S(x)}{y}\Bigr) =
S\Bigl(\frac{S(x)}{y}\Bigr)$

.
.
.
.
$S'\Bigl(
    {S(x)\over 1 - u}
\Bigr)S'\Bigl(
    \frac{S(x)}{x}\frac{S(1-u)}{1-u}
\Bigr) + (1-u)S'(1-u) = S(1-u)$


$h(u) := {S\bigl(y\bigr(q(u)\bigl)\bigr)\over x} =
S\Bigl(
    \frac{S(x)}{x}\frac{S(1-u)}{1-u}
\Bigr)$
$h(0) := \lim_{u \to 0^+}h(u) = 
S\Bigl( \frac{S(x)}{x}S(1) \Bigr) = S(0) = 1$
$h'(u) = S'\Bigl(
    \frac{S(x)}{x}\frac{S(1-u)}{1-u}
\Bigr)\frac{S(x)}{x}\Bigl(
    \frac{S'(1-u)(-1)}{1-u} - 
    \frac{S(1-u)(-1)}{(1-u)^2} 
\Bigr)=$
$= \frac{S(x)}{x}\frac{1}{1-u}\Bigl(
    \frac{S(1-u)}{1-u} -
    S'(1-u)
\Bigr)S'\Bigl(
    \frac{S(x)}{x}\frac{S(1-u)}{1-u}
\Bigr)$

.
.
.
.
.
# 7:40am 12.11.2018
Git clone angular ubuntu and normal
git cline components likewise
dl vlc

Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\DefaultMediaCost"

Ideas: win key plus UP -> top half

# 8:29am
Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\DefaultMediaCost" -Name Ethernet
Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\DefaultMediaCost" -Name Ethernet -Value 1 ---non metered
Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\DefaultMediaCost" -Name Ethernet -Value 2 ---metered

# 7:15am 12.12.2018

Git remote upstream??? for material left.

Meter connection?

# 7:03am 12.13.2018

Copy music

Why is saving invoking net errr?
why is chrome stating on startup

m#

# 7:15am 12.14.2018

notifications win 10 shortcut
