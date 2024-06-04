---
dg-publish: 'true'
refference:
  - https://zh.wikipedia.org/wiki/ZFC
  - https://zhuanlan.zhihu.com/p/60294249
aliases:
  - 策梅洛-弗兰克尔集合论
---

**策梅洛 - 弗兰克尔集合论**（英语：Zermelo-Fraenkel Set Theory），是 [数学基础](https://zh.wikipedia.org/wiki/%E6%95%B0%E5%AD%A6%E5%9F%BA%E7%A1%80 "数学基础") 中最常用的 [一阶](https://zh.wikipedia.org/wiki/%E4%B8%80%E9%98%B6%E9%80%BB%E8%BE%91 "一阶逻辑")[公理化集合论](https://zh.wikipedia.org/wiki/%E5%85%AC%E7%90%86%E5%8C%96%E9%9B%86%E5%90%88%E8%AE%BA "公理化集合论")。含 [选择公理](https://zh.wikipedia.org/wiki/%E9%80%89%E6%8B%A9%E5%85%AC%E7%90%86 "选择公理") 时常简写为**ZFC**，不含选择公理的则简写为**ZF**。它是二十世纪早期为了建构一个不会导致类似 [罗素悖论](https://zh.wikipedia.org/wiki/%E7%BD%97%E7%B4%A0%E6%82%96%E8%AE%BA "罗素悖论") 的矛盾的 [集合理论](https://zh.wikipedia.org/wiki/%E9%9B%86%E5%90%88%E8%AE%BA "集合论") 所提出的一个 [公理系统](https://zh.wikipedia.org/wiki/%E5%85%AC%E7%90%86%E7%B3%BB%E7%BB%9F "公理系统")。



觉得有必要在第一章补充聊一下集合论的公理， ZFC 公理体系。ZF 是 Zermelo–Fraenkel 的简写，他们分别指数学家 Ernst Zermelo 和 Abraham Fraenkel；C 指选择公理 (Axiom of Choice)。合在一起简称 ZFC。

集合是由确定的元素构成的整体，或者是“一堆东西”。但是我们需要有一些公理来规定什么样的一堆东西可以是集合，什么样的一堆东西就不能是集合。不然会出问题，例：Russell 悖论， 令 $R$ 是由所有本身不为自己元素的集合构成的集合，即 $R = \{x 为集合 | x \notin x\}$ 那么我们就得到 $R \in R \iff R \notin R$ 这里有点绕，需要多读几遍，用通俗的话来讲罗素悖论：在某个城市中有一位理发师，他说：“本人的理发技艺十分高超，誉满全城。我将为本城所有不给自己理发的人理发，我也只给这些人理发。”—— 那么问题来了，他到底该不该给自己理发呢？

下面我们就按逻辑顺序逐条展开公理

首先我们需要确定两个集合的相等

**Axiom 1 (Extensionality)**

$\forall x,\forall y,\forall a$ ，若 $a \in x \iff a \in y$ ，那么 $x=y$ $\forall x\forall y\forall a: (a \in x \iff x \in y) \Rightarrow x = y$

至此，我们还不知道集合到底存不存在；所以接下来的公理规定至少空集是存在的

**Axiom 2 (Empty Set Exists) ** $\exists~ a, ~s.t. \forall~ x,~ x \notin a$ ; 称 $a$ 为空集，记作 $\emptyset$ $\exists a: \forall x ~\neg(x\in a)$

有了空集，接下来我们需要构造更多的集合

**Axiom 3 (Pairing) ** 任意给定两个元素 $x,y$ ，那么存在一个集合 $a$ 包含且只包含这两个元素
$\forall x \forall y ~ \exists a, ~\forall z, z \in a \iff ((z =x) \vee (z= y))$

> 注：这里的两个元素不一定要相异，我们可以取 $x=y=\emptyset$ ; 现在我们来 pairing 一个集合 $a$ ，使得 $z \in a \iff z = \emptyset$ , 这就相当于构造了新集合 $a=\{\emptyset\}$ ; 我们可以在此基础上继续运用这条公理，构造出更多的集合，比如 $\{\{\emptyset\}\}$ , 或是 $\{\emptyset, \{\emptyset\}\}$ ；而由此我们也可以构造出集合 $\{~\{\emptyset, \{\emptyset\}\} ,\{ \{\emptyset\}\}~\}$ 。这样我们就定义出一些不同 (结构) 的集合来，而且可以一直定义下去，这就可以用来表示 $0,1,2,\ldots$ ；当然到目前为止集合的构造还有很多限制，而最终的 von Nuemann 序数也不是基于这样的定义。我们继续往下看。

现在，如果给你两个集合 $x=\{a,b\}, y=\{c,d\}$ ; 仅仅使用上面的公理只能构造出集合 $z=\{\{a,b\},\{c,d\}\}$ (注：这里的集合还是两个元素)，但是构造不出集合 $\{a,b,c,d\}$ , 因为这个公理只让你构造一个集合包含两个元素。

于是, 我们需要以下的公理

**Axiom 4** **(Union) **给定集合 $A$ ，它所有元素的并 $\cup_{A}$ 也是一个集合。 $\forall A\exists B\forall c~(x \in B \iff \exists D (c\in D \wedge D \in A ))$

例： $A=\{\{a,b\},\{b,c\}\}$ , $A$ 的元素的并有也构成一个合法的集合 $\{a,b,c\}$

> 注：根据 **Axiom 2**, **Axiom 3** 跟 **Axiom 4**, 我们就能够构造出所有的有限序数 (也就是自然数)，且有顺序出来了： $0:=\emptyset \in 1:=\{\emptyset\}=\{0\} \in 2:=\{\emptyset, \{\emptyset\}\}=\{0, 1\} \in 3 =\{\emptyset, \{\emptyset\}, \{\emptyset, \{\emptyset\}\}\}=\{0,1,2\}\in \dots$；即，我们把 $\beta = \alpha \cup \{\alpha\}$ 定义为 $\alpha$ 的后继 (successor)，也就是 $\alpha + 1$

一个集合 $a$ 的幂集是指由 $a$ 的所有子集构成的集合，记作 $\mathcal P(a)$ 。例如 $\mathcal P(\{a, b\}) = \{\emptyset, \{a\}. \{b\}, \{a,b\}\}$ 。这个概念很重要，所以我们需要有公理来确保任何集合的幂集都存在

**Axiom 5 (Power Set)** $\forall a, \, \mathcal P(a)$ 存在。即， $\forall a \exists A \forall b~ (b \in A \iff b \subset a)$

至此，我们的集合已经初步成型了。我们在此基础插讲几个基于集合的定义。

**Definition 1.26: 有序对 (ordered pair)** $(x,y) :=\{\{x\}, \{x,y\}\}$ 注：很自然的可以拓展，比如三元有序列 $(x,y,z):=\{\{x\}, \{x, y\}, \{x,y,z\}\}$

**Definition 1.27: 集合上的二元关系 (binary relation)** 关系 $R$ 本身也是一个集合，它的元素是由集合上元素的有序对构成。任取 $a,b \in X$ , 称 $a,b$ 有关系 (related) , 记作 $a~R~b$ , 当且仅当有序对 $(a,b) \in R$

**Definition 1.28: 等价关系 (equivalence)** $\sim := \{(x,y)|x \sim y\}$ ; 其中 $\sim$ 表示： 1) $a \sim a$ 2) $a \sim b \iff b \sim a$ 3) $a \sim b, b \sim c \Rightarrow a \sim c$ 注：这里是用一个集合来表示一个等价关系，而这个集合是由所有符合这个等价关系的元素对构成

