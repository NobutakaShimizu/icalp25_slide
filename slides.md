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

<div class="grid grid-cols-10 gap-8 place-items-center h-56">

<div class="col-span-6">

[**Nobutaka Shimizu**](https://sites.google.com/view/nobutaka-shimizu/home) (Institute of Science Tokyo)

joint work with Shuichi Hirahara (National Institute of Informatics)

</div>
<div class="col-span-4">

  <QRCode value="https://nobutakashimizu.github.io/icalp_2025/" :size="120" render-as="svg"/>

<div class="text-center text-blue-500 text-sm">

[proceedings](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ICALP.2025.97)

[ECCC](https://eccc.weizmann.ac.il/report/2025/031/)

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
# Question
::content::

<div class="question">

What does this plot represent?🤔

</div>


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




---
layout: top-title
color: amber-light
---

::title::

# Matrix Multiplication

::content::

<div class="topic-box">

Improvements of exponents in fast square matrix multiplication algorithms

</div>

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



---
layout: top-title
color: amber-light
---

::title::

# Computational Complexity of Matrix Multiplication

::content::

<div class="grid grid-cols-7 gap-4">

<div class="col-span-6">

<div class="topic-box">

<div style="text-align: center;">

You need to wait for **$>$ 3000 years**...

(if the current improvement rate of 0.0046 / 35 years continues)

</div>

</div>

</div>

<div class="col-span-1">

![coldsleep](./images/coldsleep_man.png)

<figcaption style="text-align: center; font-size: 0.6em; color: #666;">

Need coldsleep!

</figcaption>


</div>

</div>



<div style="width: 80%; margin: 0 auto;">

<figure>

![computational complexity of matrix mult](./images/plot.png)

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

- $\alpha = 1$: the usual (average-case) matrix mult

- $\alpha = \frac{1}{\abs{\F}}$ and $\alpha=\frac{1}{n}$ are easy (random matrix or compute $n$ entries)

- This paper: small $\abs{\F}$ (indeed constant size field)

- An algorithm is non-trivial if $\alpha \ge \frac{1}{\abs{\F}} + \textcolor{c2185b}{\varepsilon}$ (better than random guess)

</v-clicks>

---
layout: top-title
color: amber-light
---

::title::

# Practical Situation: low-energy matrix multiplication

::content::

- AI rely on large-scale matrix mult on GPU
  - According to [International Energy Agency](https://www.iea.org/reports/electricity-2024/executive-summary), in 2026, **electricity consumption** from data centres, AI and the cryptocurrency could be the same as the total electricity consumption of Japan.

<v-click>

- Implementation of matrix mult algorithms using **physical devices**
  - Water flow <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ITCS.2024.96" class="cite-reference">\[Valinat, ITCS'24\]</a>, thermodynamic systems <a href="https://openreview.net/forum?id=6flkWTzK2H" class="cite-reference">\[Coles et al, NeurIPS'23 (workshop)\]</a>, optical devices <a href = "https://www.nature.com/articles/s41377-022-00717-8" class="cite-reference">\[Zhou et al, Light: Science & Applications'22\]</a>
  - Submarine communications cables are based on **optical** fibers

</v-click>

<v-clicks>

- These algorithms may have **errors** due to white noise in physical systems
  - Physical devices solve **approximate** matrix mult


<div class="topic-box">

This paper presents how to correct such error!😄

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
  - $\exists$ algo with $\alpha>\frac{8}{9}$ $\Rightarrow$ $\exists$ algo with $\alpha=1$
  - open question: $\alpha\ge \frac{1}{\abs{\F}}+\varepsilon$?

- Our previous work <a class="cite-reference" href="https://dl.acm.org/doi/10.1145/3717823.3718244">\[Hirahara, S., STOC'25\]</a>
  - If $\abs{\F}=O(1)$, $\exists$ algo with average-agreement $\frac{\textcolor{c2185b}{2}}{\abs{\F}}+\varepsilon$ $\Rightarrow$ $\exists$ algo with average-agreement $1$
    - does not work for $\F=\F_2$
  - If $\abs{\F}=O(1)$, $\exists$ **circuit** with average-agreement $\frac{\textcolor{c2185b}{1}}{\abs{\F}}+\varepsilon$ $\Rightarrow$ $\exists$ **circuit** with average-agreement $1$
    - **nonuniform**: for every $n$, there exists a reduction $R_n$ such that ...
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

- Resolves the open question of <a class="cite-reference" href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2024.34">\[Gola, Shinkar, Singh, RANDOM'24\]</a>
- Independently, <a class="cite-reference" href="https://arxiv.org/abs/2502.13065">\[Vaikuntanathan, Zamir, '25\]</a> showed the same result (completely different approach)
  - conditional (under the hardness of **Learning with Error**)
  - much better overhead: **$\polylog(\abs{\F}/\varepsilon)$**

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

Construct $A'$ and $B'$ such that $A'\cdot B'$ is the encoding of $AB$.

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

<div class = "topic-box">

What we need: **$\widetilde{O}(N)$-time list-decodable code**

</div>

</v-click>

---
layout: top-title
color: amber-light
---
::title::
# Previous Technique \[Hirahara, S., STOC'25\]
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
# Previous Technique \[Hirahara, S., STOC'25\]
::content::

<div style="display: flex; justify-content: center; align-items: center;">

![tensor encoding](./images/LRreduction.svg)

</div>

- Product = Tensor encoding of $AB$
- We can identify $AB$ from the list by **Freivalds' randomized verification**


---
layout: top-title
color: amber-light
---
::title::
# New Reduction (Sketch)
::content::

- The loss of $2$-factor in $\alpha$ is due to decoding algo for tensor codes
- key idea: avoid tensor code using **expander-walk lifting**

<div style="display: flex; justify-content: center; align-items: center;" v-click>

![Code](./images/expander_walk_reduction.svg)

</div>

---
layout: top-title
color: amber-light
---
::title::
# Expander-Walk Code
::content::

<div class="definition">

Let $G=(V,E)$ be a $d$-regular **expander** graph and 
$W\subseteq V^\ell$ be the set of all walks of length $\ell-1$ on $G$ (specifically, $W \subseteq V^\ell$).
**Expander-walk code** is the code defined by the following encoding function $\Enc\colon \F^V\to\F^W$:

$$
  \Enc(x) = \rbra{ x(v_0)+x(v_1)+\dots+x(v_{\ell-1}) }_{(v_0,v_1,\dots,v_{\ell-1})\in W }
$$

</div>

<div style="display: flex; justify-content: center; align-items: center;">

![Expander-walk code](./images/expanderwalk.svg)

</div>

<figcaption style="text-align: center; font-size: 0.8em; color: #666;">

Sum the values of vertices traversed by a walk of length $2$

</figcaption>

- $\widetilde{O}(\abs{W})$-time approximate list-decoding algorithms <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, Srivastava, Tulsiani, STOC'21\]</a>, <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, RANDOM'23\]</a>

---
layout: top-title
color: amber-light
---
::title::
# Lifting
::content::

<div style="display: flex; justify-content: center; align-items: center;">

![lifting](./images/expander_construction.svg)

</div>

<figcaption style="text-align: center; font-size: 0.8em; color: #666;">

Matrix $A'$ becomes an $\abs{W}\times kn$ matrix. The $\mathbf{i}=(i_1,\dots,i_k)$-th row contains the $i_1$-th row vector, $i_2$-th row vector, ... of $A$.
$B'$ is constructed by applying the same operation to $B$ with rows and columns interchanged.

</figcaption>

---
layout: top-title
color: amber-light
---
::title::
# Product of Lifting
::content::

<div style="display: flex; justify-content: center; align-items: center;">

![Matrix construction](./images/lifting.svg){width=90%}

</div>

- The $(\mathbf{i},\mathbf{j})$-th entry of $A'\cdot B'$ equals $(AB)_{i_1,j_1} + \dots + (AB)_{i_k,j_k}$ -> "XOR" of $k$ entries of $AB$
- Sum along the walk $(i_1,j_1)\to \dots \to (i_k,j_k)$ on the tensor product $G^2$.

<div class="topic-box">

$A'B'$ is encoding of $AB$ using the **expander-walk code** on $G^2$.

</div>

---
layout: top-title
color: amber-light
---
::title::
# New Reduction (again)
::content::

<div style="display: flex; justify-content: center; align-items: center;">

![Code](./images/expander_walk_reduction.svg)

</div>

- encoding: $O(n^2)$-time
- decoding: $\widetilde{O}(n^2)$-time <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, Srivastava, Tulsiani, STOC'21\]</a>, <a href="https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.APPROX/RANDOM.2023.60" class="cite-reference">\[Jeronimo, RANDOM'23\]</a>


---
layout: top-title
color: amber-light
---
::title::
# Summary
::content::

<div class="topic-box">

Optimal **worst-case-to-average-case** and **exact-to-approximate** reduction for matrix mult.

</div>

<div class="grid grid-cols-2 gap-4">

<div>

- Open Question
  - Reduce the hidden constant **$2^{2^{\poly(p/\varepsilon)}}$**?
  - matrix over **$\Real$** or **$\mathbb{Q}$**?
    - how to formalize? (ideas welcome!!!)

- Our future plan
  1. Deal with real numbers
  2. Implement (perhaps using optical devices)
  <v-click>3. Sell it to NVIDIA or OpenAI </v-click>

</div>

<div v-click="1" style="display: flex; justify-content: center; align-items: center; flex-direction: column;">

<img src="./images/money_okanemochi.png" alt="okanemochi" style="width: 60%; height: 60%" />

<div style="display: flex; justify-content: center; align-items: center;" v-click="2">
<QRCode value="https://nobutakashimizu.github.io/icalp_2025/" :size="70" render-as="svg"/>
</div>

<div v-click="2">

Thank you!

</div>

</div>




</div>
