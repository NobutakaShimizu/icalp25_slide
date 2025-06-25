---
theme: neversink
layout: cover
title: An Optimal Error-Correcting Reduction for Matrix Multiplication
info: |
  ## An Optimal Error-Correcting Reduction for Matrix Multiplication
  ICALP 2025

author: Nobutaka Shimizu
mdc: true
css: unocss
style: |
  @import './styles/custom.css';
addons:
  - slidev-addon-rabbit
rabbit:
  slideNum: true 
fonts:
  sans: 'Roboto'
  mono: 'Fira Code'
  weights: '400,500,700'
  italic: true
favicon: 'https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6/svgs/solid/book.svg'
themeConfig:
  primary: '#1976d2'


---

# An Optimal Error-Correcting Reduction for Matrix Multiplication

<div class="grid grid-cols-2 gap-4 place-items-center h-56">

<div>

- Shuichi Hirahara (National Institute of Informatics)
- [**Nobutaka Shimizu**](https://sites.google.com/view/nobutaka-shimizu/home) (Institute of Science Tokyo)

</div>
<div>

  <QRCode value="https://nobutakashimizu.github.io/stoc25_slide/" :size="120" render-as="svg"/>

<div class="text-center text-blue-500 text-sm">

  $\uparrow$ [slide (github page)](https://nobutakashimizu.github.io/stoc25_slide/)

  [ECCC link](https://eccc.weizmann.ac.il/report/2025/031/)

</div>
</div>

</div>

:: note ::
<div class="text-slate-500">
  @ICALP 2025
</div>

---
layout: top-title
color: amber-light
---

::title::

# Matrix Multiplication

::content::

<div class="topic-box">

Given two matrices $A, B \in \F^{n\times n}$, compute their product $AB$ (over a finite field $\F$).

</div>

<v-click>

<div style="display: flex; gap: 1em; font-size: 0.7em; border: 1px solid #ccc; padding: 0.5em; border-radius: 5px;">
<div>

| year | $\omega$ |  authors |
|:--:|:--|:--|
| 1968 | $2.807$ | [Strassen](https://link.springer.com/article/10.1007/BF02165411) |
| 1978 | $2.795$ | [Pan](https://ieeexplore.ieee.org/document/4567976) |
| 1979 | $2.779$ | [Bini, Capovani, Romani, Lotti](https://www.sciencedirect.com/science/article/pii/0020019079901133) |
| 1981 | $2.522$ | [Schönhage](https://epubs.siam.org/doi/10.1137/0210032) |
| 1981 | $2.517$ | [Romani](https://epubs.siam.org/doi/10.1137/0211020) |

</div>
<div>

|year | $\omega$ | authors |
|:--:|:--|:--|
| 1981 | $2.496$ | [Coppersmith, Winograd](https://ieeexplore.ieee.org/document/4568320) |
| 1986 | $2.479$ | [Strassen](https://ieeexplore.ieee.org/document/4568194) |
| 1990 | $2.3755$ | [Coppersmith, Winograd](https://www.sciencedirect.com/science/article/pii/S0747717108800132?via%3Dihub) |
| 2010 | $2.3737$ | [Stothers](https://era.ed.ac.uk/handle/1842/4734) |
| 2012 | $2.3729$ | [Williams](https://dl.acm.org/doi/10.1145/2213977.2214056) |

</div>
<div>

| year | $\omega$ | authors |
|:--:|:--|:--|
| 2014 | $2.3728639$ | [Le Gall](https://dl.acm.org/doi/10.1145/2608628.2627493) |
| 2020 | $2.3728596$ | [Alman, Williams](https://theoretics.episciences.org/14213) |
| 2022 | $2.371866$ | [Duan, Wu, Zhou](https://ieeexplore.ieee.org/document/10353208) |
| 2024 | $2.371552$ | [Williams, Xu, Xu, and Zhou](https://epubs.siam.org/doi/10.1137/1.9781611977912.134) |
| 2025 | $2.371339$ | [Alman, Duan, Williams, Xu, Xu, and Zhou](https://epubs.siam.org/doi/10.1137/1.9781611978322.63) |

</div>
</div>

<style>
th {
  background-color: #f0f0f0;
}
</style>

</v-click>

---
layout: top-title
color: amber-light
---

::title::

# Computational Complexity of Matrix Multiplication

::content::

<div class="question">

When can we get an $O(n^2)$-time algorithm?🧐

</div>

<v-click>

<div style="width: 55%; margin: 0 auto;">
```mermaid
---
config:
    themeVariables:
        xyChart:
            plotColorPalette: "#0000FF"
---
xychart-beta
    x-axis [1968, 1968, 1978, 1979, 1981, 1981, 1981, 1986, 1990, 2010, 2012, 2014, 2020, 2022, 2024, 2025]
    y-axis 2 --> 3
    line [3, 2.807, 2.795, 2.779, 2.522, 2.517, 2.496, 2.479, 2.3755, 2.3737, 2.3729, 2.3728639, 2.3728596, 2.371866, 2.371552, 2.371339]
```
</div>

<style>
th {
  background-color: #f0f0f0;
}
</style>

</v-click>

---
layout: top-title
color: amber-light
---

::title::

# Computational Complexity of Matrix Multiplication

::content::

<div class="topic-box">

<div style="text-align: center;">

😭😭😭😭 We need to wait **3122 years** 😭😭😭😭

if the current improvement rate of 0.0046 / 35 years continues

</div>

</div>



<div style="width: 80%; margin: 0 auto;">

<figure>

![computational complexity of matrix multiplication](./images/plot.png)

</figure>

</div>


---
layout: top-title
color: amber-light
---

::title::

# Average-Case Approximate Matrix Multiplication

::content::


<div class="topic-box">

Given two **random** matrices $A,B\sim\F^{n\times n}$ as input, compute any matrix $C\in\F^{n\times n}$ that agrees with $AB$ on at least $\textcolor{c2185b}{\alpha}\cdot n^2$ entries.

</div>

<div style="display: flex; justify-content: center; align-items: center;">

![](./images/approximate_MM.svg)

</div>

<v-clicks>

- $\alpha = 1$: the usual (average-case) matrix multiplication

- $\alpha = \frac{1}{\abs{\F}}$ is easy (random matrix)

- An algorithm is non-trivial if $\alpha \ge \frac{1}{\abs{\F}} + \textcolor{c2185b}{\varepsilon}$ (better than random guess)

</v-clicks>

---
layout: top-title
color: amber-light
---

::title::

# Practical Situation: low-energy matrix multiplication

::content::

- AI rely on large-scale matrix multiplication on GPU
  - According to [International Energy Agency](https://www.iea.org/reports/electricity-2024/executive-summary), in 2026, **electricity consumption** from data centres, AI and the cryptocurrency could be the same as the total electricity consumption of Japan.

<v-click>

- Matrix multiplication algorithms using **physical devices** (aiming at low energy consumption)
  - Water flow <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ITCS.2024.96" class="cite-reference">\[Valinat, ITCS'24\]</a>, thermodynamic systems <a href="https://openreview.net/forum?id=6flkWTzK2H" class="cite-reference">\[Coles et al, NeurIPS'23 (workshop)\]</a>, optical devices <a href = "https://www.nature.com/articles/s41377-022-00717-8" class="cite-reference">\[Zhou et al, Light: Science & Applications'22\]</a>
  - [post](https://www.quantamagazine.org/ai-needs-enormous-computing-power-could-light-based-chips-help-20240520/) by Quanta Magazine

</v-click>

<v-clicks>

- These algorithms may have **errors** due to white noise in physical systems
  - Physical devices solve **approximate** matrix multiplication


<div class="topic-box">

We show how to **correct** the errors in average-case approximate matrix multiplication algorithms.

</div>

</v-clicks>

---
layout: top-title
color: amber-light
---

::title::

# Problem Setting (Formal)

::content::

<div class="definition">

The **agreement** of two matrices $C,D\in\mathbb{F}^{n\times n}$ is defined as

$$
  \begin{align*}
    \agr(C,D) &:= \Pr_{i,j\sim[n]}[C(i,j) = D(i,j)].
  \end{align*}
$$

An algorithm $M$ is said to have **average agreement $\alpha$** if
$$
\Exp_{A,B\sim\mathbb{F}^{n\times n}}[\agr(M(A,B),AB)] = \Pr_{\substack{A,B\sim\F^{n\times n}\\ i,j\sim[n]}}[M(A,B)_{i,j}=(AB)_{i,j}]\ge \alpha.
$$
 
 </div>


<v-clicks>

- $\alpha=1$ means that $M$ computes $AB$ exactly for any input $A,B$.
- Why **average-case**?🤔 -> we can estimate **$\alpha$** in $\widetilde{O}(n^2)$ time by random sampling🤓
  - Choose $A,B,i,j$ and check whether $M(A,B)_{i,j}=(AB)_{i,j}$

</v-clicks>

---
layout: top-title
color: amber-light
---

::title::

# Previous Results

::content::

- Worst-case to average-case reductions for **exact** matrix mult
  - <a href="https://www.sciencedirect.com/science/article/pii/002200009390044W?via%3Dihub" class="cite-reference">\[Blum, Luby, Rubinfeld, JCSS'93\]</a>, <a href="https://dl.acm.org/doi/10.1145/3519935.3520041" class="cite-reference">\[Asadi, Golovnev, Gur, Shinkar, STOC'22\]</a>, <a href="https://dl.acm.org/doi/10.1145/3564246.3585189" class="cite-reference">\[Hirahara, S., STOC'23\]</a>

<v-clicks>

- The first **approximate** matrix mult result: <a class="cite-reference" href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2024.34">\[Gola, Shinkar, Singh, RANDOM'24\]</a>
  - Similar result for $\F=\F_2$ (under one-sided error setting)
  - $\exists$ algo with $\alpha>\frac{8}{9}$ $\Rightarrow$ $\exists$ algo with $\alpha=1$

- Improvement: <a class="cite-reference" href="https://dl.acm.org/doi/10.1145/3717823.3718244">\[Hirahara, S., STOC'25\]</a>
  - If $\abs{\F}>n/\alpha^2$, $\exists$ algo with average-agreement $\alpha$ $\Rightarrow$ $\exists$ algo with average-agreement $1$.
  - If $\abs{\F}=O(1)$, $\exists$ algo with average-agreement $\frac{\textcolor{c2185b}{2}}{\abs{\F}}+\varepsilon$ $\Rightarrow$ $\exists$ algo with average-agreement $1$
  - If $\abs{\F}=O(1)$, $\exists$ **circuit** with average-agreement $\frac{\textcolor{c2185b}{1}}{\abs{\F}}+\varepsilon$ $\Rightarrow$ $\exists$ **circuit** with average-agreement $1$
    - **nonuniform**: for every $n$, there is a reduction $R_n$ such that ...
</v-clicks>

---
layout: top-title
color: amber-light
---

::title::

# Main Result

::content::

<div class="question">

Is there a **uniform reduction** that works for $\alpha\ge\frac{\textcolor{c2185b}{1}}{\abs{\F}}+\varepsilon$?

</div>

<v-clicks>

<div class="theorem">

Suppose $\abs{\F}$ is prime.
If there exists a $T(n)$-time algorithm with average agreement **$\alpha\ge \frac{1}{\abs{\F}}+\varepsilon$**,
then there exists an $2^{2^{\poly(\abs{\F}/\varepsilon)}}\cdot T(n)\cdot \polylog(n)$-time algorithm with average agreement $1$.
</div>


- Independently, <a class="cite-reference" href="https://arxiv.org/abs/2502.13065">\[Vaikuntanathan, Zamir, '25\]</a> showed the same result (completely different approach)
  - conditional (under the hardness of **Learning with Error**)
  - much better overhead: **$\polylog(\abs{\F}/\varepsilon)$**

- Nonuniform reduction <a class="cite-reference" href="https://dl.acm.org/doi/10.1145/3717823.3718244">\[Hirahara, S., STOC'25\]</a> has overhead **$\abs{\F}\cdot\log(1/\varepsilon)\cdot\log n$**
</v-clicks>



---
layout: section
color: amber-light
---

# Proof Idea

---
layout: top-title
color: amber-light
---

::title::

# Idea: Matrix Encoding

::content::

$M$: worst-case approximation algorithm such that $\agr(M(A,B),AB)\ge\alpha$ for any $A,B\in\F^{n\times n}$

<div style="display: flex; justify-content: center; align-items: center;">

![Code](./images/reduction.svg)

</div>

<v-click>

<div class="topic-box">

Key point: Design encoding/decoding using **list-decodable codes**.

</div>

</v-click>

---
layout: top-title
color: amber-light
---

::title::

# Error-Correcting Codes

::content::

- An **encoding function** is a linear map $\Enc\colon \F^n\to\F^N$
  - $\Enc(z)=Lz$ for $L\in\F^{N\times n}$
  - A **code** is $\calC=\Enc(\F^n)\subseteq \F^N$
  
<div style="display: flex; justify-content: center; align-items: center;">

![code](./images/encoding.svg)

</div>    
  
<v-clicks>
  
- $r=n/N$: **rate** of $\calC$ (larger $r$ is better)
- **distance**: fractional Hamming distance, i.e., $\dist(x,y):=\Pr_{i\sim[N]}[x_i\ne y_i]$

</v-clicks>

---
layout: top-title
color: amber-light
---
::title::

# Error-Correcting Codes

::content::


<div class="definition">

A code $\calC\subseteq\F^N$ is **$(\rho,L)$-list-decodable** if $\abs{\calC \cap \ball(y,\rho)}\le L$ for any $y\in\F^N$.

</div>

- $\ball(x,\rho)=\{ y\in\F^N \colon \dist(x,y)\le\rho \}$ : Hamming ball.


<div style="display: flex; justify-content: center; align-items: center;">

![code](./images/list-decoding.svg)

</div>  

<v-click>

In this work, we need the following:

1. rate is $\Omega(1)$
2. $(1-\alpha/2,L)$-list-decodable for $L=\widetilde{O}(1)$ using an $\widetilde{O}(N)$-time algorithm.

</v-click>

---
layout: top-title
color: amber-light
---
::title::
# Tensor Code
::content::

<div class="definition">

The **tensor code** with respect to $\Enc\colon x\mapsto Lx$ is the code $\calC^2\subseteq\F^{N\times N}$ specified by the encoding function $\Enc'\colon \F^{n\times n} \to \F^{N\times N}$ defined by
  $$ \Enc'\colon X \mapsto L X L^\top. $$

</div>


<div style="display: flex; justify-content: center; align-items: center;">

![tensor encoding](./images/tensor.svg)

</div>

- original code is $(1-\textcolor{c2185b}{\alpha},O(1))$-list-decodable $\Rightarrow$ tensor code is $(1-\textcolor{c2185b}{2\alpha},O(1))$-list-decodable <a href="https://epubs.siam.org/doi/10.1137/090778274" class="cite-reference">\[Gopalan, Guruswami, Raghavendra, SICOMP'11\]</a>.

  - the non-optimality of $\alpha\ge \frac{\textcolor{c2185b}{2}}{\abs{\F}}+\varepsilon$ in our uniform reduction is due to this loss

---
layout: top-title
color: amber-light
---
::title::
# Uniform Reduction
::content::

<div style="display: flex; justify-content: center; align-items: center;">

![tensor encoding](./images/LRreduction.svg)

</div>

<figcaption style="text-align: center; font-size: 0.8em; color: #666;">

We can identify $AB$ from the list by checking the Freivalds' randomized algorithm.

</figcaption>

---
layout: top-title
color: amber-light
---
::title::
# Uniform Reduction
::content::

- If $\abs{\F}=\Omega(n)$, we use the Reed-Solomon code
  - nearly linear time list-decoding algorithm <a href="https://ieeexplore.ieee.org/document/1459042" class="cite-reference">\[Alekhnovich, IEEE Trans. Inf. Theory'05\]</a>
- If $\F$ is small, we use an expander-based code <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, Srivastava, Tulsiani, STOC'21\]</a>, <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, RANDOM'23\]</a>
  - rate $\Omega(1)$, list size $O(1)$, and list-decodable within radius $1-\frac{1}{\abs{\F}}-\varepsilon$ in $\widetilde{O}(N)$ time
  - $\Omega(1)$-rate code + direct sum over expander walk or HDX
  - hidden constant factor is $2^{2^{\poly(\abs{F}/\varepsilon)}}$ due to regularity lemma of list-decoding algorithm

<div class="topic-box">

This reduction is **exact-to-approximate** but **worst-case to worst-case**.

</div>

---
layout: top-title
color: amber-light
---
::title::
# Worst-Case to Average-Case Reduction
::content::

- Issue: even if $A,B\sim\F^{n\times n}$, their encodings $LA,BL^\top$ are **not** uniform

- **Idea**: divide $LA, BL^\top$ into small blocks such that each block is uniform
  - technical part: way to compute such division

<div style="display: flex; justify-content: center; align-items: center;">

![Code](./images/square.svg)

</div>


<figcaption style="text-align: center; font-size: 0.8em; color: #666;">

We divide $LA,BL^\top$ such that the marginal distribution of each $A_i,B_j$ is uniform.

</figcaption>


---
layout: top-title
color: amber-light
---
::title::
# Summary
::content::

<div class="topic-box">

If we can solve **approximate** matrix multiplication **on average**, then we can solve **exact** matrix multiplication for **any input** in almost the same time.

</div>

- **Technique**: encoding using **list-decodable code on expanders**
  - list-decoding algorithm by <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, RANDOM'23\]</a>

- Open Questions
  - Can we do something similar for matrix multiplication over the **real numbers**?
    - suitable for practical situation
  - Reduce the hidden constant **$2^{2^{\poly(p/\varepsilon)}}$** when the field is small (without any assumption)
    - How about $\log\log(n) \ll \abs{\F} \ll n$?