**Definition 1.29: 映射 (mapping) **也是用集合来表示 $f:=\{(x, f(x))\}$ ; 更严谨一些，映射 $f: A \mapsto B$ 是一个三元有序列 $f=(A,B,G_f), ~ G_f \subset A \times B$ , 满足:1) $(x, y) \in G_f, (x,y') \in G_f \Rightarrow y = y'$ 2) 投影函数 (projection) $\pi_1(G_f)=\{x | (x,y) \in G_f\} = A$

根据上面五个公理，我们就可以构建 von Neumann 宇宙 $V_n$ 了：令 $V_0 = \emptyset$ , 那么递归的定义 $V_{n+1} = \mathcal P(V_n)$ ，当超越自然数的时候，我们可以类似的定义：对于序数 $\beta$ , $V_{\beta+1}=\mathcal P (V_{\beta})$ ; 而当 $\lambda$ 是极限序数 (limit ordinal, 本篇下文会讲) 时，我们就定义 $V_{\lambda}=\bigcup_{\beta < \lambda}V_{\beta}$ 。也可以干脆把两种情况合起来：任取序数 $\alpha$ , $V_{\alpha}=\bigcup_{\beta < \alpha}\mathcal P(V_{\beta})$ 。 $V_{\alpha}$ 也被称为集合的阶 (stages or ranks)。我们把集合 $S$ 的阶定义成最小的序数 $\alpha$ 使得 $S \subset V_{\alpha}$ 。

假设我们得到宇宙 $V_{\omega}=\cup_{n\in \mathbb N} V_n$ , 你可以验证 $V_{\omega}$ 是符合上述五个公理的，或者说这个宇宙对于上面五条公理是相容的 —— 这里说假设，是因为我们还不知道 $V_{\omega}$ 是否存在。但这是一个比较无聊的宇宙，因为尽管宇宙中有无穷多个集合，其中的集合都只涉及有限元素的集合 (though there are infinitely many sets in the universe, there are no infinite sets)

