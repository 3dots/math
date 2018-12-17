# Probability Theory: The Logic of Science by E. T. Jaynes [link](http://omega.albany.edu:8008/JaynesBook.html)

## Chapter 1: Plausible Reasoning

**syllogism**: an instance of a form of reasoning in which a conclusion is drawn (whether validly or not) from two given or assumed propositions (premises), each of which shares a term with the conclusion, and shares a common or middle term not present in the conclusion (e.g., all dogs are animals; all animals have four legs; therefore all dogs have four legs ).
- deductive reasoning as distinct from induction.

Scientists use mostly these two:

1. If A is true, then B is true.
2. B is false.
=> 3. A is false.

AND

1. If A is true, then B is true.
2. B is true => A is more plausible.

**contrapostion**: conversion of a proposition from all A is B to all not-B is not-A.

"If it's raining" => "Sam will meet Jack at the movies".

Not equivalent to

"Saw will not meet Jack at the movies" => "It isn't raining."

>Every time we can construct a mathematical model which reproduces a
part of common sense by prescribing a definite set of operations, this shows us how to "build a machine" (i.e., write a computer program) which operates on incomplete data and, by applying quantitative versions of the above weak syllogisms, does plausible reasoning instead of deductive reasoning.

**abberation**: a departure from what is normal, usual, or expected, typically one that is unwelcome.

- Biology: a characteristic that deviates from the normal type.
- Optics: the failure of rays to converge at one focus because of limitations or defects in a lens or mirror.

**desiderata**: things wanted or needed.

**conjuntion**: product, AND operation.  
**disjuntion**: sum, OR operation.

**same truth value**: A iff B means A,B have same truth value. iff means necessary and sufficient.

Two propositions with the same truth value, are equally plausible.

A = B


# 5:03pm 12.08.2018
# 7:54am 12.10.2018
# 6:45pm 12.10.2018
# 7:31pm 12.16.2018
Highlight surrounding brackets? Improve extension?
Clickning on result focuses vscode

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
(B|C)S\bigl((\overline A|BC)\bigr)$$

$$\tag{1}
(A|C)S\Biggl(\frac{(A\overline B|C)}{(A|C)}\Biggr) = (B|C)S\Biggl(\frac{(\overline AB|C)}{(B|C)}\Biggr)$$

Let $\overline A = BD \Rightarrow A\overline B = \overline B$ and $\overline AB = \overline A$.

Thus:
$$(A\overline B|C) = (\overline B|C) = 
S\bigl((B|C)\bigr)$$

$$(\overline AB|C) = (\overline A|C) = 
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
    \alpha(x) := \ln\biggl(\frac{-xS'(x)}{S(x)}\biggr)   &
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
$g(q) := \ln\Bigl(
    \frac{S(x)}{x}
    \frac{e^{-J(q)}}{e^{-J(q + \alpha(x))}}
    \frac{1}{1 - e^{-q}}
\Bigr)$

Goal is to show: $g(q) = O(e^{-2q})$
$e^{g(q)} = \frac{\frac{S(x)}{x}\frac{S(1-e^{-q})}{1-e^{-q}}}
{e^{-J(q + \alpha(x))}}
= \frac{\frac{y(q)}{x}S\biggl({ \frac{S(x)}{y(q)} }\biggr)}
{S\bigr(1 - e^{-(q + \alpha(x))} \bigl)} =
\frac{S\bigl({S(y(q))\over x}\bigr)}
{S\bigr( {S(x)\over y(q + \alpha(x))} \bigl)}$

$S(x)$ is strictly decreasing, thus $S'(x) \lt 0 $ for $0 \lt x \lt 1$

${\partial_y}(1):
S\Bigl(\frac{S(x)}{y}\Bigr) + 
yS'\Bigl(\frac{S(x)}{y}\Bigr)\frac{-S(x)}{y^2}
= xS'\Bigl(\frac{S(y)}{x}\Bigr)\frac{S'(y)}{x}$

$S'(y)S'\Bigl(\frac{S(y)}{x}\Bigr) +
\frac{S(x)}{y}S'\Bigl(\frac{S(x)}{y}\Bigr) =
S\Bigl(\frac{S(x)}{y}\Bigr)$

$(S'(x) + \frac{S(x)}{x})S'\Bigl(\frac{S(x)}{x}\Bigr) =
S\Bigl(\frac{S(x)}{x}\Bigr) \ge 0$
$\Rightarrow S'(x) + \frac{S(x)}{x} \le 0$

${-xS'(x)\over S(x)} \ge 1$
$\Rightarrow \alpha(x) \ge 0$

$1 - e^{-(q + \alpha(x))} \ge 1 - e^{-q}$

${S(x)\over y(q + \alpha(x))} \ge {S(x)\over y(q)}$

$S\bigg({S(x)\over y(q + \alpha(x))}\bigg) \le S\bigg({S(x)\over y(q)}\bigg)$

${1\over S\bigg({S(x)\over y(q + \alpha(x))}\bigg)} \ge 
{1\over S\bigg({S(x)\over y(q)}\bigg)}$

${S(x)\over 1 - e^{-(q + \alpha(x))}} \le {S(x)\over 1 - e^{-q}}$
$y(q + \alpha(x)) \le y(q)$

${S\big(y(q + \alpha(x))\big)\over x} \ge {S\big(y(q)\big)\over x}$

$ S\Bigg({S\big(y(q)\big)\over x}\Bigg) \ge 
S\Bigg({S\big(y(q + \alpha(x))\big)\over x}\Bigg)$



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