接下来，我们讨论无限集 (infinite set); 首先, 我们需要禁掉无限的 $\in$ 链，即不存在无限向下的集合 " 属于 " 链： $x_1 \ni x_2\ni x_3 \ni \ldots$ 不存在

**Axiom 6 (Foundation/Regularity) **任何非空集合 $x$ 都含有元素 $y$ , 使得 $x \cap y = \emptyset$ : $\forall x(x \ne \emptyset \Rightarrow \exists y \in x(y \cap x=\emptyset))$

> 注：由此条公理并结合 Axiom 3 (Pairing)，我们就能推得 $\forall x, x \notin x$ 且任一集合都有序数阶 (ordinal rank)

回到我们上面讲的有限序数的讨论。我们很自然的想在有限序数的基础上扩展出无限的序数。首先想到的是，所有有限序数/自然数构成的集合 $\omega =\{0,1,2,3,\ldots\}$ ，可以简单验证这个 $\omega$ 是满足序数定义的 (文末会给出序数的严格定义)。但是，现在直接这样写 $\omega$ 是有问题的，因为我们现在还不知道这些写出来的 $\omega$ 是不是一个集合，这件事情需要由公理来保证。另一方面，我们不仅仅满足于 $\omega$ , 我们还希望在 $\omega$ 的基础上继续往大了数过去，这也需要有公理来保证。于是就有了如下两条公理：

**Axiom 7 (Replacement)** $f$ 是定义在集合 $X$ 上的一个映射，那么 $f$ 的值域 (range) 也是一个集合

**Axiom 8** **(Infinity) **存在这样的集合 $X$ : $\emptyset \in X, $ 且 $y \in X \Rightarrow y \cup \{y\} \in X$

我们来看一下上面这两条公理是如何帮助我们构建无限序数的。首先，根据之前的公理，我们已经可以合法的构造出了 $0,1,2,3, \ldots$ 这些有限序数，然后根据 Axiom 8，我们知道存在这么一个集合 $X$ 满足 $\emptyset \in X$ , 且 $ \forall y \in X, y \cup \{y\} \in X$ - 其实这就已经是在说这个 $X$ 就是我们要找的 $\omega$ 了。这是因为 $\emptyset \in X \Rightarrow 1= \emptyset \cup \{\emptyset\} \in X$ ; 然后任取有限序数 $N$ , 我们归纳运用 $N$ 次 **Axiom 8** 就能证明 $N \in X$ , 这就证明了 $X=\{1, 2, ...\} = w$ 是一个合法存在的集合。验证 $\omega$ 符合序数的定义我们放到文末。

所以，**Axiom 8 **也可以等价的写成：集合 $\omega =\{1, 2, ...\} $ 是存在的。现在，我们有了 $1,2, 3, \ldots,\omega$ ，同时，我们可以继续运用有限序数后继的定义来定义 $\omega$ 的后继： $\omega + 1 := \omega \cup \{\omega\}=\{0,1,2,\ldots, \omega\}$ , $\omega + 2 := (\omega + 1) \cup \{\omega + 1\} = \{0,1,\ldots, \omega, \omega+1\}$ , 等等；根据之前的 Axiom，这样定义出来的 $\omega +1, \omega + 2, \ldots$ 都是合法的集合，同时也可以验证这些集合满足序数的定义，于是我们的序数就扩充成了： $0, 1, 2\ldots, \omega, \omega+1, \omega+2, \ldots$ 接下来我们还想定义更大的序数，比如说 $\omega + \omega$ , 即把之前所有列出来的序数放到一起 - 这样还是一个集合吗？这里我们就需要用到 **Axiom 7 **了。考虑集合 $\omega$ 上的映射 $f(n) = \omega + n, ~ n \in \omega$ ；于是，我们一用 **Axiom 7** 有 $f$ 值域 $f(\omega) =\{f(0), f(1), f(2), \ldots\} =\{\omega, \omega+1, \omega+2, \ldots\} $ 也是一个集合; 然后再根据 **Axiom 3 ** $\{\omega, f(\omega)\}$ 也是一个集合; 最后运用 **Axiom 4 **对集合 $\{\omega, f(\omega)\}$ 中的元素取并集, 则 $\cup\{\omega, f(\omega)\}=\{0, 1, 2, \ldots, \omega, \omega + 1, \omega + 2, \ldots\} =\omega + \omega $ 也是一个集合。当然，如果要更严格来说；回忆上面讲到用有序对给出的映射的定义 $f:=\{(x, f(x))\}$ ，所以，我们还需要证明上面的 $f$ 满足映射的定义，即, $f$ 的集合编码 (set-encoding): $f = \{(x, f(x))~ |~ x \in \omega\}=\{(1 ,\omega+1), (2,\omega+2), \ldots\}$ 是一个集合，这边主要是借用序数来说明这些公理的动机，所以这部分的证明就略过了。

至此, 我们可以得到更大的集合: $\omega \cup \{\omega, \omega+1, \omega+2, \ldots\}=\{0,1,2,\ldots,\omega, \omega+1, \omega+2, \ldots\}$ 我们可以反复的利用公理不断的向上构建我们的序数： $0,1,2,3,\ldots,\omega, \\ \omega+1, \omega+2, \ldots, \omega + \omega = \omega \cdot 2 \\ \omega \cdot 2, \omega \cdot 2 +1, \omega \cdot 2+2, \ldots, \omega \cdot 2 + \omega =\omega \cdot 3,\\ \vdots,\\ \omega^2+1,\omega^2+2, \ldots,\\ \vdots,\\ \omega^3, \ldots, \omega^4, \ldots, \omega^{\omega},\\ \vdots,\\ \omega^{\omega^{\omega}}, \ldots, \omega^{\omega^{\omega^{\omega^{\ldots}}}} = \varepsilon_0,\\ \vdots,\\ \varepsilon _1, \ldots, \varepsilon_2, \ldots, \varepsilon_{\tau}, \ldots\\ \vdots$

注：我们下文也会讲到，上式中有 $\omega + \omega = \omega \cdot 2 \ne 2 \cdot \omega = \omega$ ; 交换律不满足。超过有限的时候，数的大小跟排序很有关系。令 $2=\{a, b\}; ~ \omega =\{1, 2, \ldots, n, \ldots\}$ ; 则：

$2\cdot \omega =Ord(\{(a, 1), (b, 1), (a, 2), (b, 2), \ldots\}) = \omega$ ; $\omega \cdot 2 = Ord( \{(1,a), (2,a), \ldots; (1,b), (2,b), \ldots\}) = \omega + \omega$

上式中, $Ord$ 是所有序数构成的类 (class) ，我们在 Definition 1.35 处细聊。

上式中的 $\varepsilon_{\tau}|_{\tau=0, 1, 2, \ldots}$ 是一列从小到大的序数, 满足 $\omega ^ {\varepsilon} = \varepsilon$ ; 下文会再遇到。

以上 8 条公理被称为 ZF 公理体系; 有时候这里还会加一条 (Comprehension) 公理：令 $\phi$ 为某一性质， $S$ 为一集合，那么 $\{x \in S | \phi(x)\}$ 也是一个集合。其实这一条公理是多余的，因为我们可以用 Axiom 2 (Empty Set Exists) 跟 Axiom 7 (Replacement) 把它推出来。

最后是选择公理，这个公理很重要，影响深远；有非常多很有用很漂亮的定理都是基于这个公理，但有时候它也会产生一些不可思议、违反直觉的结论。

**Axiom 9 (Choice) ** $\forall \mathcal F\, s.t. \emptyset\notin \mathcal F$ ，那么我们可以定义一个 $\mathcal F$ 上的映射 $g,\, s.t. \, \forall y \in \mathcal F, g(y) \in y$

> 注：映射 $g$ 也被称为选择函数 (choice function)， 它的作用就是从 $\mathcal F$ 里的每个集合中选出一个元素来；一旦能选出来了，那么我们就能把这些选出来的元素构成一个集合。即，给定一些列 $\mathcal F$ 中的集合/元素 $y$ , 我们可以用选择函数从每个 $y$ 中选出它的一个元素 $g(y)$ , 也就是说 $\{(y,g(y)|y \in \mathbb F, g(y) \in y\}$ 是一个合法存在的集合。 值得注意的是：我们可以从 ZF 公理证明选择函数对于有限个集合，一定可以找到一个选择函数；然而如果我们要从无限个集合里面选（不管这些集合是有限集还是无限集），我们都需要选择公理。当然，如果能够找到选择函数，那就不需要：比如说如果所有的集合中都有一个最大元素，那我们就可以选 $f=\max$ ，那就不需要用选择公理了。

至此，所有公理都阐述完毕了。当然，ZFC 的形式有好多种，上面说的只是一种形式，但是所有的形式都是等价的。

末了，我们简单提一下序数 (ordinals) 和基数 (cardinals)。

前面结合公理的讨论，我们已经把序数定义的差不多了，也有了很多直观的描述，这边再简单提一下更抽象的定义以及相关的性质。

**Definition 1.30: 偏序集 (partial-ordered set) **集合 $X$ 上存在一个二元关系 $<$ ，任取元素 $a,b,c \in X$ , 都满足一下条件： 1) $\forall a \in X, a \nless a$ 2) $a < b, b < c \Rightarrow a < c$

**Definition 1.31: 全/线序集 (total/linear-ordered set) **偏序集 $(X, <)$ 同时满足： 3) $\forall a, b \in X$ , $a < b, a=b, a>b$ 有且仅有一个成立

> 注：若 $<$ 是一个偏序 (线序), 那么相应的 $\le$ 也被称为偏序 (线序); 有时候会称 $<$ 为严格偏序 (线序) 以加区别。

**Definition 1.32: **令 $(X, <)$ 是偏序集, 非空集合 $P$ 是 $X$ 的一个子集，且 $a\in X$ , 那么： 1) $a$ 是 $P$ 的极大元 (maximal element), 若 $a \in P$ 且 $\forall x \in P, a \nless x$ 2) $a$ 是 $P$ 的极小元 (minimal element), 若 $a \in P$ 且 $\forall x \in P, x \nless a$ 3) $a$ 是 $P$ 的最大元 (greatest element), 若 $a \in P$ 且 $\forall x \in P, x \le a$ 4) $a$ 是 $P$ 的最小元 (least element), 若 $a \in P$ 且 $\forall x \in P, a \le x$

**Definition 1.33: 良序集 (well-ordered set) **集合 $(X, <)$ 是良序集，当且仅当： 1) $(X, <)$ 是全序集 2) $X$ 的所有非空子集在次序 $<$ 下都存在最小元素

**Definition 1.34: **称集合 $T$ 的传递性的 (transitive), 当且仅当： $\forall t \in T, t \subset T$

**Definition 1.35: **称集合 $\alpha$ 为序数 (ordinal number), 当且仅当 $\alpha$ 在二元关系 $\in$ 下是良序集，且具传递性

我们一般用小写希腊字母表示序数， $\alpha, \beta, \gamma. \ldots$ 。把所有序数构成的类 (class) 记为 $Ord$ 。注意我们这里用了类而没有说集合。类是一个比集合更宽泛的概念，集合肯定是一个类；但类不一定是集合；不是集合的类称为 proper 类 (proper class)。 ZFC 理论对类没有一个正式的定义，一般可以理解成一系列可以通过某一性质被明确定义的 " 合集“ (注：笔者这里抖机灵一个“合集”的概念，指一堆不一定是集合的东西)。 $Ord$ 不满足 集合的定义，但是我们还是可以通过性质明确描述它的所有元素，所以它是一个 proper class。

**Definition 1.36:** 序数 $\alpha < \beta \iff \alpha \in \beta$

列举序数的一些性质，证明很明显，略了： 1) $0 = \emptyset$ 是一个序数 2) 令 $\alpha$ 是一个序数，且 $\beta \in \alpha$ ，那么 $\beta$ 也是一个序数 3) $\alpha, \beta$ 是两个序数，且 $\alpha \ne \beta, \alpha \subset \beta$ , 那么 $\alpha \in \beta$ 4) $\alpha, \beta$ 是两个序数, 那么 $\alpha \subset \beta, ~\beta \subset \alpha$ 有且仅有一个成立 5) $<$ 是类 $Ord$ 上的一个线序/全序 6) 任取序数 $\alpha$ , 我们有 $ \alpha = \{\beta: \beta < \alpha\}$ 7) 令 $C$ 为非空序数类, 那么 $\bigcap C$ 是一个序数， $\bigcap C \in C$ ，且 $\bigcap C = \inf C$ 8) 若 $X$ 是一个非空序数集, 那么 $\bigcup X$ 是一个序数，且 $\bigcup X =\sup X$ 9) 任取序数 $\alpha$ ， $\alpha \cup \{\alpha\}$ 也是一个序数，且 $\alpha \cup \{\alpha\}=\inf\{\beta:\beta > \alpha \}$ ;

于是, 我们定义 $\alpha + 1 := \alpha \cup \{\alpha\}$ ，称为 $\alpha$ 的后继 (successor)

从上面的性质，我们也可以看到为什么 $Ord$ 是一个 proper 类，而不是一个集合：因为如果 $Ord$ 是集合，那么 $\sup Ord + 1$ 也是一个序数，于是就有 $\sup Ord + 1 \in Ord$ ，这就矛盾了**。**

**Theorem 1.37：**任意良序集都与一个唯一的序数同构 (isomorphic)。

> 证：略

令 $\alpha, \beta$ 为两个序数，若 $\alpha =\beta + 1$ ，那么称 $\alpha$ 为后继序数 (successor ordinal)；若 $\alpha$ 不是一个后继序数，那么 $\alpha=\sup\{\beta:\beta < \alpha\}=\cup \alpha$ , 称 $\alpha $ 为极限序数 (limit ordinal)。我们一般认为 $0$ 也是一个极限序数，并且定义 $\sup \emptyset = 0$

**Theorem 1.38 (超越归纳法/Transfinite Induction)：**令 $C$ 是某个序数类，且满足以下三个条件： 1) $0 \in C$ 2) $\alpha \in C \Rightarrow \alpha + 1 \in C$ 3) 若 $\alpha$ 是非零极限序数且 $\forall \beta < \alpha, \beta \in C$ ，那么 $\alpha \in C$ 则 $C=Ord$

> 证：略，都能搜到

**Definition 1.39：**令 $\alpha > 0$ 是一个极限序数，令 $\langle \gamma_{\epsilon}: \epsilon < \alpha \rangle$ 是一个非降的序数列 ( $\epsilon < \eta \Rightarrow \gamma_{\epsilon} \le \gamma_{\eta}$ )。我们定义这个序数列的极限为： $\lim_{\epsilon \to \alpha} \gamma_{\epsilon}:=\sup\{\gamma_{\epsilon}: \epsilon < \alpha\}$

称序数列 $\langle \gamma_{\alpha}: \alpha \in Ord \rangle$ 是规范的 (normal)，如果它是严格升序列，且连续的 (连续的意思指任取极限序数 $\alpha$ , 我们都有 $\gamma_{\alpha}=\lim_{\epsilon \to \alpha} \gamma_{\epsilon}$ )

接下来，讨论一下序数的运算**Definition 1.40 (加法定义): **任取 $\alpha \in Ord$ : 1) $\alpha + 0 = \alpha$ 2) $\forall \beta \in Ord, ~\alpha + (\beta + 1) = (\alpha + \beta) +1$ 3) $\beta$ 为任一极限序数，那么 $\alpha + \beta = \lim_{\epsilon \to \beta}(\alpha + \epsilon)$

**Definition 1.41 (乘法定义): **任取 $\alpha \in Ord$ : 1) $\alpha \cdot 0 = 0$ 2) $\alpha \cdot (\beta + 1)=\alpha \cdot \beta+ \alpha$ 3) $\beta$ 为任一极限序数，那么 $\alpha \cdot \beta =\lim_{\epsilon \to \beta} \alpha \cdot \epsilon$

**Definition 1.42 (乘方定义): **任取 $\alpha \in Ord$ : 1) $\alpha^ 0 = 1$ 2) $\alpha^{(\beta + 1)}=\alpha^\beta \cdot \alpha$ 3) $\beta$ 为任一极限序数，那么 $\alpha ^ \beta =\lim_{\epsilon \to \beta} \alpha^\epsilon$

**Lemma 1.43: **任取序数 $\alpha, \beta, \gamma$ , 我们有： 1) $\alpha+(\beta + \gamma)=(\alpha + \beta) + \gamma$ 2) $\alpha \cdot (\beta \cdot \gamma)=(\alpha \cdot \beta) \cdot \gamma$

> 证：对 $\gamma$ 用超越归纳法即可

所以序数的 $+$ 跟 $\cdot$ 运算满足结合律，但是它们不满足交换律, 比如： $1 + \omega = \omega \ne \omega + 1, 2\cdot \omega =\omega\ne \omega \cdot 2=\omega + \omega$

**Lemma 1.44: ** $\alpha, \beta, \gamma$ 都是序数，我们有： 1) $\beta < \gamma\Rightarrow \alpha + \beta < \alpha + \gamma$ 2) 若 $\alpha < \beta$ ，那么存在唯一的序数 $\delta$ 使得 $\alpha + \delta = \beta$ 3) 若 $\beta < \gamma$ 且 $\alpha > 0$ ，那么 $\alpha \cdot \beta < \alpha \cdot \gamma$ 4) 若 $\alpha > 0$ , $\gamma$ 为任一序数, 则存在唯一的序数 $\beta$ 及另一唯一序数 $\rho < \alpha$ , 使得 $\gamma = \alpha \cdot \beta + \rho$ 5) 若 $\beta < \gamma$ 且 $\alpha > 1$ ，那么 $\alpha^{\beta} < \alpha^{\gamma}$

> 证：略

**Theorem 1.45 (Cantor's Normal Form Theorem): **任意序数 $\alpha > 0$ 都能被唯一的表示称如下形式： $\alpha = \omega^{\beta_1}\cdot k_1 + \ldots + \omega^{\beta_n}\cdot k_n$ 其中序数 $\alpha \ge \beta_1 > \ldots > \beta_n$ ; 而 $k_1, \ldots, k_n$ 为非零有限， $n \ge 1, n \in \mathbb N$

> 证：我们对 $\alpha$ 做归纳。当 $\alpha=1$ 时，我们有 $1=\omega^0$ 。对于任意 $\alpha > 0$ , 假设结论对所有小于 $\alpha$ 的序数都成立；令 $\beta$ 为满足条件 $\omega^{\beta} \le \alpha$ 的最大序数, 根据 Lemma 1.44 (4) ($\omega^{\beta} > 0$ ), 我们知道存在唯一的序数 $\delta$ 以及唯一的序数 $\rho < \omega^{\beta}$ , 使得 $\alpha = \omega^{\beta}\cdot \delta + \rho$ (这边有 $\rho < \alpha$ ); 因为 $\beta$ 为满足条件 $\omega^{\beta} \le \alpha$ 的最大序数, 所以 $\delta$ 必须是有限序数，否则我们就有 $\alpha \ge \omega^{\beta} \cdot \delta \ge \omega^{\beta}\cdot \omega = \omega^{\beta+1}$ ，这就矛盾了；证毕。

上述的序数唯一展开式是有可能碰到 $\alpha=\omega^{\alpha}$ 的情况的，这个 $\alpha$ 就相当大了，我们把最小的满足这个情况的序数定义为 $\varepsilon_0$ 。我们可以把它构造出来：令 $\varepsilon_0 = \lim_{n \to \omega} \alpha_n$ , 其中 $\alpha_0 = \omega, \alpha_{n+1} = \omega^{\alpha_n}$ , 则 $\varepsilon_0$ 就是最小的序数满足 $\omega^{\varepsilon}=\varepsilon$

**Definition 1.46 **称两个集合 $X,~Y$ 拥有相同的势或基数 (cardinality/cardinal number), 记作 $|X|=|Y|$ ，当且仅当存在一个映射 $f: X\mapsto Y$ ,且 $f$ 是双射/单射 + 满射 (one-to-one and onto/bijection)

注：上述定义中的 $|X|=|Y|$ 是一个等价关系。基数的定义可以从 Axiom 6 (结合等价类)；或者从 Axiom 9 来。我们这边从 Axiom 9 入手, 定义 ZFC 体系中的基数。

我们说集合 $X$ 是有限的，如果 $|X|=|n|, n \in \mathbb N$ (注：这里 $n$ 就是构造有限序数的那个集合或者与之同构的集合)，然后我们说 $X$ 有 $n$ 个元素。显然 $|m|=|n|$ ，当且仅当 $m=n$ , 于是我们可以把有限基数等同于自然数。

**Definition 1.47 **(基数的序/ordering of cardinal numbers) $|X| \le |Y|$ ，当且仅当存在一个单射 (one-to-one/injection) $f: X \mapsto Y$ , 显然这个序具有传递性。定义 $|X| < |Y| \iff |X| \le |Y|, |X| \ne |Y|$

**Theorem 1.48 **(Cantor) $\forall X, |X| < |\mathcal P(X)|$

> 证：显然可以找到单射 $f(x) = \{x\}$ ，故 $|X| \le |\mathcal P(X)|$ 。任取映射 $f: X \mapsto \mathcal P(X)$ 。构造 $X$ 的子集 $Y=\{x \in X: x \notin f(x)\} \in \mathcal P(X)$ , 则 $Y$ 不在 $f$ 的值域里, 即 $Y \notin f(X)$ ：若 $z \in X$ 满足 $f(z) = Y$，则 $z \in Y \iff z \notin Y$ , 矛盾。所以 $f$ 不是满射，故 $|X| \ne |\mathcal P(X)|$

**Theorem 1.49 **(Cantor-Bernstein) 若 $|A| \le |B|$ 且 $|B| \le |A|$ ，那么 $|A| =|B|$

> 证：根据 Definition 1.47，我们知道存在 $f: A\mapsto B, ~ g: B\mapsto A$ 两个单射，而我们需要构造一个双射 $h: A \mapsto B$ 。令 $A_0 = A, B_0 = B$, 递归的定义 $B_{n+1}=f(A_n), A_{n+1}=A-g(B-B_{n+1})$ , 于是我们有 $B_{n+1} \subset B_n, A_{n+1} \subset A_{n}$ , 令 $A_{\omega}=\cap_{n\in \omega}A_n, ~ B_{\omega}=\cap_{n \in \omega}B_n$ 。 定义 $\hat f: A_{\omega} \mapsto B_{\omega}$ , $\hat f(a) =f(a)$ , 即 $\hat f = f|_{A_\omega}$ 。任取 $a \in A_{\omega}$ , 则 $\forall n \in \mathbb N, a \in A_n$ , 所以 $\forall n \in \mathbb N, f(a) \in B_{n+1}$ , 于是 $f(a) \in B_{\omega}$ (1)。反过来，若 $b \in B_{\omega}$ , 则 $\forall n \in \mathbb N, b \in B_{n+1}$ ，则 $\forall n \in \mathbb N, \exists a_n \in A_n, s.t. ~b=f(a_n)$ ; 因为 $f$ 是单射，$\hat f$ 也是单射，所以这边所有的 $a_n, n \in \mathbb N$ 都是一个元素, 不妨记为 $a$ 。那么我们就有 $a \in A_{\omega}$ 且 $b=f(a)$ (2)。根据 (1)、(2) 可知 $\hat f$ 在 满射，所以 $\hat f$ 是双射。 定义 $\hat g: B_{\omega}^C \mapsto A_{\omega}^C$ , $\hat g(b) =g(b)$ , 即 $\hat g = g|_{B_\omega}$ 。 取 $b \notin B_{\omega}$ , 那么我们可以找到某个 $n \in \omega$ , 使得 $b \notin B_{n+1}$ 。根据 $A_{n+1}$ 的定义，我们有 $g(b) \notin A_{n+1}$ ，所以 $g(b) \notin A_{\omega}$ 。反过来，若 $a \notin A_{\omega}$ ，那么我们可以找到某个 $n \in \omega$ ，使得 $a \notin A_{n+1}$ , 因为存在某个 $b \notin B_{n+1}$ , 使得 $g(b) =a$ 。而且，这个 $b$ 是唯一的，且 $b \notin B_{\omega}$ 。这就证明了 $\hat g$ 是双射。 最后，定义 $h(a) = \begin{cases} f(a), a \in A_{\omega} \\ g^{-1}(a), a \notin A \end{cases}$ , 则 $h$ 是一个双射。证毕。 注：值得一提的是上述这个证明并没有用到选择公理。

**Definition 1.50 **定义基数的运算： 1) $\kappa + \lambda = |A \cup B|$ , 其中 $|A|=\kappa, |B|=\lambda, A \cap B = \emptyset$ 2) $\kappa \cdot \lambda = |A \times B|$ ，其中 $|A|=\kappa, |B|=\lambda$ 3) $\kappa^{\lambda}=|A^B|$ ，其中 $|A|=\kappa, |B|=\lambda$ , $A^B := \{f~ |~ f: B \mapsto A\}$

> 例：若 $|A|=|A'|, |B|=|B'|$ ，那么 $|A\times B|=|A' \times B'|$

**Lemma 1.51 **若 $|A|=\kappa$ ，则 $|\mathcal P(A)|=2^{\kappa}$

> 证： $\forall X \subset A$ ，定义 $\chi_X(x) = \begin{cases} 1, x \in X, \\ 0, x \in A-X \end{cases}$ ，映射 $f:X\mapsto \chi_X$ 是 $\mathcal P(A)$ 跟 $\{0,1\}^A$ 之间的一一对应，再根据 Definition 1.50 3) 就证明了。

**Lemma 1.52 **一些更多的基数运算法则： 1) 基数的加法跟乘法满足结合律、交换律、分配律 2) $(\kappa \cdot \lambda)^{\mu} =\kappa^{\mu} \cdot \kappa^{\mu}$ 3) $\kappa^{\lambda + \mu} = k^{\lambda} \cdot \kappa^{\mu}$ 4) $(\kappa^{\lambda})^{\mu}=\kappa^{\lambda \cdot \mu}$ 5) $\kappa \le \lambda \Rightarrow \kappa^{\mu} \le \lambda^{\mu}$ 6) $\kappa^0=1; 1^{\kappa}=1; \kappa \ne 0 \Rightarrow 0^{\kappa}=0$

> 证：略。每个性质的证明都是构造一一映射

**Definition 1.53 **一个序数 $\alpha$ 被称为基数，当且仅当: $\forall \beta < \alpha, |\alpha| \ne |\beta|$ (这里 $|\alpha|$ 指序数 $\alpha$ 作为集合的势)

我们一般用 $\kappa, \lambda, \mu, \ldots$ 表示基数。

若 $W$ 是良序集，那么存在一个序数 $\alpha$ ，使得 $|W|=|\alpha|$ 。所以，我们令 $|W|=$ 使得 $|W|=|\alpha|$ 的最小序数 $\alpha$ (least ordinal)

每一个自然数都是 (有限) 基数；若集合 $S$ 是有限集，则 $|S| =n$ , $n$ 是某个自然数

序数 $\omega$ 是最小的无限基数 (least infinite cardinal)。值得注意的是，所有的无穷基数 (infinite cardinals) 都是极限序数 (limit ordinals), 我们称那些是基数的无穷序数为 $\aleph$ (alephs)。

**Lemma 1.54 **(1) 任取基数 $\alpha$ , 都有存在基数 $\beta$ , 使得 $\alpha < \beta$ ; (2) 若 $X$ 是由基数组成的集合，那么 $\sup X$ 也是一个基数

> 证：略

利用 Lemma 1.54, 我们可以递增的关系 ( $\alpha < \beta$ )，一一枚举出所有的 alephs。我们一般用 $\aleph_{\alpha}$ 表示基数，而用 $\omega_{\alpha}$ 表示其序的类型： $\aleph_0=\omega_0=\omega, ~\aleph_{\alpha+1}=\omega_{\alpha+1}=\aleph_{\alpha}^+$ $\aleph_{\alpha}=\omega_{\alpha}=\sup\{\omega_{\beta}: ~\beta < \alpha\}$ , 其中 $\alpha$ 是一个极限序数

称基数 $\aleph_{\alpha+1}$ 为后继基数 (successor cardinal)；若一个基数的小标是一个极限序数，则称它为极限基数 (limit cardinal)
