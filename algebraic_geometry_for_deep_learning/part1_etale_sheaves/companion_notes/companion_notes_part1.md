# Companion Notes to *Buildings in the Desert — Part 1*

## Mathematical Precision and Pedagogical Simplification

### A Technical Supplement at the Graduate Textbook Level

---

**Author:** Étale Cohomology  
**Version:** 1.0 (April 2026)  
**License:** CC BY 4.0  
**Companion to:** [*Buildings in the Desert — Part 1*](https://zenn.dev/etalecohomology/articles/e65f08b5ba899e) (originally published on Zenn, 15 March 2026)  
**Repository:** [ai-math-notes/buildings_in_the_desert](https://github.com/EtaleCohomology/ai-math-notes)

---

## Preface

The article *Buildings in the Desert — Part 1: Étale Sheaves, Category Theory, and Sheaf Neural Networks* was originally published on Zenn on 15 March 2026. Its purpose is pedagogical: to convey to AI engineers and researchers the conceptual landscape of scheme theory, the étale topology, and sheaves, so that they may approach the contemporary literature on Sheaf Neural Networks, Categorical Deep Learning, and Singular Learning Theory with confidence.

Pedagogical writing, however, operates under constraints that differ from those of research mathematics. A metaphor is not a proof. A simplified statement is not a theorem. When the central didactic device is a landscape of "buildings in the desert," visited by "elevators" and overseen by a "sky castle," one necessarily sacrifices precision for vividness.

This supplementary volume is the author's own response to that sacrifice. It identifies those passages of Part 1 where pedagogical simplification departs, subtly or substantially, from the precise mathematical formulation; it explains, at a level of detail suitable for advanced undergraduate and graduate readers, what the precise statement ought to be; it offers revised wording; and it supplies the proofs, examples, and counterexamples that the original article chose to suppress.

The present document is thus neither an erratum in the narrow sense — Part 1 remains, in the author's judgment, a legitimate piece of expository writing — nor a repudiation. It is an accompaniment. Readers who seek only the conceptual picture may read Part 1 alone. Readers who wish to pass from the metaphor to the mathematics are invited to read Part 1 and the present document in tandem.

The structure of the notes mirrors the structure of a graduate-level textbook. Each refinement is presented as a self-contained section, with a statement of the original passage, a precise formulation of the mathematical issue, a revised statement, and a detailed discussion. Theorems and propositions are numbered in the style of Bourbaki; remarks are set apart for clarity; exercises are collected in an appendix.

The author takes this opportunity to acknowledge that the decision to write such a supplement reflects a particular conception of intellectual honesty. It would have been easier, and in many respects more professional by the standards of contemporary technical blogging, to simply revise the original article silently and redeploy. The decision to instead preserve Part 1 and publish an accompanying technical supplement is a deliberate gesture toward the tradition of *errata corrige* in mathematical publishing, a tradition that dates at least to the eighteenth century and that regards the progressive refinement of written work as a collaborative undertaking between author and reader.

Readers who detect further imprecisions are warmly invited to open an issue on the repository. A second version of these notes will be prepared in due course.

*— The author, April 2026*

---

## Introduction

### The Problem of Pedagogical Fidelity

Pedagogy, in mathematics as elsewhere, is the art of saying less than the truth in order that more of the truth may be understood. No competent teacher presents, on first contact, the full apparatus of definitions and axioms that the mature subject requires. One speaks of the derivative before one speaks of the total derivative; one speaks of the integer before one speaks of the $p$-adic integer; one speaks of the Galois group of a polynomial before one speaks of the absolute Galois group of a field. Each simplification is a deliberate infidelity, justified by the hope that the student will, in time, return to recover what was omitted.

The difficulty is that the infidelities accumulate. By the time the pedagogical narrative has reached its summit — in Part 1, the invocation of sheaves, ℓ-adic cohomology, and the Weil conjectures — the gap between what the reader believes he has understood and what the mathematician actually means has grown considerable. The reader who attempts to pass from Part 1 to the primary literature (to Bodnar et al. 2022, to Gavranović et al. 2024, to Hartshorne or Milne or Deligne) will find that many things he thought he understood were understood only in outline, and that the outline, inspected closely, is wrong in details that matter.

The purpose of these notes is to close that gap. Each chapter below identifies a specific simplification in Part 1, explains precisely how the simplification departs from the rigorous formulation, and supplies the rigorous formulation itself with full mathematical apparatus. The reader emerging from these notes should be equipped to read the primary literature without the embarrassment of rediscovering, mid-paper, that a concept he thought he knew from Part 1 was in fact a pedagogical caricature.

### A Note on Severity

Not all simplifications are equal. Some, if left uncorrected, would mislead the reader in substantive ways; others are merely infelicities of exposition. The present notes classify the refinements into three tiers:

**High-priority refinements** (Chapters 3–5) address issues that would, in the author's judgment, cause material confusion for a reader passing to the primary literature. The most serious of these is the systematic conflation, in Sections 3.3 and 3.5 of Part 1, of two conceptually distinct structures: the choice of a generator of a cyclic multiplicative group, and the action of the Galois group. This confusion, were it to persist in the reader's mind, would make it impossible to follow the arithmetic of cyclotomic fields as presented in any standard text.

**Medium-priority refinements** (Chapters 6–8) address precise definitions that Part 1, for reasons of brevity, stated imprecisely. The definition of an étale morphism is an instance. Part 1 states that étale morphisms are "flat, unramified, and locally of finite presentation"; the definitions of these three conditions that Part 1 offers are, however, paraphrases sufficient for the building metaphor but inadequate for reading Grothendieck's EGA. The refinement here consists of supplying the precise definitions.

**Low-priority refinements** (Chapters 9–10) address matters of rhetoric, emphasis, and historical perspective. Part 1, in its opening pages, describes "200-year-old algebraic geometry" as the source of the tools now entering deep learning. This is, strictly, inaccurate: the tools in question are products of the Grothendieck revolution of the 1960s, making them at most sixty years old. Such matters do not affect the mathematical substance of the exposition, but they can affect the reader's sense of intellectual orientation, and so they are addressed here for completeness.

### How to Use This Document

Each refinement follows a consistent structure:

1. **Original Statement.** The passage from Part 1 is reproduced verbatim.

2. **Nature of the Simplification.** The pedagogical purpose of the original phrasing is identified, together with an analysis of what, precisely, the simplification has elided.

3. **Precise Formulation.** The mathematical content is restated with full rigor, including all hypotheses, quantifiers, and exceptional cases.

4. **Discussion.** Proofs, examples, counterexamples, and connections to the broader literature are supplied. Where appropriate, the reader is pointed to standard references (Hartshorne, Milne, Silverman, Lang) for further study.

5. **Revised Passage.** A proposed rewording of the original passage, consistent with the precise formulation, is offered. The reader is free to adopt, adapt, or reject this rewording.

Readers who are preparing to teach from Part 1 will find the revised passages particularly useful: they represent the author's best attempt at a formulation that preserves the pedagogical virtues of the original while avoiding the substantive inaccuracies.

Readers who are preparing to read the primary literature will find the discussions more useful: they supply the mathematical background that Part 1 assumes as known or postpones as out of scope.

Readers who are simply curious about how educational simplification operates in mathematical exposition may read the document as a kind of case study.

---

## Part I: Foundations

### Chapter 1: Scope and Methodology

#### 1.1 What These Notes Are Not

Before stating what the present notes attempt to do, it is worth stating clearly what they do not.

These notes do not constitute a self-contained textbook on algebraic geometry. They presuppose familiarity with the content of Part 1, which itself is pedagogical and not a substitute for standard references. A reader who has not encountered the basic language of schemes, sheaves, or Galois theory before will find these notes difficult; such a reader is advised to consult Hartshorne (1977), Milne (2020), or Vakil (2017) in parallel.

These notes do not constitute a complete catalogue of all conceivable refinements to Part 1. The author has chosen, from among the many small infelicities of the original, those whose correction seems most likely to benefit the reader. An exhaustive treatment is neither possible nor desirable; every pedagogical text contains decisions about emphasis that another author might reasonably have made differently.

These notes do not repudiate Part 1. On the contrary, the author continues to believe that the "buildings in the desert" metaphor is a useful one, and that the four-tier structure (marked by the icons 🏫🎓📐🔬 in the original) succeeds in rendering the landscape of scheme theory accessible to a broad audience. The present notes are offered in the spirit of a companion volume, not a retraction.

#### 1.2 What These Notes Are

The notes are, in essence, a *precise reading* of Part 1. Where the original offers metaphor, the notes offer definition. Where the original offers intuition, the notes offer theorem. Where the original elides an exception, the notes supply it.

The model for this kind of writing is the long tradition, in mathematical publishing, of supplements, addenda, and notes appended to textbooks. Bourbaki's *Éléments de mathématique* contains, in many of its fascicles, historical notes and exercises that form a substantial fraction of the volume. Hartshorne's *Algebraic Geometry* is followed, in practice, by a small library of supplementary texts (Liu, Vakil, Görtz–Wedhorn) that refine, extend, and occasionally correct the original. The present document positions itself modestly within this tradition.

#### 1.3 The Classification of Refinements

As stated in the Introduction, refinements are classified into three tiers. The classification is not mechanical; it reflects the author's judgment as to which simplifications are most likely to mislead.

A refinement is classified as **high-priority** if, in the author's judgment, a reader who accepts the original passage as precise will, with high probability, encounter difficulty when consulting the primary literature. The clearest instance is the confusion, in Part 1, between the generator of a cyclic group and a Galois element; this confusion is so easy to make, and so consequential when carried forward, that it merits extended treatment (Chapters 3, 4, 5).

A refinement is classified as **medium-priority** if the original passage, though imprecise, is unlikely to mislead on most readings, but would mislead a reader consulting a specific type of reference (e.g., Grothendieck's EGA). The definition of an étale morphism falls into this category.

A refinement is classified as **low-priority** if the imprecision affects rhetoric, emphasis, or historical framing rather than mathematical substance. The description of algebraic geometry as "200 years old" is an example. Such refinements are included for completeness but could, in principle, be omitted without affecting the reader's technical understanding.

#### 1.4 A Remark on the Relation to Part 1

Throughout these notes, references to Part 1 are made in the form "§3.3 of Part 1" or similar. The section numbering of Part 1 is taken as authoritative; no renumbering is introduced.

Where a passage from Part 1 is quoted, it is quoted verbatim. Where a revised passage is proposed, it is clearly marked as such. The reader is thus always in a position to compare original and revision, and to form an independent judgment as to whether the revision represents an improvement.

The revised passages are offered not as mandatory corrections but as invitations. A future edition of Part 1 might adopt some or all of the revisions; it might also reject them, preferring the original phrasing for pedagogical reasons. The decision is not the present author's alone.

---

### Chapter 2: Prerequisites and Notation

#### 2.1 Prerequisites

The reader of these notes is assumed to be familiar with:

1. Basic commutative algebra: rings, ideals, localization, tensor products. Atiyah–Macdonald (1969) is the standard reference.

2. Basic Galois theory: field extensions, separability, the fundamental theorem of Galois theory for finite extensions. Lang's *Algebra* (2002), Chapters V–VI, suffices.

3. Basic scheme theory: affine and projective schemes, morphisms, sheaves of modules, the structure sheaf. Hartshorne (1977), Chapter II, or Vakil (2017), Chapters 1–5, suffice.

4. Basic topology: topological spaces, open and closed sets, continuous maps. Any introductory text.

Familiarity with ℓ-adic cohomology, étale sheaves in the derived sense, or the formalism of Grothendieck topologies, would be useful but is not strictly required. Key notions will be defined as they arise.

#### 2.2 Notation

The following notational conventions are used throughout:

- $\mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}$ denote the usual rings of integers, rationals, reals, and complex numbers.

- $\mathbb{F}_p$ denotes the finite field with $p$ elements (where $p$ is prime), namely $\mathbb{Z}/p\mathbb{Z}$.

- $\mathbb{F}_q$ denotes the finite field with $q = p^n$ elements, for $n \geq 1$.

- $\overline{\mathbb{F}}_p = \bigcup_{n \geq 1} \mathbb{F}_{p^n}$ denotes the algebraic closure of $\mathbb{F}_p$.

- $\mu_n = \{\zeta \in \overline{\mathbb{Q}} : \zeta^n = 1\}$ denotes the group of $n$-th roots of unity in an algebraic closure of $\mathbb{Q}$.

- $\zeta_n = e^{2\pi i / n}$ denotes a fixed primitive $n$-th root of unity.

- $\mathbb{Q}(\zeta_n)$ denotes the $n$-th cyclotomic field.

- $(\mathbb{Z}/n\mathbb{Z})^\times$ denotes the group of units of $\mathbb{Z}/n\mathbb{Z}$, of order $\varphi(n)$ (Euler's totient).

- $\mathrm{Gal}(L/K)$ denotes the Galois group of a Galois extension $L/K$.

- $\varphi$ denotes Euler's totient function.

- $\mathrm{Frob}_p$ denotes the Frobenius element at a prime $p$ (in an unramified Galois extension), defined up to conjugacy.

- $\mathrm{Spec}\, A$ denotes the spectrum of a commutative ring $A$, viewed as a scheme.

- $\mathbb{A}^n_k$ and $\mathbb{P}^n_k$ denote affine and projective $n$-space over a field $k$.

- $\mathcal{O}_X$ denotes the structure sheaf of a scheme $X$.

- $\Omega_{Y/X}$ denotes the sheaf of relative Kähler differentials for a morphism $Y \to X$.

- $\kappa(x)$ denotes the residue field at a point $x$ of a scheme.

- $\mathcal{O}_{X,x}$ denotes the local ring at a point $x$.

- $\mathfrak{m}_x$ denotes the maximal ideal of a local ring.

#### 2.3 A Remark on Set-Theoretic Foundations

The present notes, like Part 1, work within the standard ZFC set theory, supplemented by the existence of universes as needed (for example, when speaking of the category of all schemes). The universe convention is tacit and causes no difficulties in the present exposition.

#### 2.4 Conventions on Rings

All rings are assumed commutative and with identity, unless explicitly stated otherwise. A ring homomorphism is assumed to send 1 to 1. The trivial ring (in which $0 = 1$) is allowed as a degenerate case.

---

## Part II: High-Priority Refinements

### Chapter 3: Galois Groups of Cyclotomic Polynomials

This chapter addresses the first and simplest of the high-priority refinements: the description, in Part 1, of the Galois group of the polynomial $x^3 - 1$.

#### 3.1 The Original Statement

In §3.3 of Part 1, the following table appears:

> | Floors | Example equation | Elevator patterns | Galois group |
> |---|---|---|---|
> | 2 | $x^2 = 2$ | Back and forth (swap) | $\mathbb{Z}/2\mathbb{Z}$ (2 operations) |
> | 3 | $x^3 = 1$ | Round-and-round + reverse | $\mathbb{Z}/2\mathbb{Z}$ (fix $x=1$, swap remaining 2) |
> | 4 | $x^4 = 1$ | 1-step rotation, 2-step skip, reverse | $(\mathbb{Z}/4\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$ (2 operations) |
> | 5 | $x^5 = 1$ | 1-step, 2-step, 3-step, 4-step rotations | $(\mathbb{Z}/5\mathbb{Z})^\times \cong \mathbb{Z}/4\mathbb{Z}$ (4 operations) |

Later, in §3.5, the Galois group of $x^3 = 1$ is written as $(\mathbb{Z}/3\mathbb{Z})^\times$ (with two elements, $\sigma_1 = e$ and $\sigma_2 : \zeta_3 \mapsto \zeta_3^2$).

#### 3.2 Nature of the Simplification

Two issues arise.

**First**, the parenthetical description "fix $x = 1$, swap remaining 2" in §3.3 is pedagogically accurate — the Galois group of $x^3 - 1$ over $\mathbb{Q}$ does indeed fix the rational root $x = 1$ and permute the two non-rational roots $\zeta_3, \zeta_3^2$ — but the formulation risks misleading the reader who is trying to understand *which polynomial* has a Galois group of order 2. The full splitting field of $x^3 - 1$ over $\mathbb{Q}$ is $\mathbb{Q}(\zeta_3)$, a quadratic extension; the Galois group of this extension is indeed of order 2. However, a careless reader might believe that the Galois group of order 2 is "the Galois group of $x^3 - 1$ acting on three roots," which is imprecise. The Galois group acts on the set of roots $\{1, \zeta_3, \zeta_3^2\}$, but this action is not effective on the full three-element set because $1 \in \mathbb{Q}$ is fixed by every Galois element; the action factors through an action on $\{\zeta_3, \zeta_3^2\}$, which is faithful.

**Second**, the notation "$\mathbb{Z}/2\mathbb{Z}$" in the row for $x^3 = 1$ is inconsistent with the notation "$(\mathbb{Z}/3\mathbb{Z})^\times$" used in §3.5. Since $(\mathbb{Z}/3\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$, the two descriptions are isomorphic; but the pedagogical force of the notation $(\mathbb{Z}/n\mathbb{Z})^\times$ — namely, its emphasis on the *cyclotomic* origin of the group — is lost in the first version.

#### 3.3 Precise Formulation

We state the relevant facts in full generality.

**Theorem 3.3.1** (Galois group of cyclotomic polynomials over $\mathbb{Q}$). *Let $n \geq 1$ be an integer, and let $\zeta_n$ be a primitive $n$-th root of unity. Then:*

*(i) The minimal polynomial of $\zeta_n$ over $\mathbb{Q}$ is the cyclotomic polynomial*

$$
\Phi_n(x) = \prod_{\substack{1 \leq k \leq n \\ \gcd(k, n) = 1}} (x - \zeta_n^k).
$$

*(ii) The polynomial $\Phi_n$ has degree $\varphi(n)$ and is irreducible over $\mathbb{Q}$.*

*(iii) The extension $\mathbb{Q}(\zeta_n) / \mathbb{Q}$ is Galois, and*

$$
\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q}) \cong (\mathbb{Z}/n\mathbb{Z})^\times.
$$

*The isomorphism is given by $\sigma_k \leftrightarrow k \bmod n$, where $\sigma_k : \zeta_n \mapsto \zeta_n^k$.*

*(iv) The polynomial $x^n - 1$ factors over $\mathbb{Q}$ as*

$$
x^n - 1 = \prod_{d \mid n} \Phi_d(x).
$$

*(v) The splitting field of $x^n - 1$ over $\mathbb{Q}$ equals the splitting field of $\Phi_n$ over $\mathbb{Q}$, namely $\mathbb{Q}(\zeta_n)$.*

*Proof.* For (i)–(iii), see Lang (2002), Chapter VI, §3, Theorem 3.1. The key ingredient is the irreducibility of $\Phi_n$, originally proved by Gauss for prime $n$ and extended by Kronecker and Dedekind to general $n$.

Statement (iv) is an immediate consequence of the factorization

$$
x^n - 1 = \prod_{\zeta^n = 1} (x - \zeta) = \prod_{d \mid n} \prod_{\substack{\zeta^d = 1 \\ \text{ord}(\zeta) = d}} (x - \zeta) = \prod_{d \mid n} \Phi_d(x).
$$

Statement (v) follows because every root of $x^n - 1$ is a power of $\zeta_n$, so the splitting fields agree. $\square$

**Corollary 3.3.2.** *In particular, for $n = 3$:*

$$
\mathrm{Gal}(\mathbb{Q}(\zeta_3)/\mathbb{Q}) \cong (\mathbb{Z}/3\mathbb{Z})^\times = \{1, 2\} \cong \mathbb{Z}/2\mathbb{Z}.
$$

*The non-trivial element $\sigma_2$ sends $\zeta_3 \mapsto \zeta_3^2$; this is complex conjugation on $\mathbb{Q}(\zeta_3) \subset \mathbb{C}$.*

**Remark 3.3.3.** The degree 2 of the extension $\mathbb{Q}(\zeta_3)/\mathbb{Q}$ coincides with the degree of the minimal polynomial of $\zeta_3$, namely $\Phi_3(x) = x^2 + x + 1$. It is this minimal polynomial, rather than $x^3 - 1$ itself, that has Galois group $\mathbb{Z}/2\mathbb{Z}$ over $\mathbb{Q}$.

**Remark 3.3.4.** The Galois group of the splitting field of $x^3 - 1$ over $\mathbb{Q}$ acts on the three roots $\{1, \zeta_3, \zeta_3^2\}$, fixing $1$ (which lies in $\mathbb{Q}$) and permuting $\zeta_3, \zeta_3^2$. The induced action on the set $\{\zeta_3, \zeta_3^2\}$ is faithful; the action on the full set $\{1, \zeta_3, \zeta_3^2\}$ is therefore also faithful, though with a fixed point.

#### 3.4 Discussion

The phenomenon observed for $x^3 - 1$ generalizes. For any $n$, the polynomial $x^n - 1$ factors over $\mathbb{Q}$ as a product of cyclotomic polynomials $\Phi_d$ for $d \mid n$; each $\Phi_d$ is irreducible, with Galois group $(\mathbb{Z}/d\mathbb{Z})^\times$; and the splitting field of $x^n - 1$ is the cyclotomic field $\mathbb{Q}(\zeta_n)$.

The reason this is not immediately apparent in Part 1 is that the pedagogy operates at two distinct levels, which are not always sharply separated:

- At the level of the *equation* $x^n - 1 = 0$, one considers the set of all $n$ roots, namely $\mu_n$.

- At the level of the *Galois group*, one considers the action on roots of the minimal polynomial $\Phi_n$, which has degree $\varphi(n)$.

For $n = 3$: $\mu_3 = \{1, \zeta_3, \zeta_3^2\}$ has 3 elements, but $\Phi_3$ has 2 roots, and the Galois group has order 2. For $n = 4$: $\mu_4 = \{1, i, -1, -i\}$ has 4 elements, but $\Phi_4(x) = x^2 + 1$ has 2 roots, and the Galois group has order 2. For $n = 5$: $\mu_5$ has 5 elements, but $\Phi_5(x) = x^4 + x^3 + x^2 + x + 1$ has 4 roots, and the Galois group has order 4.

**Example 3.4.1** ($n = 6$). The sixth cyclotomic polynomial is $\Phi_6(x) = x^2 - x + 1$, with roots $\zeta_6 = e^{\pi i / 3}$ and $\zeta_6^5 = e^{-\pi i / 3}$. The Galois group $\mathrm{Gal}(\mathbb{Q}(\zeta_6)/\mathbb{Q}) \cong (\mathbb{Z}/6\mathbb{Z})^\times = \{1, 5\}$ has order 2; the non-trivial element sends $\zeta_6 \mapsto \zeta_6^5 = \overline{\zeta_6}$ (complex conjugation).

Although $\mu_6$ has 6 elements $\{1, \zeta_6, \zeta_6^2, \zeta_6^3, \zeta_6^4, \zeta_6^5\}$, the Galois group acts through its action on the two primitive roots $\zeta_6, \zeta_6^5$; the other four roots are fixed or permuted among themselves by the subgroups of smaller cyclotomic subfields.

**Example 3.4.2** ($n = 8$). $\Phi_8(x) = x^4 + 1$, with four roots $\zeta_8, \zeta_8^3, \zeta_8^5, \zeta_8^7$. The Galois group $(\mathbb{Z}/8\mathbb{Z})^\times = \{1, 3, 5, 7\}$ is isomorphic to $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$, the Klein four-group. This is the first example, in the cyclotomic hierarchy, of a non-cyclic Galois group.

#### 3.5 Revised Passage

The author proposes the following revised version of the table in §3.3 of Part 1:

> | Equation | Splitting field over $\mathbb{Q}$ | Galois group | Order |
> |---|---|---|---|
> | $x^2 - 2 = 0$ | $\mathbb{Q}(\sqrt{2})$ | $\mathbb{Z}/2\mathbb{Z}$ | 2 |
> | $\Phi_3(x) = 0$ | $\mathbb{Q}(\zeta_3)$ | $(\mathbb{Z}/3\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$ | 2 |
> | $\Phi_4(x) = 0$ | $\mathbb{Q}(\zeta_4) = \mathbb{Q}(i)$ | $(\mathbb{Z}/4\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$ | 2 |
> | $\Phi_5(x) = 0$ | $\mathbb{Q}(\zeta_5)$ | $(\mathbb{Z}/5\mathbb{Z})^\times \cong \mathbb{Z}/4\mathbb{Z}$ | 4 |
> | $\Phi_6(x) = 0$ | $\mathbb{Q}(\zeta_6)$ | $(\mathbb{Z}/6\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$ | 2 |
> | $\Phi_7(x) = 0$ | $\mathbb{Q}(\zeta_7)$ | $(\mathbb{Z}/7\mathbb{Z})^\times \cong \mathbb{Z}/6\mathbb{Z}$ | 6 |

With an accompanying remark:

> *Remark: The polynomial $x^n - 1$ factors over $\mathbb{Q}$ as a product of cyclotomic polynomials $\Phi_d(x)$ for each divisor $d$ of $n$. The "essential" Galois content lies in the Galois group of $\Phi_n$, which is $(\mathbb{Z}/n\mathbb{Z})^\times$. The other factors contribute to the action only through the smaller subfields they generate.*

The pedagogical image of "elevator movements" and "rotating floors" remains valid for the non-trivial cyclotomic roots, but is now anchored in the precise fact that the Galois group acts faithfully on the $\varphi(n)$ primitive $n$-th roots, and trivially on the remaining non-primitive ones.

### Chapter 4: Multiplicative Group Generators versus Galois Action

This chapter addresses what the present author regards as the most consequential simplification in Part 1: the systematic conflation, in §§3.3 and 3.5, of two structurally distinct operations. The first is the *choice of a generator* of a cyclic multiplicative group (for example, the group $\mu_n$ of $n$-th roots of unity, viewed as a subgroup of $\overline{\mathbb{Q}}^\times$). The second is the *Galois action* on that group, viewed as a quotient of the absolute Galois group of the base field. The two are related, but they are not identical; indeed, a central aim of elementary algebraic number theory is to keep them distinct.

#### 4.1 The Original Statement

Two passages from Part 1 are relevant.

The first, from §3.3, describes the "elevator movements" for the equation $x^4 = 1$ inside the finite field $\mathbb{F}_{17}$:

> Elevator A (rotate by 1): $1 \to 4 \to 16 \to 13 \to 1$
>
> Elevator B (skip by 2): $1 \to 16 \to 1,\ 4 \to 13 \to 4$
>
> Elevator C (reverse rotate by 3): $1 \to 13 \to 16 \to 4 \to 1$

The second, also from §3.3, gives the analogous description for $x^5 = 1$ inside $\mathbb{F}_{11}$:

> Rotate by 1: $1 \to 3 \to 9 \to 5 \to 4 \to 1$
>
> Rotate by 2 (skip): $1 \to 9 \to 4 \to 3 \to 5 \to 1$
>
> Rotate by 3 (= reverse of 2)
>
> Rotate by 4 (= reverse of 1)

The pedagogical intent is clear. The author of Part 1 wishes to convey, at the high-school level (🏫), the sense that "as the number of roots grows, the variety of permutations among them grows correspondingly." The mental picture is that of an elevator that can travel between floors in several distinguishable patterns.

The difficulty is that the listed "elevator movements" are not, strictly speaking, elements of the Galois group. They are, rather, choices of generator for the cyclic group $\mu_n$ of $n$-th roots of unity, viewed inside the multiplicative group $\mathbb{F}_p^\times$ of a suitable finite field. This distinction requires explanation.

#### 4.2 Nature of the Simplification

Consider $n = 5$ and the prime $p = 11$. The group $\mu_5 \subset \overline{\mathbb{F}}_{11}^\times$ of fifth roots of unity, modulo 11, consists of the elements $\{1, 3, 4, 5, 9\}$, which together form a cyclic subgroup of $\mathbb{F}_{11}^\times$ of order 5.

The element $3 \in \mathbb{F}_{11}^\times$ is a *generator* of this cyclic subgroup: successive powers yield

$$
3^0 = 1,\quad 3^1 = 3,\quad 3^2 = 9,\quad 3^3 = 27 \equiv 5,\quad 3^4 = 81 \equiv 4,\quad 3^5 \equiv 1.
$$

Equally valid generators are $9, 5, 4$ (the elements $3^2, 3^3, 3^4$ respectively); all four are generators because $\gcd(k, 5) = 1$ for $k = 1, 2, 3, 4$. The only non-generator is $1 = 3^0$, which generates the trivial subgroup.

The "elevator by $k$-step rotation" described in Part 1 corresponds to multiplication by $3^k$ within $\mathbb{F}_{11}^\times$. The map $x \mapsto 3^k \cdot x$ is, for each $k$, a bijection of $\mu_5$ onto itself; and the four distinguishable bijections arising for $k = 1, 2, 3, 4$ are indeed all the bijections of $\mu_5$ that preserve the multiplicative structure of this cyclic group. In the language of group theory, $\mathrm{Aut}(\mu_5) \cong (\mathbb{Z}/5\mathbb{Z})^\times$, a group of order 4.

So far there is no error. The error enters when one identifies these four automorphisms of $\mu_5$ with four elements of the Galois group.

#### 4.3 The Precise Distinction

Let us state the matter with full rigor.

**Setup.** Fix a prime $n$ (for expository simplicity; the composite case is similar but notationally more cumbersome). Let $\zeta_n \in \overline{\mathbb{Q}}$ be a primitive $n$-th root of unity, and let $\mu_n = \langle \zeta_n \rangle$ be the group of $n$-th roots of unity. As abstract groups, $\mu_n \cong \mathbb{Z}/n\mathbb{Z}$.

Two distinct structures present themselves:

**Structure A: Automorphisms of the abstract group $\mu_n$.** These are the group homomorphisms $\phi : \mu_n \to \mu_n$ that are bijective. Every such $\phi$ is determined by its value on a generator; if $\phi(\zeta_n) = \zeta_n^k$, then $\phi$ is an automorphism if and only if $\gcd(k, n) = 1$. We obtain

$$
\mathrm{Aut}(\mu_n) \cong (\mathbb{Z}/n\mathbb{Z})^\times.
$$

This isomorphism exists purely at the level of abstract group theory: it does not involve $\mathbb{Q}$, does not involve $\mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$, and does not involve any notion of a field extension.

**Structure B: The Galois action on $\mu_n$.** Consider the cyclotomic extension $\mathbb{Q}(\zeta_n) / \mathbb{Q}$. Its Galois group is $\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$; by Theorem 3.3.1, this group is isomorphic to $(\mathbb{Z}/n\mathbb{Z})^\times$, via the map $\sigma_k \leftrightarrow k$, where $\sigma_k$ is the unique automorphism of $\mathbb{Q}(\zeta_n)$ fixing $\mathbb{Q}$ and sending $\zeta_n \mapsto \zeta_n^k$.

The Galois action restricts to an action of $\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$ on $\mu_n$: the element $\sigma_k$ acts by $\zeta_n^j \mapsto \zeta_n^{kj}$. This action *coincides* with the abstract automorphism of Structure A corresponding to multiplication by $k$. In fact, this is the content of the classical theorem that the cyclotomic character

$$
\chi : \mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q}) \to \mathrm{Aut}(\mu_n) \cong (\mathbb{Z}/n\mathbb{Z})^\times
$$

is an isomorphism.

**So where is the confusion?** The confusion arises when one reads the "elevator movements" in Part 1 and assumes that each listed rotation is a Galois element. This is true only if one has fixed a specific identification of $\mu_n$ with the cyclic subgroup of $\mathbb{F}_p^\times$ generated by a chosen element. Changing the chosen generator of $\mu_n$ (passing from $\zeta_n$ to, say, $\zeta_n^2$) does not produce a new Galois element; it produces a relabeling of the same Galois element.

#### 4.4 A Worked Example

Let us work through the case $n = 5$, $p = 11$ in detail.

Within $\mathbb{F}_{11}^\times = \langle 2 \rangle$ (a cyclic group of order 10), the subgroup of fifth roots of unity is

$$
\mu_5 = \{1, 3, 4, 5, 9\} \subset \mathbb{F}_{11}^\times.
$$

Indeed, $2^2 = 4$ generates $\mu_5$ as a cyclic subgroup of order 5: $4, 4^2 = 16 \equiv 5, 4^3 \equiv 9, 4^4 \equiv 3, 4^5 \equiv 1$.

Alternatively, $3 \in \mathbb{F}_{11}^\times$ also generates $\mu_5$: $3, 9, 5, 4, 1$. Or $5$: $5, 3, 4, 9, 1$. Or $9$: $9, 4, 3, 5, 1$.

**Question.** Does the generator $4$ of $\mu_5$ correspond to $\zeta_5 \in \mathbb{Q}(\zeta_5)$? Or does $3$? Or $9$?

**Answer.** There is *no canonical identification*. The choice of generator of $\mu_5 \subset \mathbb{F}_{11}^\times$ is a choice; different choices lead to different labelings; and no choice is privileged over another.

To pick one: suppose we identify $\zeta_5 \leftrightarrow 3 \in \mathbb{F}_{11}$. Then:

- $\zeta_5^1 = 3$
- $\zeta_5^2 = 9$
- $\zeta_5^3 = 5$ (since $\zeta_5^3 = (\zeta_5^2)^2 / \zeta_5 = 9^2 / 3 = 81 / 3 \equiv 4 / 3 \equiv 4 \cdot 4 = 16 \equiv 5$, or more directly $3^3 = 27 \equiv 5$)
- $\zeta_5^4 = 4$
- $\zeta_5^5 = 1$

Under this identification, the Galois element $\sigma_2 \in \mathrm{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q})$, which sends $\zeta_5 \mapsto \zeta_5^2$, corresponds in $\mathbb{F}_{11}$ to the map $3 \mapsto 9$, or more generally $x \mapsto x^2$ restricted to $\mu_5$. The image of $\mu_5 = \{1, 3, 4, 5, 9\}$ under squaring is $\{1, 9, 5, 3, 4\}$, i.e., $\mu_5$ is preserved, with the permutation

$$
1 \mapsto 1,\quad 3 \mapsto 9,\quad 9 \mapsto 4,\quad 4 \mapsto 5,\quad 5 \mapsto 3.
$$

In cycle notation, this is the 4-cycle $(3, 9, 4, 5)$ fixing $1$.

Similarly, $\sigma_3$ sends $\zeta_5 \mapsto \zeta_5^3$, which in $\mathbb{F}_{11}$ corresponds to the cubing map $x \mapsto x^3$. And $\sigma_4$ corresponds to $x \mapsto x^4 = x^{-1}$ on $\mu_5$, which is the inversion map.

The Galois group $\mathrm{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q}) \cong (\mathbb{Z}/5\mathbb{Z})^\times = \{1, 2, 3, 4\}$ has *four* elements, which act on $\mu_5 \subset \mathbb{F}_{11}^\times$ as follows:

- $\sigma_1$: identity
- $\sigma_2$: $x \mapsto x^2$ (Frobenius-like squaring)
- $\sigma_3$: $x \mapsto x^3$
- $\sigma_4$: $x \mapsto x^4 = x^{-1}$ (inversion)

**Comparison with the "elevator movements" in Part 1.** Part 1 lists four "rotations" for $x^5 = 1$ in $\mathbb{F}_{11}$:

| Rotation | Part 1 description | In $\mathbb{F}_{11}$ | As automorphism of $\mu_5$ |
|---|---|---|---|
| by 1 | $1 \to 3 \to 9 \to 5 \to 4 \to 1$ | $x \mapsto 3x$ | not a homomorphism |
| by 2 | $1 \to 9 \to 4 \to 3 \to 5 \to 1$ | $x \mapsto 9x$ | not a homomorphism |
| by 3 | (reverse of 2) | $x \mapsto 5x$ | not a homomorphism |
| by 4 | (reverse of 1) | $x \mapsto 4x$ | not a homomorphism |

The maps listed in Part 1 are *translations* (multiplication by a constant) within the cyclic group $\mu_5$. A translation is not a group homomorphism unless the constant is 1 (the identity). So the four "rotations" of Part 1 are not automorphisms of $\mu_5$ as an abstract group; they are the four distinct choices of *generator*, identified via the map "pick the next element after $1$."

The Galois group, by contrast, consists of the four *automorphisms* of $\mu_5$ (as a group), namely the maps $x \mapsto x^k$ for $k = 1, 2, 3, 4$.

These are two different — though related — structures, and Part 1 does not clearly distinguish them.

#### 4.5 Why This Distinction Matters

The distinction is not merely pedantic. It matters for three concrete reasons.

**First**, when the reader passes to the primary literature on arithmetic geometry, he will encounter the Galois group as a permutation of roots. The elements of the Galois group will be described as $\sigma : \zeta_n \mapsto \zeta_n^k$, and the group structure will be composition. The reader who has internalized Part 1's "rotation by $k$" will attempt to compose two such rotations and obtain nonsense, because translations do not compose the way automorphisms do.

Specifically: the composition of "rotation by 1" and "rotation by 2" (as translations) sends $x \mapsto 3(9x) = 27x \equiv 5x$, which is "rotation by 3" in Part 1's notation — a coincidence arising from the cyclic group structure of $\mathbb{F}_{11}^\times$. But this is *not* the composition law of the Galois group. The composition of $\sigma_2$ and $\sigma_3$ in $\mathrm{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q})$ gives $\sigma_2 \circ \sigma_3 = \sigma_6 = \sigma_1$ (since $6 \equiv 1 \pmod 5$), i.e., the identity. By contrast, the composition of "rotation by 2" and "rotation by 3" as translations gives "rotation by 5" ≡ "rotation by 0," also the identity — but for a different reason (multiplication by 6 in the full multiplicative group).

The answers agree here, but that is a coincidence of the small example. In the general case, the two operations do not agree.

**Second**, the distinction is critical for the Sheaf Neural Network (SNN) framework that Part 1 introduces. In SNNs à la Bodnar et al. (2022), the "restriction maps" along edges are elements of $\mathrm{GL}(d, \mathbb{R})$ or (in the symmetric version of Hansen–Ghrist) $O(d)$; they are homomorphism-like objects, composed along paths. If one thinks of them as translations rather than homomorphisms, the mathematical framework degenerates.

**Third**, the distinction matters for the historical narrative Part 1 invokes. The Galois representation

$$
\rho_n : \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q}) \to \mathrm{Aut}(\mu_n) \cong (\mathbb{Z}/n\mathbb{Z})^\times
$$

is the prototype of all Galois representations, and its generalizations (to elliptic curves, to modular forms, to motives) are the content of much of modern arithmetic geometry. The entire edifice rests on Structure B (Galois action), not Structure A (choice of generator). Conflating the two elides the content of the edifice.

#### 4.6 The Case of $n = 4$

The case $n = 4$ is worth a separate worked example because the simplification in Part 1 is even more striking here.

The group $\mu_4 = \{1, i, -1, -i\} \subset \mathbb{Q}(i)$ has order 4. Its automorphism group is

$$
\mathrm{Aut}(\mu_4) \cong (\mathbb{Z}/4\mathbb{Z})^\times = \{1, 3\},
$$

a group of order 2 (not 4). The automorphism corresponding to $k = 3$ is $\zeta_4 \mapsto \zeta_4^3 = \zeta_4^{-1}$, i.e., complex conjugation.

The Galois group $\mathrm{Gal}(\mathbb{Q}(i)/\mathbb{Q})$ also has order 2, generated by complex conjugation.

Part 1, by contrast, lists three distinct "elevator movements" for $\mu_4$ in $\mathbb{F}_{17}$:

- Rotate by 1
- Skip by 2
- Reverse rotate by 3

Three is not two. The reader who attempts to match these three movements against the two-element Galois group will become confused.

The resolution: among the three listed "rotations," the "skip by 2" is actually *not a generator* of $\mu_4$. Multiplication by $\zeta_4^2 = -1$ sends $1 \mapsto -1, -1 \mapsto 1, i \mapsto -i, -i \mapsto i$, which is the automorphism $\zeta_4 \mapsto \zeta_4^{-1}$ (complex conjugation), corresponding to $k = 3$ under the identification $\mu_4 \cong \langle \zeta_4 \rangle$. Wait — this is not correct either. Let us be careful.

The map "multiply by $-1$" on $\mu_4$ sends $\zeta_4 \mapsto -\zeta_4 = \zeta_4^3$, $\zeta_4^2 \mapsto -\zeta_4^2 = \zeta_4^4 = \zeta_4^0 = 1$... but wait, that's not right either. Let me recompute.

$\mu_4 = \{\zeta_4^0, \zeta_4^1, \zeta_4^2, \zeta_4^3\} = \{1, i, -1, -i\}$. Multiplication by $-1 = \zeta_4^2$ sends $\zeta_4^k \mapsto \zeta_4^{k+2}$. So:

- $\zeta_4^0 = 1 \mapsto \zeta_4^2 = -1$
- $\zeta_4^1 = i \mapsto \zeta_4^3 = -i$
- $\zeta_4^2 = -1 \mapsto \zeta_4^4 = 1$
- $\zeta_4^3 = -i \mapsto \zeta_4^5 = i$

This is *not* an automorphism of $\mu_4$ as a group, because it sends $1$ to $-1 \neq 1$. It is a translation by $\zeta_4^2 = -1$, which is a group element, but translation by a non-identity element is never a homomorphism.

So "skip by 2" in Part 1, interpreted as multiplication by $\zeta_4^2$ on $\mu_4$, is a translation, not an automorphism; it is not a Galois element.

The actual automorphisms of $\mu_4$ are the maps $\zeta_4 \mapsto \zeta_4^k$ for $k \in (\mathbb{Z}/4\mathbb{Z})^\times = \{1, 3\}$:

- $k = 1$: identity
- $k = 3$: $\zeta_4 \mapsto \zeta_4^3 = -i$, and by extension, $i \mapsto -i$, $-1 \mapsto -1$ (since $(-1)^3 = -1$), $-i \mapsto i$

The second map has a fixed point at $\pm 1$ and swaps $\pm i$; in cycle notation on $\mu_4$, it is the 2-cycle $(i, -i)$.

**Summary for $n = 4$.** The Galois group $\mathrm{Gal}(\mathbb{Q}(i)/\mathbb{Q})$ has 2 elements, corresponding to the identity and complex conjugation. Part 1's description of 3 or more "elevator movements" (rotation by 1, skip by 2, reverse rotate by 3) overcounts, because some of the listed movements are translations rather than automorphisms.

#### 4.7 Precise Formulation: The General Theorem

We now state the precise theorem that Part 1's pedagogical description attempts to approximate.

**Theorem 4.7.1.** *Let $n \geq 1$, $\zeta_n$ a primitive $n$-th root of unity, $\mu_n = \langle \zeta_n \rangle$. Let $p$ be a prime not dividing $n$, and let $q$ be the smallest positive integer such that $p^q \equiv 1 \pmod n$. Then:*

*(i) The polynomial $\Phi_n(x) \in \mathbb{F}_p[x]$ factors as a product of irreducible factors, each of degree $q$.*

*(ii) The residue field of the prime ideal above $p$ in $\mathbb{Z}[\zeta_n]$ is $\mathbb{F}_{p^q}$.*

*(iii) The Frobenius element $\mathrm{Frob}_p \in \mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q}) \cong (\mathbb{Z}/n\mathbb{Z})^\times$ corresponds to $p \bmod n$.*

*(iv) The orbits of the Frobenius action on $\mu_n$ (viewed in an algebraic closure of $\mathbb{F}_p$) are of length $q$, with $\varphi(n)/q$ orbits among the primitive roots.*

*(v) In particular, if $p \equiv 1 \pmod n$ (i.e., $q = 1$), then $\Phi_n$ splits completely mod $p$, every root of $\mu_n$ lies in $\mathbb{F}_p$, and the Frobenius acts trivially on $\mu_n$.*

*Proof.* See Neukirch (1999), Chapter I, §8, or Washington (1997), Chapter 2. The key ingredient is the correspondence between prime ideals of $\mathbb{Z}[\zeta_n]$ above $p$ and Frobenius conjugacy classes in $\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$. $\square$

**Corollary 4.7.2.** *For $n = 5$ and $p = 11$: since $11 \equiv 1 \pmod 5$, $\Phi_5$ splits completely mod 11, $\mu_5 \subset \mathbb{F}_{11}^\times$, and the Galois action is trivial on $\mu_5 \cap \mathbb{F}_{11}$. (The non-trivial Galois action appears when one lifts to characteristic 0.)*

**Corollary 4.7.3.** *For $n = 4$ and $p = 17$: since $17 \equiv 1 \pmod 4$, $\Phi_4$ splits completely mod 17, $\mu_4 \subset \mathbb{F}_{17}^\times$, and analogously the Galois action is trivial on $\mu_4 \cap \mathbb{F}_{17}$.*

#### 4.8 Revised Passage

The author proposes replacing the problematic passages of §3.3 with the following revised text. Changes are indicated in boldface.

> For the equation $x^5 = 1$, the group of solutions is the cyclic group $\mu_5$ of fifth roots of unity. Over $\mathbb{Q}$, this group is generated by $\zeta_5 = e^{2\pi i/5}$, and the Galois group $\mathrm{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q}) \cong (\mathbb{Z}/5\mathbb{Z})^\times$ has **four elements, acting by $\sigma_k : \zeta_5 \mapsto \zeta_5^k$ for $k = 1, 2, 3, 4$.**
>
> **These four elements are automorphisms of the cyclic group $\mu_5$:** raising every element to the $k$-th power is a homomorphism $\mu_5 \to \mu_5$, bijective precisely when $\gcd(k, 5) = 1$.
>
> Over the finite field $\mathbb{F}_{11}$, the group $\mu_5$ embeds as the subgroup $\{1, 3, 4, 5, 9\}$ of $\mathbb{F}_{11}^\times$. **The Galois action, transferred to $\mathbb{F}_{11}$, is given by the Frobenius-like automorphism $x \mapsto x^k$ for $k = 1, 2, 3, 4$.** For example, $\sigma_2$ acts on $\mu_5 \cap \mathbb{F}_{11}$ by $x \mapsto x^2$, sending $3 \mapsto 9, 9 \mapsto 4, 4 \mapsto 5, 5 \mapsto 3$, i.e., the 4-cycle $(3, 9, 4, 5)$ with $1$ fixed.
>
> **(Pedagogical note for the 🏫-level reader: The images of an elevator "rotating by $k$ steps" among the five floors should be understood as this raising-to-the-$k$-th-power operation, not as a translation that slides each floor to its $k$-th neighbor.)**

A similar rewrite applies to the $n = 4$ passage, with the additional note that the case $n = 4$ has a Galois group of order 2, not 3 or 4; "skip by 2" is a translation (not a Galois element) and should not appear in the list of elevator movements.

#### 4.9 Summary

The confusion between generator-choice and Galois action is the single most consequential simplification in Part 1. Its correction requires distinguishing:

- *Choices of generator* of a cyclic group $\mu_n$: there are $\varphi(n)$ such choices, corresponding to primitive $n$-th roots.
- *Automorphisms* of the cyclic group $\mu_n$: there are $\varphi(n)$ such automorphisms, corresponding to maps $x \mapsto x^k$ with $\gcd(k, n) = 1$.
- *Galois elements* of $\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$: there are $\varphi(n)$ such elements; they act on $\mu_n$ as automorphisms, and the correspondence is $\sigma_k \leftrightarrow x \mapsto x^k$.
- *Translations* in $\mathbb{F}_p^\times$ restricted to $\mu_n$: these are maps $x \mapsto cx$ for $c \in \mu_n$. They are permutations of $\mu_n$, but not homomorphisms (except for $c = 1$); they are not Galois elements.

Part 1's "elevator movements," listed as "rotation by $k$ steps," are translations of the third kind — not Galois elements. The revised passage reassigns the pedagogical image to the correct mathematical operation (Frobenius-like raising to the $k$-th power) while preserving the intuitive appeal.

---

### Chapter 5: Galois Groups as Permutation Groups

This chapter addresses a second high-priority refinement: the general principle that the Galois group of a polynomial $f$ of degree $n$ embeds faithfully as a subgroup of the symmetric group $S_n$. Part 1 implicitly assumes this principle but does not state it; as a result, certain passages (notably the treatment of $x^3 - 2$ with its Galois group $S_3$) can create a misleading impression that the Galois group *is* the full symmetric group, rather than merely being embedded in it.

#### 5.1 The Original Statement

In §3.3 of Part 1, the discussion of "how corridors are connected" appeals to the intuition that the Galois group shuffles the solutions of a polynomial equation. The language used is vivid but imprecise:

> *Rule: "Connect solutions that occupy the same position in the sky castle's elevator."*
>
> The castle's elevator has "Position A" and "Position B" (corresponding to the two solutions).

Later, in §3.3's discussion of $x^3 - 2 = 0$ under the graduate-student level (🔬), Part 1 states:

> The splitting field of this equation is $\mathbb{Q}(\sqrt[3]{2}, \zeta_3)$, and the Galois group is the symmetric group $S_3$ (a non-abelian group of order 6).

This statement is correct. However, an earlier-level reader encountering the phrase "the Galois group is $S_3$" without first encountering the general principle "Galois groups embed into $S_n$" may conclude that $S_n$ *is* the Galois group of every degree-$n$ polynomial. This is false in general.

#### 5.2 Nature of the Simplification

The general principle is the following.

**Theorem 5.2.1** (Galois as permutation group). *Let $f(x) \in K[x]$ be a separable polynomial of degree $n$ with roots $\alpha_1, \dots, \alpha_n$ in a splitting field $L/K$. The Galois group $G = \mathrm{Gal}(L/K)$ acts on the set of roots $\{\alpha_1, \dots, \alpha_n\}$ by permutation. This action induces an embedding*

$$
G \hookrightarrow S_n.
$$

*The embedding is determined up to conjugation by the choice of ordering of the roots. The image is always a transitive subgroup of $S_n$ if and only if $f$ is irreducible.*

*Proof.* The action of $G$ on roots is well-defined because each $\sigma \in G$ permutes the roots of $f$ (every $K$-automorphism sends roots to roots). The action is faithful because $L = K(\alpha_1, \dots, \alpha_n)$, so any $\sigma$ acting trivially on all roots is the identity. This gives the injective homomorphism $G \hookrightarrow S_n$. Transitivity ⟺ irreducibility is standard; see Lang (2002), Chapter VI, §2. $\square$

**Corollary 5.2.2.** *$|G|$ divides $n!$. In particular, $|G| \leq n!$.*

**Remark 5.2.3.** The embedding $G \hookrightarrow S_n$ is generally proper: most polynomials have Galois group strictly smaller than $S_n$. Indeed, for a random polynomial (in a suitable probabilistic sense) over $\mathbb{Q}$, the Galois group is "usually" $S_n$ (by a theorem of van der Waerden), but explicit examples where the Galois group is smaller abound.

**Example 5.2.4.** $x^2 + 1$ has Galois group $\mathbb{Z}/2\mathbb{Z}$ (since $[\mathbb{Q}(i) : \mathbb{Q}] = 2$), which is $S_2$ — the symmetric group on 2 elements.

**Example 5.2.5.** $x^3 - 1$ has Galois group $\mathbb{Z}/2\mathbb{Z}$, which is a proper subgroup of $S_3$ (indeed, index 3). The reason is that $x^3 - 1$ is not irreducible; it factors as $(x - 1)(x^2 + x + 1)$, and the Galois group acts only on the roots of the second factor.

**Example 5.2.6.** $x^3 - 2$ has Galois group $S_3$ itself. The polynomial is irreducible (by Eisenstein's criterion at $p = 2$), so the Galois group acts transitively on the three roots; the group has order $[\mathbb{Q}(\sqrt[3]{2}, \zeta_3) : \mathbb{Q}] = 6 = |S_3|$, so the embedding is surjective.

#### 5.3 Precise Formulation

Let us state the full structure theorem.

**Theorem 5.3.1** (Structure of Galois groups of polynomials). *Let $f \in K[x]$ be a separable polynomial of degree $n$, with splitting field $L/K$ and Galois group $G = \mathrm{Gal}(L/K)$. Then:*

*(i) $G$ embeds as a subgroup of $S_n$.*

*(ii) The image of $G$ in $S_n$ is transitive if and only if $f$ is irreducible over $K$.*

*(iii) If $f = f_1 \cdots f_k$ is the factorization into irreducible factors (over $K$), with $f_i$ of degree $n_i$, then $G$ embeds in $S_{n_1} \times \cdots \times S_{n_k}$, and the image is a subgroup that projects surjectively onto each factor that is the Galois group of $f_i$.*

*(iv) $|G|$ is the degree of the splitting field: $|G| = [L : K]$.*

*(v) $|G|$ divides $n!$ (respectively, $n_1! \cdot n_2! \cdots n_k!$ in the factored case), but is typically much smaller.*

*Proof.* Statements (i), (ii), (iv) are covered in any standard Galois theory text, e.g., Lang (2002), Chapter VI. Statement (iii) follows from (i) and (ii) applied to each factor. Statement (v) follows from (iv) and $[L : K] \leq n!$. $\square$

#### 5.4 Worked Examples

**Example 5.4.1** ($f(x) = x^4 - 10x^2 + 1$). The roots are $\pm\sqrt{2} \pm \sqrt{3}$, and the splitting field is $\mathbb{Q}(\sqrt{2}, \sqrt{3})$. The Galois group is

$$
\mathrm{Gal}(\mathbb{Q}(\sqrt{2}, \sqrt{3})/\mathbb{Q}) \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z},
$$

of order 4. As a subgroup of $S_4$, it is the Klein four-group $V_4 \subset S_4$, consisting of the identity, the two 2+2 cycles $(12)(34)$ and $(13)(24)$, and their product $(14)(23)$. Note that $|V_4| = 4 < |S_4| = 24$.

**Example 5.4.2** ($f(x) = x^4 - 2$). The roots are $\pm\sqrt[4]{2}, \pm i\sqrt[4]{2}$. The splitting field is $\mathbb{Q}(\sqrt[4]{2}, i)$, of degree 8 over $\mathbb{Q}$. The Galois group is the dihedral group $D_4$ of order 8, acting on the four roots by rotation and reflection (viewed as vertices of a square in the complex plane). $D_4 \subset S_4$ has index 3; the embedding is proper.

**Example 5.4.3** ($f(x) = x^5 - 2$). The splitting field is $\mathbb{Q}(\sqrt[5]{2}, \zeta_5)$ of degree 20, and the Galois group is the Frobenius group $F_{20}$ of order 20. As a subgroup of $S_5$, $F_{20}$ is the normalizer of a 5-cycle; it is a transitive solvable subgroup of $S_5$, proper (since $|S_5| = 120$).

**Example 5.4.4** ($f(x) = x^5 - x - 1$). This polynomial is irreducible over $\mathbb{Q}$, and its Galois group is the full symmetric group $S_5$. This is a classical example of a "generic" quintic with non-solvable Galois group.

**Example 5.4.5** ($f(x) = $ "random" polynomial of degree $n$). For a random monic polynomial of degree $n$ with integer coefficients of bounded height, the Galois group is $S_n$ with probability tending to 1 as the height grows. (Theorem of van der Waerden; see Serre, *Lectures on the Mordell–Weil Theorem*, §6.)

#### 5.5 Connection to Chebotarev's Theorem

The embedding $G \hookrightarrow S_n$ is crucial for interpreting the Chebotarev density theorem, which Part 1 invokes in §3.3.

**Theorem 5.5.1** (Chebotarev density, for number fields). *Let $L/\mathbb{Q}$ be a Galois extension with Galois group $G$. For each unramified prime $p$, the Frobenius conjugacy class $[\mathrm{Frob}_p] \subset G$ is well-defined. For any conjugacy class $C \subset G$, the density of primes $p$ with $[\mathrm{Frob}_p] = C$ equals $|C| / |G|$.*

Applied to the splitting field of $f \in \mathbb{Z}[x]$: the factorization type of $f$ modulo $p$ is determined by the cycle type of $\mathrm{Frob}_p$, viewed as a permutation of roots in $S_n$. The density of primes with a given factorization type equals the proportion of $G$ occupied by permutations of that cycle type.

**Example 5.5.2** (from Part 1, §3.3). For $f(x) = x^3 - 2$, $G = S_3$. The conjugacy classes of $S_3$ are:

- identity: 1 element, cycle type $(1, 1, 1)$, density $1/6$
- transpositions: 3 elements, cycle type $(2, 1)$, density $3/6 = 1/2$
- 3-cycles: 2 elements, cycle type $(3)$, density $2/6 = 1/3$

These densities agree with the classical result that half of primes split as $(1)(2)$ (transposition type) and one third are inert as $(3)$ (3-cycle type).

**Remark 5.5.3.** The statement of Chebotarev requires that $L/\mathbb{Q}$ be Galois and that the primes be unramified. The ramified primes (for $x^3 - 2$, these are $p = 2$ and $p = 3$) are excluded from the count; they contribute to the finite set of exceptions. Part 1 does not mention this exception, which is a low-priority imprecision but worth noting for the careful reader.

#### 5.6 Revised Passage

The author proposes inserting a new paragraph, near the beginning of §3.3 of Part 1, establishing the general principle before discussing specific examples:

> **General Principle: The Galois group is a subgroup of $S_n$.** For any polynomial $f(x)$ of degree $n$ with distinct roots, the Galois group of its splitting field acts on the $n$ roots by permutation. This induces an injective homomorphism
>
> $$G = \mathrm{Gal}(L/K) \hookrightarrow S_n$$
>
> where $S_n$ is the symmetric group on $n$ elements. The image of $G$ is a subgroup of $S_n$, generally proper. The order of $G$ divides $n!$ but is typically much smaller.
>
> For $x^2 = 2$, the Galois group is $\mathbb{Z}/2\mathbb{Z} = S_2$ (the full symmetric group).
>
> For $x^3 - 1$, the Galois group is $\mathbb{Z}/2\mathbb{Z} \subset S_3$ (proper subgroup, since the root $1 \in \mathbb{Q}$ is fixed).
>
> For $x^3 - 2$, the Galois group is $S_3$ itself (Exercise: verify).
>
> For $x^4 - 2$, the Galois group is the dihedral group $D_4 \subset S_4$ of order 8.
>
> For a "random" polynomial of degree $n$, the Galois group is $S_n$ with high probability.

This added paragraph would establish, before any specific example, the general framework within which the examples are instances.

#### 5.7 Summary

Chapter 5 has established that:

(i) Every polynomial's Galois group embeds into the symmetric group on its roots.

(ii) The embedding is not generally surjective; the specific subgroup depends on the polynomial.

(iii) For irreducible polynomials, the image is transitive.

(iv) For reducible polynomials, the image lies in a product $S_{n_1} \times \cdots \times S_{n_k}$.

(v) The density-theoretic content of Chebotarev makes use of the $S_n$ embedding: cycle types of Frobenius elements control factorization of primes.

This chapter, together with Chapters 3 and 4, completes the treatment of the high-priority refinements related to Galois theory. Chapters 6–8 turn to medium-priority refinements concerning scheme-theoretic definitions (étale morphisms, finite fields) and the precise statement of Chebotarev.

## Part III: Medium-Priority Refinements

### Chapter 6: Étale Morphisms — Precise Definitions

This chapter addresses one of the more subtle medium-priority refinements: the definition of an étale morphism as presented in §3.2 of Part 1. The pedagogical paraphrase offered there — "flat, unramified, and locally of finite presentation" — is standard textbook language, but the gloss given to each of the three conditions is imprecise in ways that could mislead a reader consulting Grothendieck's *Éléments de Géométrie Algébrique* (EGA) or any of its successors.

#### 6.1 The Original Statement

In §3.2 of Part 1, the following definition appears:

> **Definition (Étale morphism):** A morphism of schemes $f: Y \to X$ is étale if $f$ is simultaneously:
>
> 1. Flat — algebraically, "not collapsed"
> 2. Unramified — "not branching" (the derivative does not vanish)
> 3. Locally of finite presentation — "describable by finitely many equations"
>
> Intuitively, it is "the algebraic version of a local homeomorphism."

A footnote then adds:

> *Note:* Many introductory texts omit condition 3 and define étale as "flat + unramified," but strictly speaking this condition is required. Over Noetherian schemes, it follows automatically from "finite type," which is why it is often omitted.

#### 6.2 Nature of the Simplification

The pedagogical intent is legitimate: one wants to convey, without excessive formalism, the idea that étale morphisms are "the algebraic geometer's local homeomorphisms." Each of the three conditions has a geometric meaning, and Part 1's paraphrases capture something of that meaning.

However, the paraphrases contain inaccuracies that matter for the careful reader:

1. **"Flat — not collapsed"** is vague. Flatness is a precise homological condition, and the intuition "not collapsed" is suggestive but non-operational. A student who attempts to verify flatness by checking "nothing is collapsed" will not arrive at anything.

2. **"Unramified — the derivative does not vanish"** is actually incorrect as stated. The condition "derivative does not vanish" is closer to the condition of being smooth (or étale plus non-vanishing of a determinant), not to unramifiedness. The precise condition of being unramified is that the sheaf of relative differentials $\Omega_{Y/X}$ vanishes.

3. **"Locally of finite presentation — describable by finitely many equations"** is approximately correct but obscures the distinction between "finite type" (finitely many generators) and "finite presentation" (finitely many generators *and* finitely many relations). These coincide over Noetherian rings but diverge in general.

4. The footnote on the Noetherian case is *incorrect*. It states that "over Noetherian schemes, [finite presentation] follows automatically from 'finite type'." The correct statement is:

> *Over Noetherian base schemes, "locally of finite type" implies "locally of finite presentation."*

This is because finitely generated modules over Noetherian rings are finitely presented (by the general fact that submodules of finitely generated modules over Noetherian rings are finitely generated). But this is a theorem that requires Noetherian hypotheses on the *base*, not just the target; and the formulation in Part 1 suggests it follows from finite type on the map, which is not precise.

#### 6.3 Precise Definitions

We proceed to state precise definitions of each of the three conditions, followed by the full definition of étale.

**Definition 6.3.1** (Flat morphism). *Let $f : Y \to X$ be a morphism of schemes. The morphism $f$ is **flat** if for every point $y \in Y$, the local ring $\mathcal{O}_{Y,y}$ is flat as a module over the local ring $\mathcal{O}_{X, f(y)}$ via the induced ring map $\mathcal{O}_{X, f(y)} \to \mathcal{O}_{Y, y}$.*

*Recall: An $A$-module $M$ is **flat** if the functor $- \otimes_A M$ preserves exact sequences. Equivalently, $\mathrm{Tor}^A_1(N, M) = 0$ for all $A$-modules $N$, or equivalently, tensoring with $M$ preserves injectivity.*

**Remark 6.3.2.** The intuition "flat = not collapsed" can be given the following more precise form: if one has a flat family of varieties $f : Y \to X$ parameterized by the base $X$, then the fibers $Y_x = f^{-1}(x)$ "vary continuously" as $x$ varies — they do not jump in dimension or other numerical invariants. This is the content of the semicontinuity theorems (EGA IV, §12) and the dimension theorem for flat morphisms. The fibers of a flat morphism all have the same dimension (locally, and where they exist).

**Definition 6.3.3** (Unramified morphism). *Let $f : Y \to X$ be a morphism of schemes, locally of finite type. The morphism $f$ is **unramified at a point** $y \in Y$ if the following equivalent conditions hold (setting $x = f(y)$):*

*(i) The maximal ideal $\mathfrak{m}_x \mathcal{O}_{Y, y}$ generates the maximal ideal $\mathfrak{m}_y$ of $\mathcal{O}_{Y, y}$, and the residue field extension $\kappa(y) / \kappa(x)$ is finite separable.*

*(ii) The module of relative Kähler differentials $\Omega^1_{Y/X, y}$ is zero.*

*(iii) The diagonal morphism $\Delta : Y \to Y \times_X Y$ is an open immersion near $y$.*

*The morphism $f$ is **unramified** if it is unramified at every point $y \in Y$.*

**Remark 6.3.4.** The equivalence of (i), (ii), (iii) is non-trivial. A proof may be found in EGA IV, §17, or in Milne's *Étale Cohomology* (1980), Chapter I. Condition (i) is the most arithmetic: it corresponds to the classical notion of unramified prime in a number field extension. Condition (ii) is the most geometric: $\Omega^1_{Y/X}$ measures "infinitesimal deformations of $Y$ over $X$," and its vanishing means there are no such deformations. Condition (iii) is the most categorical: the diagonal being open means that $Y \to X$ is "monomorphism-like on an étale neighborhood."

**Remark 6.3.5** (Correction to Part 1's "derivative does not vanish"). The condition "the derivative does not vanish" is, strictly, not the definition of unramifiedness. What is true is the following: for a smooth morphism $f : Y \to X$ of relative dimension 0, $f$ is étale, and at each point $y$ the fiber is a finite separable extension of the residue field at $f(y)$; in the affine case $Y = \mathrm{Spec}(A[x]/(g))$ over $X = \mathrm{Spec}(A)$, the morphism is étale at a prime $\mathfrak{q}$ if and only if $g'(x)$ is a unit in $A[x]/(g)$ localized at $\mathfrak{q}$, where $g'$ is the formal derivative of $g$. The "derivative does not vanish" is thus a correct diagnostic *in a specific class of examples* (one variable over an affine base), but not a general definition.

**Definition 6.3.6** (Locally of finite presentation). *A morphism $f : Y \to X$ is **locally of finite presentation** if for every affine open $\mathrm{Spec}(A) = V \subset X$ and every affine open $\mathrm{Spec}(B) = U \subset Y$ with $f(U) \subset V$, the ring $B$ is an $A$-algebra of finite presentation, i.e., $B \cong A[T_1, \dots, T_n] / (f_1, \dots, f_m)$ for some $n, m \geq 0$ and polynomials $f_j$.*

*Finite type requires only finitely many generators: $B \cong A[T_1, \dots, T_n] / I$ for some ideal $I$. Finite presentation requires, additionally, that $I$ be finitely generated.*

**Proposition 6.3.7** (Noetherian coincidence). *If $X$ is locally Noetherian, then $f : Y \to X$ is locally of finite type if and only if $f$ is locally of finite presentation.*

*Proof.* One direction is immediate (finite presentation ⟹ finite type). For the converse, if $X$ is locally Noetherian and $f$ is locally of finite type, then for each affine open $\mathrm{Spec}(A) \subset X$ the ring $A$ is Noetherian, and for each affine open $\mathrm{Spec}(B) \subset Y$ lying over it, $B = A[T_1, \dots, T_n] / I$ for some ideal $I$. Since $A$ is Noetherian, $A[T_1, \dots, T_n]$ is Noetherian (Hilbert basis theorem), so every ideal is finitely generated. In particular, $I$ is finitely generated, so $B$ is of finite presentation over $A$. $\square$

**Remark 6.3.8.** The hypothesis that *$X$ is locally Noetherian* (rather than *$f$ is locally of finite type*) is what makes the proposition work. Part 1's footnote is thus slightly misstated: one must hypothesize that the base is Noetherian, not merely that the map is of finite type. The distinction matters when working over non-Noetherian bases (e.g., in rigid analytic geometry, or in the theory of adic spaces), where the two conditions genuinely differ.

#### 6.4 The Definition of Étale

We may now state the full definition.

**Definition 6.4.1** (Étale morphism). *A morphism of schemes $f : Y \to X$ is **étale** if $f$ is:*

*(i) Locally of finite presentation,*

*(ii) Flat, and*

*(iii) Unramified.*

*Equivalently (under locally of finite presentation), $f$ is étale if and only if $f$ is smooth of relative dimension 0.*

**Theorem 6.4.2** (Equivalent characterizations). *Let $f : Y \to X$ be locally of finite presentation. The following are equivalent:*

*(i) $f$ is étale.*

*(ii) $f$ is flat and the relative differentials $\Omega^1_{Y/X}$ vanish.*

*(iii) $f$ is smooth and $\Omega^1_{Y/X} = 0$.*

*(iv) For each $y \in Y$ with $x = f(y)$, there exists an affine open neighborhood $\mathrm{Spec}(B) \ni y$ mapping into an affine open $\mathrm{Spec}(A) \ni x$, and an element $g \in A[T] / (h)$ such that $B \cong A[T, g^{-1}] / (h)$ and $h'(T)$ is a unit in $A[T, g^{-1}] / (h)$.*

*(v) $f$ is a local isomorphism in the étale topology (a covering by étale morphisms).*

*Proofs of these equivalences are in EGA IV, §17, or Milne (1980), Chapter I, §3.*

**Remark 6.4.3.** Characterization (iv) — the "standard étale form" — is what most readers encounter in practice. It says that étale morphisms look, locally, like algebraic extensions given by a monic polynomial with unit derivative. This is the form used in computations in arithmetic geometry and algebraic number theory.

#### 6.5 Examples of Étale Morphisms

**Example 6.5.1** (Finite separable extensions). *Let $K/k$ be a finite separable field extension, and let $f : \mathrm{Spec}(K) \to \mathrm{Spec}(k)$. Then $f$ is étale.*

This is the prototypical example; all of arithmetic geometry's use of étale morphisms extends this case to schemes of higher dimension.

**Example 6.5.2** (Smooth degree-2 double cover). *Let $k$ be a field of characteristic $\neq 2$, and let $A = k[x]$, $B = A[y]/(y^2 - x)$. The map $\mathrm{Spec}(B) \to \mathrm{Spec}(A)$ is étale on the open subset where $x \neq 0$ (i.e., $B_x = k[x, x^{-1}, y]/(y^2 - x)$), but fails to be étale at $x = 0$ (where the fiber has a "double point").*

*Verification.* The derivative of $y^2 - x$ with respect to $y$ is $2y$. At $x = 0$, we have $y = 0$ in the fiber, so $2y = 0$, which is not a unit. Hence the map is not étale at the origin. On the locus $x \neq 0$, $y = \pm\sqrt{x} \neq 0$, so $2y$ is a unit, and the map is étale.

This illustrates how étale-ness is a local condition that fails at ramification points. $\square$

**Example 6.5.3** (Covering of the pointed line). *Let $A = k[x, x^{-1}]$ and $B = A[y]/(y^n - x)$ for $n$ invertible in $k$. Then $\mathrm{Spec}(B) \to \mathrm{Spec}(A)$ is an étale cover of degree $n$.*

*Verification.* The derivative is $ny^{n-1}$, and on $B = A[y]/(y^n - x)$ we have $y^n = x$, so $y^{n-1} = x/y$. Since $x$ is a unit in $A$ and $y$ is a unit in $B$ (its $n$-th power is $x$, a unit), $y^{n-1}$ is a unit. With $n$ invertible, the derivative is a unit, confirming étale-ness. $\square$

**Example 6.5.4** (Frobenius is usually not étale). *In characteristic $p$, the Frobenius morphism $F : X \to X^{(p)}$ is flat (over reasonable bases) but typically *not* unramified, hence not étale. Indeed, its relative differentials are large (in the smooth case, $\Omega^1_{X/X^{(p)}}$ is isomorphic to $\Omega^1_X$ itself, which is nonzero for positive-dimensional smooth $X$).*

This is a crucial point for arithmetic geometry: the geometric Frobenius is separable but not étale; it is the "absolute Frobenius" shifted by the base-change, and its non-étale-ness is exactly what makes ℓ-adic cohomology (which "divides out" by the Frobenius) nontrivial.

#### 6.6 Revised Passage

The author proposes the following revised definition for §3.2 of Part 1.

> **Definition (Étale morphism).** A morphism of schemes $f: Y \to X$ is *étale* if it satisfies three conditions:
>
> 1. **Locally of finite presentation:** Locally, $Y$ is given by a ring $A[T_1, \ldots, T_n]/(f_1, \ldots, f_m)$ over $X$, with *finitely many* generators and *finitely many* relations. (Over a Noetherian base $X$, this is equivalent to locally of finite type.)
>
> 2. **Flat:** The stalks $\mathcal{O}_{Y,y}$ are flat as modules over the stalks $\mathcal{O}_{X,f(y)}$. Intuitively: the fibers of $f$ have constant dimension as $x$ varies.
>
> 3. **Unramified:** The sheaf of relative differentials $\Omega^1_{Y/X}$ vanishes. Equivalently, for each $y \in Y$, the residue field extension $\kappa(y)/\kappa(f(y))$ is finite separable, and the maximal ideal $\mathfrak{m}_{f(y)} \cdot \mathcal{O}_{Y,y}$ generates $\mathfrak{m}_y$ in $\mathcal{O}_{Y,y}$.
>
> In the case of an affine variety defined by $A[T]/(g)$ over $A$, the condition of étale-ness reduces to: $g'(T)$ (the formal derivative) is a *unit* in the localized ring. This is the origin of the intuition "the derivative does not vanish," but in more general settings the precise formulation is via vanishing of $\Omega^1_{Y/X}$.

#### 6.7 Summary

Chapter 6 has established:

(i) The three conditions defining an étale morphism — flat, unramified, locally of finite presentation — each have precise mathematical content that Part 1's paraphrases approximate but do not capture.

(ii) The condition "unramified" is most cleanly stated as the vanishing of $\Omega^1_{Y/X}$, not as "the derivative does not vanish." The latter is a diagnostic only in specific classes of examples.

(iii) The relationship between "locally of finite type" and "locally of finite presentation" depends on whether the base is Noetherian. Part 1's footnote misstates this.

(iv) Étale morphisms admit several equivalent characterizations; the "standard étale form" (Theorem 6.4.2 (iv)) is the one most commonly encountered in practice.

Chapter 7 addresses a different medium-priority refinement: the treatment of finite field arithmetic and the "pseudo-sign" convention used in Part 1.

---

### Chapter 7: Arithmetic of Finite Fields and the Pseudo-Sign Convention

This chapter addresses a subtle but pedagogically important imprecision in §3.4 of Part 1: the use of the labels "$+\sqrt{2}$ lineage" and "$-\sqrt{2}$ lineage" to distinguish the two "sheets" of the covering associated to the polynomial $x^2 - 2$ over the finite fields $\mathbb{F}_7$ and $\mathbb{F}_{17}$.

The pedagogical function is clear: one wishes to convey that the two roots, being interchangeable under the Galois group $\mathbb{Z}/2\mathbb{Z}$, nonetheless admit some kind of "labeling" that places solutions from different primes into correspondence. The labels "+" and "−" evoke the familiar pictures from elementary algebra, where $\sqrt{2}$ and $-\sqrt{2}$ are clearly distinguishable as a positive and a negative real number.

The difficulty is that no such distinction exists in finite fields. There is no intrinsic notion of "positive" and "negative" in $\mathbb{F}_p$ for $p > 2$; the labels "+" and "−" are arbitrary choices that cannot be aligned across different primes in any canonical way.

#### 7.1 The Original Statement

In §3.4 (toward the end of Part 1's Chapter 3), the following passage appears:

> Sheet 1 (Corridor A): $\mathbb{F}_7$ floor 3 ↔ $\mathbb{F}_{17}$ floor 6 (+$\sqrt{2}$ lineage)
>
> Sheet 2 (Corridor B): $\mathbb{F}_7$ floor 4 ↔ $\mathbb{F}_{17}$ floor 11 (−$\sqrt{2}$ lineage)

The implication is that the two sheets of the étale cover over $\mathrm{Spec}(\mathbb{Z})$ corresponding to $x^2 - 2 = 0$ can be labeled globally: one sheet contains "the positive square roots of 2" at each prime, and the other contains "the negative square roots."

#### 7.2 Nature of the Simplification

The labels "+$\sqrt{2}$" and "−$\sqrt{2}$" evoke the real-number experience: $\sqrt{2} \approx 1.414$ is positive, $-\sqrt{2} \approx -1.414$ is negative. These are distinguishable as numbers because the real field $\mathbb{R}$ admits a canonical ordering (the positivity $\mathbb{R}_{>0}$).

In finite fields, no such ordering exists. The field $\mathbb{F}_7$ is a field, but it is not an *ordered* field: there is no subset of $\mathbb{F}_7$ that could be called "the positive elements." Indeed, $-1 = 6$ in $\mathbb{F}_7$, and one cannot reasonably call $6$ "positive."

Thus the assertion that "$3 = +\sqrt{2}$ in $\mathbb{F}_7$" and "$4 = -\sqrt{2}$ in $\mathbb{F}_7$" is *a matter of convention*, not of mathematical fact.

#### 7.3 What Does Exist: The Galois Action

What does exist, intrinsically, in $\mathbb{F}_p$ for $p \equiv 1 \pmod 2$ (i.e., all odd primes) is a Galois action interchanging the two square roots of 2 (when $2$ is a square mod $p$).

In $\mathbb{F}_7$: $3^2 = 9 \equiv 2 \pmod 7$, so $3$ is a square root. The other square root is $-3 \equiv 4 \pmod 7$. The Galois action (which here is trivial, since $\mathbb{F}_7 = \mathbb{F}_7$) does not interchange them; but the "abstract Galois symmetry of $\mathbb{Q}(\sqrt{2})/\mathbb{Q}$" — the group $\mathbb{Z}/2\mathbb{Z}$ — when "transported" to $\mathbb{F}_7$, acts by the map $a \mapsto -a$ on the two-element set $\{3, 4\} = \{\pm 3\}$.

The two elements of $\{3, 4\}$ in $\mathbb{F}_7$ are thus interchangeable by the abstract Galois symmetry but are not canonically labeled by "+ " and "−".

Similarly, in $\mathbb{F}_{17}$: $6^2 = 36 \equiv 2 \pmod{17}$, so $6$ and $-6 \equiv 11 \pmod{17}$ are the two square roots. Again, the two are interchangeable by $a \mapsto -a$ but not canonically labeled.

#### 7.4 The Question of Compatibility Across Primes

The substantive question — which Part 1 alludes to but does not make precise — is whether one can consistently label the square roots across *different* primes.

**Setup.** Let $L = \mathbb{Q}(\sqrt{2})$, and let $\mathcal{O}_L = \mathbb{Z}[\sqrt{2}]$ be its ring of integers. For each prime $p$ for which $2$ is a square mod $p$ (i.e., $p \equiv \pm 1 \pmod 8$ by quadratic reciprocity), the ideal $p \mathcal{O}_L$ splits as a product of two distinct prime ideals $\mathfrak{p}_1 \mathfrak{p}_2$, with $\mathfrak{p}_1 \neq \mathfrak{p}_2$.

The residue fields $\mathcal{O}_L / \mathfrak{p}_i \cong \mathbb{F}_p$ (in this split case), and the images of $\sqrt{2}$ in the two residue fields are the two square roots of 2 in $\mathbb{F}_p$, differing by a sign.

**The key point.** The choice of which prime ideal to call "$\mathfrak{p}_1$" versus "$\mathfrak{p}_2$" is arbitrary, but *once made, it extends to a labeling at all other primes*. This is because the element $\sqrt{2} \in \mathcal{O}_L$ is a single element, and its image in $\mathcal{O}_L / \mathfrak{p}$ is a single element for each prime ideal $\mathfrak{p}$.

The "arbitrary choice" corresponds to choosing a particular embedding $\sqrt{2} \hookrightarrow \mathbb{C}$ — i.e., fixing whether $\sqrt{2}$ is identified with $+1.414...$ or $-1.414...$. Once the embedding is fixed, all residue fields $\mathcal{O}_L / \mathfrak{p}$ are equipped with a *canonical* square root of 2 (relative to that embedding), namely the image of the chosen $\sqrt{2}$.

#### 7.5 Precise Formulation

**Definition 7.5.1** (Compatible square roots). *Let $L = \mathbb{Q}(\sqrt{2})$ with a fixed embedding $L \hookrightarrow \mathbb{C}$ (choosing, say, $\sqrt{2} = 1.414\ldots > 0$). Let $\mathfrak{p}$ be a prime ideal of $\mathcal{O}_L$ above a prime $p$ of $\mathbb{Z}$ for which $2$ is a square mod $p$. The **preferred square root** of 2 in $\mathcal{O}_L / \mathfrak{p}$ is the image of the fixed element $\sqrt{2} \in \mathcal{O}_L$ under the reduction map.*

**Proposition 7.5.2.** *With the above setup:*

*(i) For each $p \equiv \pm 1 \pmod 8$, there are two prime ideals $\mathfrak{p}_1, \mathfrak{p}_2$ of $\mathcal{O}_L$ above $p$, and the preferred square roots of 2 in $\mathcal{O}_L / \mathfrak{p}_1 \cong \mathbb{F}_p$ and $\mathcal{O}_L / \mathfrak{p}_2 \cong \mathbb{F}_p$ are *different*.*

*(ii) The choice of which ideal is $\mathfrak{p}_1$ and which is $\mathfrak{p}_2$ is not canonical, but once a consistent choice is made (by fixing the embedding $L \hookrightarrow \mathbb{C}$), it determines a global labeling of "Sheet 1" and "Sheet 2" in the étale covering $\mathrm{Spec}(\mathcal{O}_L) \to \mathrm{Spec}(\mathbb{Z})$.*

*(iii) The two sheets are interchanged by the nontrivial element of $\mathrm{Gal}(L/\mathbb{Q}) \cong \mathbb{Z}/2\mathbb{Z}$, which corresponds to complex conjugation under the fixed embedding.*

*(iv) In terms of Part 1's vocabulary: Sheet 1 consists of the prime ideals $\mathfrak{p}_1$ such that the image of $\sqrt{2}$ in $\mathcal{O}_L / \mathfrak{p}_1$ equals a pre-assigned square root in each residue field. Sheet 2 is the complement.*

*Proof.* This is a standard construction; see Marcus (1977), Chapter 6. $\square$

#### 7.6 The Difficulty of Pedagogy

The reason Part 1 uses "$+\sqrt{2}$" and "$-\sqrt{2}$" rather than a more precise formulation is pedagogical: readers at the high-school level (🏫) can interpret "positive" and "negative" immediately, while the proper formulation ("the image of $\sqrt{2}$ under the chosen embedding $L \hookrightarrow \mathbb{C}$, reduced modulo a chosen prime ideal") is impenetrable.

The challenge, then, is to find language that is pedagogically accessible but not actively misleading.

#### 7.7 Revised Passage

The author proposes the following revision to the passage in §3.4 of Part 1.

> **On the Labeling of Sheets:** We label the two sheets "Sheet 1" and "Sheet 2," but these labels are not intrinsic: they depend on an arbitrary choice. This choice is most conveniently made by fixing, once and for all, a preferred square root of 2 in $\overline{\mathbb{Q}} \subset \mathbb{C}$ — say, the positive real number $\sqrt{2} = 1.414\ldots$ Then at each prime $p$ for which $\sqrt{2}$ exists in $\mathbb{F}_p$, the corresponding preferred residue of $\sqrt{2}$ is the image of our fixed $\sqrt{2} \in \overline{\mathbb{Q}}$ under the reduction map.
>
> - Sheet 1: primes $\mathfrak{p}$ such that the preferred square root of 2 at $\mathfrak{p}$ is, say, "$3$ in $\mathbb{F}_7$" and "$6$ in $\mathbb{F}_{17}$."
> - Sheet 2: the complementary set.
>
> *Caveat.* The labels Sheet 1 and Sheet 2 are not intrinsic to any single prime; they depend on the global embedding $L \hookrightarrow \mathbb{C}$. If one chose the other embedding (sending $\sqrt{2} \mapsto -1.414\ldots$), the labels would swap. The sheets themselves are well-defined as disjoint sets; their *names* are conventional.
>
> *(Pedagogical note: The earlier labels "$+\sqrt{2}$ lineage" and "$-\sqrt{2}$ lineage" in this section were a simplification. They correspond to the two sheets, but the signs $\pm$ are not intrinsic in finite fields — there is no canonical "positive" in $\mathbb{F}_7$. What is intrinsic is the symmetry between the two sheets (the Galois action) and the consistent labeling provided by the embedding $L \hookrightarrow \mathbb{C}$.)*

#### 7.8 Summary

Chapter 7 has clarified:

(i) The labels "+$\sqrt{2}$" and "−$\sqrt{2}$" in finite fields are not intrinsic.

(ii) What is intrinsic is the Galois action interchanging the two square roots.

(iii) A global labeling of sheets is possible, but depends on a choice of embedding $L \hookrightarrow \mathbb{C}$ — not on any intrinsic property of the primes.

(iv) Part 1's language is pedagogically useful but should be accompanied by a caveat about its non-intrinsic nature.

---

### Chapter 8: The Chebotarev Density Theorem

Part 1 invokes the Chebotarev density theorem in §3.3, in the context of understanding how the factorization pattern of polynomials varies with the prime $p$. The invocation is brief and omits several important hypotheses. This chapter supplies the full statement of the theorem and discusses its hypotheses carefully.

#### 8.1 The Original Statement

Part 1 §3.3 states:

> By the Chebotarev density theorem, the density of primes corresponding to each conjugacy class of $G = S_3$ equals the class size divided by $|G|$: identity class density $1/6$, transposition class $3/6 = 1/2$, 3-cycle class $2/6 = 1/3$.

The invocation is abbreviated: the theorem is mentioned by name, applied, and moved on from. For a mathematician, this is sufficient. For a graduate-level reader encountering Chebotarev for the first time, it leaves important questions unaddressed:

- What is the precise statement of the theorem?
- What are its hypotheses?
- What are its exceptions (e.g., what happens at ramified primes)?
- Why is the density proportional to the conjugacy class size?

#### 8.2 Nature of the Simplification

The simplification is one of compression rather than inaccuracy. The stated density values (1/6, 1/2, 1/3) are correct for the Galois group $S_3$ acting on the splitting field of $x^3 - 2$. What is elided is the framework within which the theorem operates — in particular:

1. The need for $L/\mathbb{Q}$ to be a Galois extension (otherwise one must pass to the Galois closure).
2. The exclusion of ramified primes (a finite set of exceptions).
3. The precise definition of "density" (natural density, Dirichlet density, or analytic density — for the Chebotarev theorem, any of these work, but they require their own definitions).
4. The meaning of "Frobenius conjugacy class" (requiring the Frobenius element to be defined up to conjugacy).

Each of these is a genuine prerequisite for the theorem's correct application.

#### 8.3 Precise Formulation

Let us state the theorem in full.

**Theorem 8.3.1** (Chebotarev density theorem). *Let $L/\mathbb{Q}$ be a finite Galois extension, with Galois group $G = \mathrm{Gal}(L/\mathbb{Q})$. Let $C \subset G$ be a conjugacy class. Then:*

*(i) For each prime $p$ of $\mathbb{Q}$ unramified in $L$, the Frobenius conjugacy class $[\mathrm{Frob}_p] \subset G$ is well-defined.*

*(ii) The set of primes $p$ for which $[\mathrm{Frob}_p] = C$ has natural density*

$$
\delta(C) = \frac{|C|}{|G|}.
$$

*In particular, this density exists and is independent of which primes we consider (subject to being unramified).*

**Hypotheses unpacked:**

1. **$L/\mathbb{Q}$ is Galois.** For an arbitrary polynomial $f \in \mathbb{Q}[x]$, one applies the theorem to the splitting field $L$ of $f$, which is always Galois. If $f$ is not irreducible, one obtains a conjugacy class in $\mathrm{Gal}(L/\mathbb{Q})$ rather than in $S_n$, but the density result still applies.

2. **Unramified primes.** A prime $p$ is *unramified* in $L$ if the prime ideal $p\mathcal{O}_L$ factors in $\mathcal{O}_L$ without repeated factors. For a polynomial $f(x) \in \mathbb{Z}[x]$, the ramified primes are the primes dividing the discriminant of $f$ — a finite set. For example, for $f(x) = x^3 - 2$, the discriminant is $-108 = -4 \cdot 27$, so the ramified primes are $2$ and $3$. The Chebotarev theorem excludes these finitely many primes from the count.

3. **Natural density.** For a set $S$ of primes, the natural density is

$$
\lim_{x \to \infty} \frac{|\{p \in S : p \leq x\}|}{|\{p : p \leq x\}|}.
$$

The Chebotarev theorem asserts this limit exists and equals $|C|/|G|$.

**Theorem 8.3.2** (Frobenius element, precise definition). *Let $L/\mathbb{Q}$ be Galois, $p$ an unramified prime, $\mathfrak{P}$ a prime of $\mathcal{O}_L$ above $p$. Then there exists a unique element $\mathrm{Frob}_\mathfrak{P} \in G$ such that*

$$
\mathrm{Frob}_\mathfrak{P}(x) \equiv x^p \pmod{\mathfrak{P}} \quad \text{for all } x \in \mathcal{O}_L.
$$

*Different choices of $\mathfrak{P}$ above $p$ give conjugate Frobenius elements; thus the conjugacy class $[\mathrm{Frob}_p] \in G$ is well-defined independently of the choice.*

*Proof.* This is classical; see Neukirch (1999), Chapter IV, or Lang (1994), Chapter IV. The key ingredient is that for unramified primes, the decomposition group $D_\mathfrak{P} = \mathrm{Stab}_G(\mathfrak{P})$ is isomorphic to the Galois group $\mathrm{Gal}(\kappa(\mathfrak{P})/\kappa(p))$ of the residue field extension, which is cyclic (generated by $x \mapsto x^p$). $\square$

#### 8.4 Application to $x^3 - 2 = 0$

Let $L$ be the splitting field of $x^3 - 2$ over $\mathbb{Q}$. Then $L = \mathbb{Q}(\sqrt[3]{2}, \zeta_3)$, $[L:\mathbb{Q}] = 6$, and $G = \mathrm{Gal}(L/\mathbb{Q}) = S_3$.

The conjugacy classes of $S_3$ are:

- $C_1 = \{e\}$: identity, $|C_1| = 1$
- $C_2 = \{(12), (13), (23)\}$: transpositions, $|C_2| = 3$
- $C_3 = \{(123), (132)\}$: 3-cycles, $|C_3| = 2$

By Chebotarev:

- Primes with $\mathrm{Frob}_p = e$ (identity, split completely): density $1/6$
- Primes with $\mathrm{Frob}_p$ a transposition: density $3/6 = 1/2$
- Primes with $\mathrm{Frob}_p$ a 3-cycle: density $2/6 = 1/3$

**What does each class mean for $x^3 - 2$?** Recall that the factorization type of $x^3 - 2 \pmod p$ is determined by the cycle structure of $\mathrm{Frob}_p$ acting on the three roots.

- $\mathrm{Frob}_p = e$ ⟹ $x^3 - 2$ splits into three linear factors mod $p$; equivalently, $p$ splits completely in $L$, which happens iff $2$ is a cube mod $p$ *and* $\zeta_3 \in \mathbb{F}_p$ (i.e., $p \equiv 1 \pmod 3$). Density 1/6. Example: $p = 31$ (since $3^3 = 27 \equiv -4 \not\equiv 2$... let me compute correctly. $x^3 - 2 \pmod{31}$: try $x = 4$: $64 = 2 \cdot 31 + 2 = 64$, yes $4^3 = 64 \equiv 2 \pmod{31}$. Other roots: $4\zeta_3$ and $4\zeta_3^2$ in $\overline{\mathbb{F}}_{31}$. But $\zeta_3 \in \mathbb{F}_{31}$? Need $x^2 + x + 1 = 0$ to have a root. Discriminant $= -3$. Is $-3$ a square mod 31? $-3 \equiv 28 \pmod{31}$. Check: $28 \pmod{31}$, squares mod 31 are $\{1, 2, 4, 5, 7, 8, 9, 10, 14, 16, 18, 19, 20, 25, 28\}$ — yes, $28 = 17^2 \pmod{31}$ or similar. So yes $\zeta_3 \in \mathbb{F}_{31}$ and $x^3 - 2$ splits into three linear factors mod 31.)

- $\mathrm{Frob}_p$ a transposition ⟹ $x^3 - 2$ factors as (linear) × (quadratic); equivalently, $2$ is a cube mod $p$ but $\zeta_3 \notin \mathbb{F}_p$. Density 1/2. Example: $p = 5$. $x^3 - 2 \pmod 5$: try $x = 3$: $27 \equiv 2 \pmod 5$, yes. So $(x - 3)$ is a factor, and the remaining quadratic is $x^2 + 3x + 4 \pmod 5$ (check: discriminant $9 - 16 = -7 \equiv 3 \pmod 5$; $3$ is not a square mod 5, so the quadratic is irreducible).

- $\mathrm{Frob}_p$ a 3-cycle ⟹ $x^3 - 2$ is irreducible mod $p$; equivalently, $2$ is not a cube mod $p$. Density 1/3. Example: $p = 7$. Test cubes mod 7: $1^3 = 1, 2^3 = 1, 3^3 = 6, 4^3 = 1, 5^3 = 6, 6^3 = 6$. Cubes mod 7 are $\{1, 6\}$, so 2 is not a cube; hence $x^3 - 2$ is irreducible mod 7.

These examples are consistent with the Chebotarev predictions.

#### 8.5 Proof Sketch of Chebotarev

A full proof of the Chebotarev density theorem is beyond the scope of these notes, but we sketch the structure.

**Ingredients:**

1. **Dirichlet's theorem on primes in arithmetic progressions** provides the case $G = (\mathbb{Z}/n\mathbb{Z})^\times$ (cyclotomic extensions of $\mathbb{Q}$). For each class $a \in (\mathbb{Z}/n\mathbb{Z})^\times$, the density of primes $p \equiv a \pmod n$ is $1/\varphi(n) = 1/|G|$.

2. **Abelian Chebotarev** (class field theory) extends this to all abelian Galois extensions $L/\mathbb{Q}$, using the Artin reciprocity law.

3. **General Chebotarev** extends to non-abelian Galois extensions $L/\mathbb{Q}$ by invoking the Artin L-function $L(s, \chi)$ attached to each irreducible representation $\chi$ of $G$. The density result follows from the non-vanishing of $L(s, \chi)$ at $s = 1$, proven by Brauer using an induction argument from abelian subgroups.

For a modern exposition, see Neukirch (1999), Chapter VII, §13. For a concise statement, see Milne's *Class Field Theory* (2020), Chapter VIII.

#### 8.6 Revised Passage

The author proposes expanding §3.3 of Part 1 to include the following:

> **Chebotarev Density Theorem.** (Chebotarev 1922, building on Dirichlet 1837.) Let $L/\mathbb{Q}$ be a finite Galois extension with Galois group $G$. Let $C \subset G$ be a conjugacy class. Then the set of primes $p$ of $\mathbb{Q}$ such that $\mathrm{Frob}_p \in C$ (when $p$ is unramified in $L$) has natural density
>
> $$
> \frac{|C|}{|G|}.
> $$
>
> **Hypothesis on ramified primes.** The theorem excludes the finitely many primes $p$ that ramify in $L$. For a polynomial $f \in \mathbb{Z}[x]$ with splitting field $L$, these are the primes dividing $\mathrm{disc}(f)$. For $x^3 - 2$, the ramified primes are $p = 2$ and $p = 3$, excluded from the Chebotarev count.
>
> **Application to $x^3 - 2$:** The Galois group is $G = S_3$, with three conjugacy classes:
>
> | Class | Cycle type | Size | Density |
> |---|---|---|---|
> | $C_1$ | $(1,1,1)$ | 1 | 1/6 |
> | $C_2$ | $(2,1)$ | 3 | 1/2 |
> | $C_3$ | $(3)$ | 2 | 1/3 |
>
> For $x^3 - 2 \pmod p$ (with $p \neq 2, 3$), the factorization type is:
>
> - Three linear factors iff $\mathrm{Frob}_p = e$: occurs with density 1/6. Example: $p = 31$.
> - One linear + one quadratic iff $\mathrm{Frob}_p$ is a transposition: density 1/2. Example: $p = 5$.
> - Irreducible iff $\mathrm{Frob}_p$ is a 3-cycle: density 1/3. Example: $p = 7$.

#### 8.7 Summary

Chapter 8 has established:

(i) The Chebotarev density theorem has a precise formulation that includes the hypothesis that the extension is Galois.

(ii) Ramified primes are excluded from the count; these form a finite set determined by the discriminant.

(iii) The Frobenius element is defined only up to conjugacy, which is why the theorem concerns conjugacy classes rather than individual elements.

(iv) The density is natural density, not merely a qualitative statement.

(v) The theorem has a clear application to $x^3 - 2$, with specific examples verifying each density prediction.

Chapter 9 turns to the third tier of refinements: the rhetorical and historical matters that, while not affecting mathematical substance, can influence the reader's orientation.

## Part IV: Low-Priority Refinements

### Chapter 9: Zariski Topology and Oversmoothing — A Critical Assessment

This chapter addresses a claim made in §3.2 of Part 1 (and echoed in Chapter 1, Reason 5) concerning the relationship between the "oversmoothing problem" in Graph Neural Networks and the "coarseness" of the Zariski topology. The claim is interesting and pedagogically suggestive, but — as the present author will argue — it is overstated. A careful reader would benefit from understanding both the genuine structural analogy (which exists) and the specific points where the analogy breaks down.

#### 9.1 The Original Statement

The key passage appears in Chapter 1 of Part 1:

> **Reason 5:** The idea of étale topology overcoming the "coarseness" of Zariski topology is mathematically isomorphic to solving the "oversmoothing problem" in GNNs. The oversmoothing phenomenon — where stacking GNN layers makes node features uniform — is structurally the same as the Zariski topology problem of "open sets being too large to distinguish local features."

And, more cautiously, in §3.2:

> Within a single floor, the answer is unique. As long as you stay on floor 2, there is no confusion. "Overlaying sheets" means creating as many parallel worlds (layers) as there are variations of the answer, and stacking them on top of each other.

The first passage asserts a structural isomorphism. The second passage describes the étale topology's role in finer resolution, without directly invoking the GNN analogy.

#### 9.2 Nature of the Overstatement

The word "isomorphic" is a technical term in mathematics, denoting a precise correspondence between structures. When Part 1 writes that the étale/Zariski distinction is "mathematically isomorphic" to the GNN oversmoothing problem, it is using language that a careful mathematician might interpret as asserting:

(i) There is a well-defined mathematical structure underlying each phenomenon.

(ii) There is a structure-preserving bijection between them.

Neither of these is quite true. Let us examine the two phenomena separately.

#### 9.3 The Zariski Topology and Its Limitations

The Zariski topology on a scheme $X$ has the property that its open sets are large (often "dense"), so that the topology cannot detect local properties in a fine way. A canonical example is the following.

**Example 9.3.1.** Consider $X = \mathrm{Spec}(k[t])$, the affine line over a field $k$. The Zariski open sets are either empty, or the whole space, or the complement of a finite set of closed points. In particular, any Zariski open set $U \neq \emptyset$ contains "almost all" of $X$: only finitely many points are excluded.

Consequently, sheaves defined via the Zariski topology cannot distinguish "local" behavior near a specific point $x \in X$ from the behavior on a very large open set containing $x$.

**Why this matters.** For applications to algebraic number theory and arithmetic geometry, one frequently wants to capture "branching" or "covering" behavior that is local in nature but cannot be described by inclusion of Zariski-open subsets. The étale topology solves this by permitting covers that are *not* inclusions — namely, finite étale morphisms — thereby allowing the topology to "see" local features that Zariski cannot.

**Formal structure.** The issue is that the Zariski site (the site whose covers are Zariski open inclusions) is "too coarse" — its topoi of sheaves lose too much information. The étale site remedies this by enriching the notion of cover. The shift from Zariski to étale is a shift from one site to another, with a resulting change in the category of sheaves.

#### 9.4 The Oversmoothing Problem in GNNs

The oversmoothing problem refers to a phenomenon in Graph Neural Networks where, as the number of message-passing layers increases, the node representations become increasingly similar across the graph. In the limit of many layers, all nodes converge to a common representation, losing all discriminating information.

**Example 9.4.1** (Linear message passing). Consider a simple graph $G = (V, E)$ with adjacency matrix $A$ and degree matrix $D$. A basic message-passing update is

$$
H^{(\ell+1)} = \tilde{A} H^{(\ell)} W^{(\ell)},
$$

where $\tilde{A} = D^{-1/2}(A + I)D^{-1/2}$ is the normalized adjacency with self-loops, and $W^{(\ell)}$ are learnable weights. The matrix $\tilde{A}$ is stochastic-like, with eigenvalues in $[-1, 1]$ (and largest eigenvalue 1). Iterating the update causes information to "diffuse" across the graph, and in the limit $\ell \to \infty$, all node representations converge to the principal eigenvector of $\tilde{A}$ — a single vector, the same for all nodes.

**Why this matters.** The oversmoothing problem limits the depth of GNNs: stacking many layers hurts rather than helps, because the "signal" (discriminating information between nodes) is smoothed away. This is problematic for applications where long-range dependencies must be captured.

**Formal structure.** The issue is that the message-passing operator $\tilde{A}$ has a dominant eigenvector, and iterating the operator projects all inputs onto this dominant eigenvector exponentially fast. The rate of convergence is controlled by the spectral gap of $\tilde{A}$.

#### 9.5 Are These "Isomorphic"?

Let us now examine whether the two phenomena are structurally the same.

**Point of similarity 1: Both involve a loss of local distinguishability.** In the Zariski case, large open sets cannot distinguish local features. In the oversmoothing case, deep layers cannot distinguish local features. Both phenomena express the idea that a "standard" framework is insufficiently fine-grained.

**Point of similarity 2: Both admit remedies via richer structures.** In the Zariski case, the remedy is the étale topology (or higher). In the oversmoothing case, the remedy is Sheaf Neural Networks, whose use of stalks and restriction maps provides a richer structure analogous to étale sheaves.

**Points of dissimilarity:**

**(a) The mathematical mechanisms are different.**

- Zariski coarseness is a phenomenon of point-set topology: certain open sets are "too large" because the topology has too few closed sets (the closed sets being zero loci of polynomials).

- Oversmoothing is a phenomenon of spectral analysis: the operator $\tilde{A}$ has a spectral gap, and iterating it converges to the dominant eigenvector.

These are related in that both involve "information loss," but the mathematical tools and theorems used to analyze them are entirely different.

**(b) The notions of "locality" differ.**

- In Zariski, "locality" refers to localization at a prime ideal: one is asking what happens "near a point" in the scheme-theoretic sense.

- In GNN oversmoothing, "locality" refers to a neighborhood in a graph: one is asking what happens "near a node" in the combinatorial sense.

These are both notions of locality, but they are not isomorphic. Scheme-theoretic locality is a construction in ring theory; graph locality is a construction in combinatorics.

**(c) The nature of the remedy differs.**

The remedy for Zariski coarseness is to *change the topology* — to move from Zariski to étale (or higher). This is an intrinsic change to the mathematical framework, affecting the category of sheaves.

The remedy for GNN oversmoothing is to *redesign the architecture* — to add residual connections, normalization, attention mechanisms, or sheaf-theoretic stalks. This is a change in the computational mechanism, not in the underlying topology of the graph.

**(d) Sheaf Neural Networks are inspired by but not isomorphic to étale sheaves.**

Bodnar et al. (2022) and related work explicitly draw on the cellular sheaf theory of Curry (2014), Hansen–Ghrist (2019), and similar sources. The terminology "sheaf" is borrowed, and the mathematical structure of restriction maps along edges is genuinely sheaf-theoretic. However, the Sheaf Neural Network is not a special case of étale sheaf theory in any technical sense; it is an analogy that inspires a new mathematical framework.

The correct statement, the author proposes, is:

> *The limitations of the Zariski topology and the oversmoothing problem in GNNs both illustrate a broader principle: mathematical frameworks that are too "coarse-grained" fail to capture local structure. Both phenomena are addressed by enriching the framework with sheaf-theoretic constructions. The specific mathematical mechanisms differ, but the conceptual parallel is instructive.*

This is weaker than "structurally the same," but it is more accurate.

#### 9.6 Revised Passage

The author proposes the following revision to the passage in Chapter 1 of Part 1.

> **Reason 5 (revised):** The étale topology's overcoming of the Zariski topology's "coarseness" is *conceptually analogous* to the Sheaf Neural Network's overcoming of oversmoothing. Both situations illustrate a general principle: mathematical frameworks that are too coarse — whether a topology with too few open sets, or a graph neural network with too few distinguishing features — fail to capture local structure. Both are remedied by enriching the framework with sheaf-theoretic constructions: étale sheaves in the case of algebraic geometry, cellular sheaves in the case of GNNs.
>
> *The parallel is conceptual, not mathematical.* The Zariski topology's coarseness is a matter of point-set topology; the oversmoothing problem is a matter of spectral dynamics. The two phenomena are not isomorphic as mathematical structures, but they illustrate a shared insight about the value of sheaf-theoretic thinking.

The revision:

(i) Replaces "structurally the same" with "conceptually analogous."

(ii) Explicitly notes the different mathematical mechanisms.

(iii) Preserves the pedagogical force of the analogy while not overclaiming.

#### 9.7 Summary

Chapter 9 has established:

(i) There is a genuine conceptual parallel between Zariski coarseness and GNN oversmoothing: both involve loss of local distinguishability, remedied by sheaf-theoretic frameworks.

(ii) The two phenomena are *not* mathematically isomorphic: the mechanisms are different (topology vs. spectrum), the notions of locality are different (scheme-theoretic vs. combinatorial), and the remedies are different (change of topology vs. change of architecture).

(iii) Part 1's claim of "structural isomorphism" is pedagogically useful but mathematically overstated. The revised phrasing captures the parallel without overclaiming.

---

### Chapter 10: Historical Perspective on Scheme Theory

This chapter addresses a low-priority but persistent theme in Part 1: the characterization of algebraic geometry (particularly in the title and introduction) as "200-year-old." The characterization is loose, and a more accurate historical framing would benefit the reader's orientation.

#### 10.1 The Original Statement

The full title of Part 1 is:

> *Buildings in the Desert: How 200-Year-Old Algebraic Geometry Is Revolutionizing Deep Learning*

And in the Prologue:

> All of these originate from a single branch of mathematics: algebraic geometry (scheme theory).
>
> Yet algebraic geometry is known as "one of the most difficult fields in all of mathematics." Hartshorne's textbook is a struggle even for graduate students. Grothendieck's EGA runs to thousands of pages.

The juxtaposition of "200-year-old" with Grothendieck's EGA is the key imprecision.

#### 10.2 Nature of the Simplification

The phrase "200-year-old algebraic geometry" is pedagogically effective — it evokes a venerable tradition, rooted in the great names of the 19th century (Riemann, Abel, Jacobi, Kronecker). Such a framing suggests that the mathematical tools now entering deep learning are ancient and proven, which is reassuring.

However, the specific tools Part 1 invokes — scheme theory, étale cohomology, ℓ-adic representations, topoi — are not 200 years old. They are products of the Grothendieck revolution of the 1960s. In historical terms:

- *Classical algebraic geometry* (Riemann surfaces, projective varieties, intersection theory): 19th century, roughly 150–200 years old.
- *Italian school* (Castelnuovo, Enriques, Severi): 1890s–1930s, roughly 100–130 years old.
- *Weil's foundations* (Foundations of Algebraic Geometry, 1946): 80 years old.
- *Grothendieck's scheme theory* (EGA, 1960s): 60 years old.
- *Étale cohomology* (SGA 4, 1963–1964): 60 years old.
- *Modern applications to Sheaf Neural Networks*: 3–5 years old (Bodnar et al. 2022).

The tools that Part 1 describes as "revolutionary for deep learning" are, therefore, predominantly products of the 1960s — not the 1820s.

This is not an error in the usual sense. "200-year-old algebraic geometry" is a reasonable shorthand for "algebraic geometry as a mature discipline." The concern is that a reader might interpret the phrase as suggesting that *specifically* the tools used in deep learning (scheme theory, étale cohomology) are 200 years old, which they are not.

#### 10.3 A More Precise Historical Narrative

Let us sketch the history in more detail.

**Classical algebraic geometry (1820s–1900s).** The roots trace to Abel's work on elliptic curves (1820s), Riemann's theory of Riemann surfaces (1850s), and Jacobi's work on elliptic functions. The period culminates in the work of Picard, Humbert, and the Italian school (Castelnuovo, Enriques, Severi), who laid the foundations of what we now call classical algebraic geometry.

**First modernizations (1900s–1940s).** The 20th century saw several attempts to rigorize and generalize classical algebraic geometry. Key figures include van der Waerden (algebraic foundations in terms of ideals), Zariski (Zariski topology, normalization, local rings), and Weil (*Foundations of Algebraic Geometry*, 1946, giving a systematic treatment using abstract varieties).

**The Grothendieck revolution (1950s–1970s).** Beginning in the late 1950s, Alexander Grothendieck systematically reformulated algebraic geometry in terms of schemes. The *Éléments de Géométrie Algébrique* (EGA), published 1960–1967 by Grothendieck and Dieudonné, represents this reformulation in its definitive form. The *Séminaire de Géométrie Algébrique* (SGA), running 1960–1969 at IHÉS, developed étale cohomology (SGA 4), ℓ-adic cohomology (SGA 5), and related tools. These were essential for Deligne's 1974 proof of the Weil conjectures.

**Post-Grothendieck developments (1970s–present).** The tools developed by Grothendieck found applications to number theory (Deligne, Serre, Faltings), representation theory (the Langlands program), and more recently to applied mathematics (topological data analysis, sheaf-theoretic approaches to machine learning).

**Sheaf Neural Networks and related work (2020s).** Bodnar, Di Giovanni, Chamberlain, Liò, and Bronstein (2022) introduced the term "Neural Sheaf Diffusion" at NeurIPS, applying cellular sheaf theory to GNNs. Hansen and Ghrist (2019, 2020) had earlier developed "spectral sheaf theory" for applied purposes, including cellular sheaves on graphs. Curry (2014) provided the foundational cellular sheaf theory that underpins these applications.

#### 10.4 What Is "Cellular Sheaf Theory"?

Since Sheaf Neural Networks specifically use *cellular* sheaves rather than étale sheaves, a brief clarification is in order.

**Definition 10.4.1** (Cellular sheaf). *Let $X$ be a CW complex (or, simplicially, a simplicial complex). A **cellular sheaf** on $X$ is an assignment, to each cell $\sigma$ of $X$, of a vector space $\mathcal{F}(\sigma)$ (the **stalk**), together with, for each incidence relation $\tau \lhd \sigma$ (i.e., $\tau$ is a face of $\sigma$), a linear map $\mathcal{F}(\tau \lhd \sigma) : \mathcal{F}(\tau) \to \mathcal{F}(\sigma)$ (the **restriction map**), satisfying the cocycle condition: for a chain of incidences $\rho \lhd \tau \lhd \sigma$, the composition $\mathcal{F}(\rho \lhd \sigma) = \mathcal{F}(\tau \lhd \sigma) \circ \mathcal{F}(\rho \lhd \tau)$.*

**Example 10.4.2** (Cellular sheaf on a graph). *Let $G = (V, E)$ be a graph, viewed as a 1-dimensional CW complex. A cellular sheaf on $G$ assigns:*

- *To each vertex $v$, a vector space $\mathcal{F}(v)$.*
- *To each edge $e = \{u, v\}$, a vector space $\mathcal{F}(e)$.*
- *To each incidence $v \lhd e$, a linear map $\mathcal{F}(v \lhd e) : \mathcal{F}(v) \to \mathcal{F}(e)$.*

*A **section** of the sheaf is a collection of elements $(x_v)_{v \in V}$, $x_v \in \mathcal{F}(v)$, such that for every edge $e = \{u, v\}$:*

$$
\mathcal{F}(u \lhd e)(x_u) = \mathcal{F}(v \lhd e)(x_v).
$$

**Remark 10.4.3.** Cellular sheaves are distinct from étale sheaves in several respects:

- Cellular sheaves are defined on a CW or simplicial complex, a combinatorial structure.
- Étale sheaves are defined on a scheme (or more generally, a site), an algebraic-geometric structure.
- The "stalks" of a cellular sheaf are vector spaces; the stalks of an étale sheaf are modules over a local ring.
- The "restriction maps" of a cellular sheaf are linear maps along incidences; the restriction maps of an étale sheaf are algebraic morphisms between stalks along étale neighborhoods.

The two are related by a functor from the étale site of a scheme to certain cellular complexes in algebraic topology, but this is a deep connection requiring significant machinery (the étale homotopy type of a scheme, due to Artin–Mazur).

**Remark 10.4.4** (Historical lineage of SNN). Sheaf Neural Networks, in their modern form, trace their lineage more directly to cellular sheaf theory (Curry, MacPherson, Shepard) than to Grothendieck's étale sheaves. The use of "sheaf" language in the AI literature should not be interpreted as invoking the full apparatus of algebraic geometry. Part 1's discussion rightly emphasizes the étale sheaves as an arithmetic prototype, but it is cellular sheaves that are operationally deployed in practice.

#### 10.5 Revised Passage

The author proposes the following revision to the title and opening of Part 1.

**Revised title:** *Buildings in the Desert: How the Mathematics of Algebraic Geometry Is Entering Deep Learning*

**Revised Prologue passage:**

> In 2025, the words "Sheaf," "Categorical," and "Algebraic Geometry" are appearing with increasing frequency in papers accepted at NeurIPS and ICML.
>
> This is no coincidence.
>
> If you are a machine learning engineer or an AI research scientist, this article concerns your career.
>
> The mathematical tools at the heart of these developments trace their roots to the 19th century (classical algebraic geometry of Abel, Riemann, and the Italian school) but reached their modern form only in the 1960s, through the work of Alexander Grothendieck and his school. The tools currently entering deep learning — sheaves, schemes, cohomology — are products of this modern development. The term "200-year-old mathematics," sometimes used informally, should be understood in the sense of a mature and well-tested discipline, not in the sense of tools unchanged since the 1820s.

This revision removes the potentially misleading "200-year-old" while preserving the rhetorical force of "mathematics that has proven its worth over a long intellectual tradition."

#### 10.6 Summary

Chapter 10 has established:

(i) The tools Part 1 emphasizes (scheme theory, étale cohomology, cellular sheaves) are products of the 20th century, primarily the 1960s onwards, not the 1820s.

(ii) The shorthand "200-year-old algebraic geometry" is pedagogically effective but historically imprecise. A more accurate phrasing acknowledges both the 19th-century roots and the 20th-century reformulation.

(iii) Cellular sheaves (used in Sheaf Neural Networks) are distinct from étale sheaves. The conceptual lineage connects them, but they are different mathematical objects.

(iv) A revised title and opening that acknowledges these distinctions would better serve the careful reader.

---

## Part V: Old-New Correspondence

### Chapter 11: Comprehensive Old-New Correspondence Table

This chapter provides a comprehensive table mapping each of the passages in Part 1 that the present notes have identified as requiring refinement, together with the proposed revision. The table is intended to serve as a practical reference for readers who wish to annotate their copy of Part 1.

#### 11.1 Overview of Refinements

The present notes have identified refinements in three tiers:

**High-priority refinements (Chapters 3–5):**
- §3.3: Galois group of $x^3 - 1$ (Chapter 3)
- §3.3: Multiplicative group generators vs. Galois action (Chapter 4)
- §3.5: Same issue, cyclotomic cases $n = 4, 5, 6, 7$
- §3.3: Galois groups as permutation groups (Chapter 5)

**Medium-priority refinements (Chapters 6–8):**
- §3.2: Definition of étale morphism (Chapter 6)
- §3.4: Pseudo-sign convention for $\sqrt{2}$ in finite fields (Chapter 7)
- §3.3 and §3.5: Chebotarev density theorem (Chapter 8)

**Low-priority refinements (Chapters 9–10):**
- Chapter 1 / §3.2: Zariski/oversmoothing analogy (Chapter 9)
- Title and Prologue: "200-year-old" historical framing (Chapter 10)

#### 11.2 Old-New Correspondence Table

The table below lists the most consequential refinements in abbreviated form. For the full discussion of each refinement, the reader is referred to the corresponding chapter of these notes.

**Table 11.2.1: High-Priority Refinements**

| ID | Part 1 Section | Original Formulation | Refined Formulation | Full Discussion |
|---|---|---|---|---|
| H1 | §3.3 (table) | "Galois group: $\mathbb{Z}/2\mathbb{Z}$ (fix $x=1$, swap remaining 2)" for $x^3 = 1$ | "Galois group: $(\mathbb{Z}/3\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z}$; this is $\mathrm{Gal}(\mathbb{Q}(\zeta_3)/\mathbb{Q})$" | Chapter 3 |
| H2 | §3.3 | For $x^4 = 1$: "1-step rotation, 2-step skip, reverse" listed as three distinct "elevator movements" | The Galois group $(\mathbb{Z}/4\mathbb{Z})^\times$ has only 2 elements: identity and $\zeta_4 \mapsto \zeta_4^3$. The listed "rotations" include a translation, which is not a Galois element. | Chapter 4 |
| H3 | §3.3 | For $x^5 = 1$: "Rotate by 1, 2, 3, 4" as four elevator patterns | The Galois group $(\mathbb{Z}/5\mathbb{Z})^\times$ has 4 elements $\sigma_k : \zeta_5 \mapsto \zeta_5^k$. The "rotations" in the passage are generator choices, not Galois elements (though the count, 4, coincides). | Chapter 4 |
| H4 | §3.3 (implicit) | Discussion of Galois groups without stating "$G \hookrightarrow S_n$" | Explicit theorem: every Galois group embeds in $S_n$ as a transitive subgroup iff polynomial is irreducible. Most Galois groups are proper subgroups of $S_n$. | Chapter 5 |

**Table 11.2.2: Medium-Priority Refinements**

| ID | Part 1 Section | Original Formulation | Refined Formulation | Full Discussion |
|---|---|---|---|---|
| M1 | §3.2 | "Unramified — the derivative does not vanish" | Precise: $\Omega^1_{Y/X} = 0$. The "derivative does not vanish" is correct as a diagnostic only in the affine one-variable case. | Chapter 6 |
| M2 | §3.2 (footnote) | "Over Noetherian schemes, [finite presentation] follows automatically from 'finite type'" | Precise: "If *the base* $X$ is locally Noetherian, then locally of finite type implies locally of finite presentation." The hypothesis is on the base, not the map. | Chapter 6 |
| M3 | §3.4 | "Sheet 1 (Corridor A): ... (+$\sqrt{2}$ lineage)" / "Sheet 2 (Corridor B): ... (−$\sqrt{2}$ lineage)" | There is no intrinsic "$+$" or "$-$" in finite fields. The labels depend on an arbitrary choice of embedding $L \hookrightarrow \mathbb{C}$. Precise formulation uses "compatible labeling" via prime ideals of $\mathcal{O}_L$. | Chapter 7 |
| M4 | §3.3 (Chebotarev invocation) | "By the Chebotarev density theorem, the density of primes corresponding to each conjugacy class..." | Full statement includes: $L/\mathbb{Q}$ Galois, unramified primes only (finite set of exceptions), natural density, conjugacy class (not single element). | Chapter 8 |

**Table 11.2.3: Low-Priority Refinements**

| ID | Part 1 Section | Original Formulation | Refined Formulation | Full Discussion |
|---|---|---|---|---|
| L1 | Chapter 1 / §3.2 | "The oversmoothing phenomenon...is structurally the same as the Zariski topology problem of..." | Conceptually analogous but not mathematically isomorphic. Different mathematical mechanisms (topology vs. spectrum). Both illustrate the value of sheaf-theoretic enrichment. | Chapter 9 |
| L2 | Title and Prologue | "200-year-old algebraic geometry" | Classical algebraic geometry is ~200 years old; the specific tools used (schemes, étale cohomology) are products of the 1960s. | Chapter 10 |

#### 11.3 Revised Versions of Key Passages

For the reader who wishes to prepare an annotated edition of Part 1, the following revised passages may be substituted:

**For §3.3 (Galois group table):**

> | Equation | Splitting field | Galois group | Order |
> |---|---|---|---|
> | $x^2 - 2 = 0$ | $\mathbb{Q}(\sqrt{2})$ | $\mathbb{Z}/2\mathbb{Z}$ | 2 |
> | $\Phi_3(x) = 0$ | $\mathbb{Q}(\zeta_3)$ | $(\mathbb{Z}/3\mathbb{Z})^\times$ | 2 |
> | $\Phi_4(x) = 0$ | $\mathbb{Q}(\zeta_4)$ | $(\mathbb{Z}/4\mathbb{Z})^\times$ | 2 |
> | $\Phi_5(x) = 0$ | $\mathbb{Q}(\zeta_5)$ | $(\mathbb{Z}/5\mathbb{Z})^\times$ | 4 |
> | $\Phi_6(x) = 0$ | $\mathbb{Q}(\zeta_6)$ | $(\mathbb{Z}/6\mathbb{Z})^\times$ | 2 |
> | $\Phi_7(x) = 0$ | $\mathbb{Q}(\zeta_7)$ | $(\mathbb{Z}/7\mathbb{Z})^\times$ | 6 |
> | $x^3 - 2 = 0$ | $\mathbb{Q}(\sqrt[3]{2}, \zeta_3)$ | $S_3$ | 6 |
> | $x^4 - 2 = 0$ | $\mathbb{Q}(\sqrt[4]{2}, i)$ | $D_4$ | 8 |

**For §3.2 (étale morphism definition):**

> A morphism of schemes $f : Y \to X$ is *étale* if:
>
> 1. Locally of finite presentation,
>
> 2. Flat, and
>
> 3. Unramified, i.e., $\Omega^1_{Y/X} = 0$.
>
> Equivalently, $f$ is smooth of relative dimension zero. In the affine case $\mathrm{Spec}(A[T]/(g)) \to \mathrm{Spec}(A)$, étale-ness is equivalent to $g'(T)$ being a unit in a suitable localization.

**For §3.4 (pseudo-sign convention):**

> *On Labeling:* We label the two sheets of the $\mathbb{Z}/2\mathbb{Z}$ cover "Sheet 1" and "Sheet 2." These labels are not intrinsic to finite fields — there is no canonical "positive" or "negative" in $\mathbb{F}_p$. What is intrinsic is the $\mathbb{Z}/2\mathbb{Z}$ symmetry interchanging them. A global labeling is possible via the choice of an embedding $L = \mathbb{Q}(\sqrt{2}) \hookrightarrow \mathbb{C}$, which specifies a preferred square root of 2 in each residue field $\mathcal{O}_L/\mathfrak{p}$.

**For Chapter 1, Reason 5:**

> **Reason 5 (revised):** The étale topology's overcoming of the Zariski topology's coarseness is *conceptually analogous* to the Sheaf Neural Network's overcoming of oversmoothing. Both situations illustrate a general principle: mathematical frameworks that are too coarse fail to capture local structure, and both are remedied by enriching the framework with sheaf-theoretic constructions. The specific mathematical mechanisms differ (topology vs. spectrum), but the conceptual parallel is instructive.

**For the title:**

> *Buildings in the Desert: How the Mathematics of Algebraic Geometry Is Entering Deep Learning*

#### 11.4 Summary

Chapter 11 provides a comprehensive map from original passages to refined versions. A reader preparing an annotated edition of Part 1 may use this chapter as a practical guide. The full justifications for each refinement are in Chapters 3–10 of the present notes.

---

### Chapter 12: Reading Guide for Revised Part 1

This final chapter offers a reading guide tailored to different audiences. It recommends which chapters of the present Companion Notes to consult first, based on the reader's mathematical background and the specific questions that may arise from Part 1.

#### 12.1 For the 🏫 Level Reader (High School)

If you are reading Part 1 at the high-school level and want to maintain the intuitive picture without becoming confused by details:

**Recommended:**
- Read Part 1 straight through for the pedagogical picture.
- Do not worry about the present notes at first.
- If questions arise ("why does Part 1 sometimes write $\mathbb{Z}/2\mathbb{Z}$ and sometimes $(\mathbb{Z}/3\mathbb{Z})^\times$?"), consult the short summary in §11.3 of this document.

**Skip:**
- Chapters 4, 5, 6 in their full technical detail. These are for more advanced readers.

#### 12.2 For the 🎓 Level Reader (Undergraduate, First Two Years)

If you have studied linear algebra and calculus but are new to Galois theory and algebraic geometry:

**Recommended:**
- Read Part 1 straight through.
- Then read Chapter 3 of these notes (cyclotomic Galois groups) to understand the naming conventions.
- Read the "Revised Passages" in Chapters 4 and 5 to understand what the careful statements look like.
- Skim Chapters 6–8 for context; return to them after further study.

**Skip:**
- The full proofs and technical equivalences in Chapters 6, 7, 8. Return to these after more coursework.

#### 12.3 For the 📐 Level Reader (Undergraduate, Upper Division)

If you have studied group theory, ring theory, and basic point-set topology:

**Recommended:**
- Read Part 1 straight through.
- Read Chapters 3, 4, 5 of these notes carefully. The distinctions between multiplicative group generators, Galois elements, and Frobenius should be internalized.
- Read Chapter 6 for the precise definition of étale morphisms.
- Read Chapter 8 for the Chebotarev theorem in full.
- Consider Chapter 9 for the conceptual assessment of the Zariski/oversmoothing analogy.

**Optional:**
- Chapter 7 if you are interested in arithmetic geometry.
- Chapter 10 if you are interested in the historical narrative.

#### 12.4 For the 🔬 Level Reader (Graduate)

If you have studied commutative algebra, homological algebra, and basic category theory:

**Recommended:**
- Read Part 1 straight through.
- Read all of Chapters 3–10 of these notes.
- Pay particular attention to:
  - Chapter 4 (the key conceptual distinction);
  - Chapter 6 (étale morphisms in full);
  - Chapter 8 (Chebotarev in full).

**For deeper engagement:**
- Consult the appendices (coming in Draft 5): glossary, notation, exercises, further reading.
- Trace Part 1's citations to the primary literature:
  - Bodnar, Di Giovanni, Chamberlain, Liò, Bronstein, "Neural Sheaf Diffusion" (NeurIPS 2022)
  - Gavranović et al., "Categorical Deep Learning" (ICML 2024)
  - Watanabe, *Algebraic Geometry and Statistical Learning Theory* (Cambridge, 2009)
  - For the mathematical background: Milne's *Étale Cohomology* and Neukirch's *Algebraic Number Theory*.

#### 12.5 For the Reader Preparing an Annotated Edition

If you are preparing an annotated edition of Part 1:

**Step 1:** Use Table 11.2.1–11.2.3 to identify all passages requiring refinement.

**Step 2:** For each passage, consult the corresponding chapter of these notes for the full justification.

**Step 3:** Insert the revised passage (from §11.3) in place of the original.

**Step 4:** Add a note referencing the relevant chapter of the Companion Notes for readers who want the full discussion.

**Step 5:** Preserve the original structure of Part 1 where possible. The pedagogical framework (building, elevators, sky castle) should remain intact; only the mathematical statements need revision.

#### 12.6 For the Reader Preparing to Read the Primary Literature

If you have read Part 1 and now wish to tackle Bodnar et al. (2022), Gavranović et al. (2024), or similar papers:

**Prerequisites to cement:**
- The distinction between generator choice and Galois action (Chapter 4). Without this, the statement "the Galois group acts on $\mu_n$" is confusing.
- The embedding $G \hookrightarrow S_n$ (Chapter 5). This is the framework for all Frobenius computations.
- The precise definition of étale (Chapter 6). This is needed for understanding "étale topology" in SGA 4 or Milne.
- The Chebotarev theorem (Chapter 8). This is used implicitly in many arithmetic-geometric arguments.

**Recommended next readings:**
- Milne, *Étale Cohomology* (1980), Chapter I: formal definitions.
- Neukirch, *Algebraic Number Theory* (1999), Chapter IV: Frobenius elements.
- For SNN/GNN applications: Bodnar et al. (2022); Hansen–Ghrist (2019, 2020).
- For categorical deep learning: Fong–Spivak, *Seven Sketches in Compositionality* (2019); Gavranović (2024).

#### 12.7 On the Status of These Notes

The present Companion Notes are Version 1.0, Draft 4 of 5. Draft 5 will add the appendices (glossary, notation, exercises, further reading, final bibliography) and integrate the four previous drafts into a single document.

Readers are invited to submit corrections and suggestions via the GitHub repository. A Version 2.0 will be prepared in response to feedback, potentially reorganizing the chapter structure based on reader responses.

The author's position, as stated in the Preface, is that the present notes are a companion to Part 1, not a replacement. Part 1 remains a legitimate piece of expository writing, serving its pedagogical purpose. These notes refine, clarify, and extend — they do not repudiate.

#### 12.8 A Closing Remark on the Practice of Refinement

The tradition of publishing supplementary notes alongside a main text has a long history in mathematics. Bourbaki's *Éléments* contains its own historical notes; Hartshorne's *Algebraic Geometry* is supplemented by Liu, Vakil, Görtz–Wedhorn; Hatcher's *Algebraic Topology* has been supplemented by numerous "notes and errata" online. The present Companion Notes situate themselves modestly within this tradition.

The practice reflects a broader intellectual value: the willingness to publish a work knowing that it is imperfect, and then to publish the corrections openly, rather than attempting to create a definitive version before release. This approach acknowledges that mathematical exposition is an ongoing collaboration between author and reader, and that the progressive refinement of written work is itself a form of mathematical activity.

## Appendix A: Glossary

This glossary compiles, for easy reference, the principal terms used in the present Companion Notes. Each entry gives the term, its definition, and a cross-reference to the chapter or section where it is discussed in detail.

---

**Absolute Frobenius.** For a scheme $X$ of characteristic $p > 0$, the absolute Frobenius $F_X : X \to X$ is the identity on the underlying topological space and the $p$-th power map on the structure sheaf: $\mathcal{O}_X \to \mathcal{O}_X$, $f \mapsto f^p$. See also *Frobenius element*, *Relative Frobenius*. Chapter 6 (Example 6.5.4).

**Abelian extension.** A Galois extension $L/K$ whose Galois group $\mathrm{Gal}(L/K)$ is abelian. Cyclotomic extensions $\mathbb{Q}(\zeta_n)/\mathbb{Q}$ are abelian extensions of $\mathbb{Q}$. Chapters 3, 4, 8.

**Algebraic closure.** A field $\overline{K}$ containing $K$ such that every polynomial in $K[x]$ factors completely in $\overline{K}[x]$, and $\overline{K}/K$ is an algebraic extension. Every field has an algebraic closure, unique up to non-canonical isomorphism. Chapter 2, §2.2.

**Artin L-function.** Given a Galois representation $\rho : \mathrm{Gal}(L/K) \to \mathrm{GL}_n(\mathbb{C})$, the Artin L-function $L(s, \rho)$ is an Euler product encoding local information at each prime. Generalizes the Riemann zeta function. Chapter 5.

**Cellular sheaf.** An assignment, to each cell of a CW complex, of a vector space (stalk), together with linear maps between stalks along incidences (restriction maps), satisfying a cocycle condition. Chapter 10, Definition 10.4.1.

**Characteristic.** The smallest positive integer $p$ such that $p \cdot 1 = 0$ in a ring $R$; zero if no such $p$ exists. Finite fields $\mathbb{F}_p$ have characteristic $p$; the rationals $\mathbb{Q}$ have characteristic zero. Chapter 2, §2.2.

**Chebotarev density theorem.** For a Galois extension $L/K$ of number fields with Galois group $G$, the density of primes $p$ of $K$ (unramified in $L$) whose Frobenius conjugacy class is $[C] \subset G$ equals $|C|/|G|$. Chapter 8.

**Cocycle condition.** For a cellular sheaf, the requirement that, for a chain of incidences $\rho \lhd \tau \lhd \sigma$, the composition of restriction maps $\mathcal{F}(\tau \lhd \sigma) \circ \mathcal{F}(\rho \lhd \tau)$ equals the single restriction $\mathcal{F}(\rho \lhd \sigma)$. Chapter 10, Definition 10.4.1.

**Conjugacy class.** In a group $G$, the equivalence class of an element $g$ under the relation $g \sim hgh^{-1}$ for $h \in G$. The set of conjugacy classes of $G$ partitions $G$. In $S_n$, conjugacy classes are determined by cycle type. Chapters 5, 8.

**Cyclotomic field.** For $n \geq 1$, the field $\mathbb{Q}(\zeta_n)$ obtained by adjoining a primitive $n$-th root of unity to $\mathbb{Q}$. It is a Galois extension of degree $\varphi(n)$. Chapter 3.

**Cyclotomic polynomial.** The polynomial $\Phi_n(x)$ whose roots are exactly the primitive $n$-th roots of unity. It has degree $\varphi(n)$ and is irreducible over $\mathbb{Q}$. Chapter 3, Theorem 3.3.1.

**Decomposition group.** For a prime $\mathfrak{P}$ of $\mathcal{O}_L$ in a Galois extension $L/K$, the stabilizer of $\mathfrak{P}$ in $\mathrm{Gal}(L/K)$. For unramified primes, isomorphic to the Galois group of the residue field extension. Chapter 8.

**Degree of a polynomial.** The highest power of the variable appearing with a nonzero coefficient.

**Discriminant (of a polynomial).** For a polynomial $f(x) = \prod_i (x - \alpha_i)$ of degree $n$, the discriminant is $\mathrm{disc}(f) = \prod_{i < j} (\alpha_i - \alpha_j)^2$. It is zero iff $f$ has a repeated root, and its prime divisors are exactly the ramified primes of the splitting field. Chapter 8.

**Étale morphism.** A morphism of schemes $f : Y \to X$ that is flat, unramified, and locally of finite presentation. Equivalently, smooth of relative dimension zero. Chapter 6.

**Étale cohomology.** Cohomology theory for schemes, developed by Grothendieck and his school in the 1960s, using the étale site and étale sheaves. Essential for the proof of the Weil conjectures. Chapters 2, 10.

**Étale topology.** The Grothendieck topology on schemes whose covers are families of étale morphisms $\{U_i \to U\}$ with $\coprod_i U_i \to U$ surjective. Chapter 6.

**Euler's totient function.** For $n \geq 1$, $\varphi(n)$ is the number of integers in $\{1, 2, \ldots, n\}$ coprime to $n$. Used throughout Chapters 3, 4.

**Faithful action.** A group action is *faithful* if only the identity element acts trivially. A Galois group always acts faithfully on its splitting field's generators. Chapter 5.

**Fiber (of a morphism).** For $f : Y \to X$ and $x \in X$, the fiber $Y_x = f^{-1}(x)$, viewed as a scheme over the residue field $\kappa(x)$. Chapter 6.

**Finite presentation.** A morphism $f : Y \to X$ is *locally of finite presentation* if locally $Y = \mathrm{Spec}(A[T_1, \ldots, T_n]/(f_1, \ldots, f_m))$ over $X = \mathrm{Spec}(A)$, with both generators and relations finite. Chapter 6, Definition 6.3.6.

**Finite type.** A morphism $f : Y \to X$ is *locally of finite type* if locally $Y = \mathrm{Spec}(A[T_1, \ldots, T_n]/I)$ over $X = \mathrm{Spec}(A)$, with only the generators required to be finite. Chapter 6.

**Flat morphism.** A morphism $f : Y \to X$ such that every stalk $\mathcal{O}_{Y,y}$ is flat over $\mathcal{O}_{X, f(y)}$. Intuitively: fibers vary continuously in dimension. Chapter 6, Definition 6.3.1.

**Flat module.** An $A$-module $M$ such that tensoring with $M$ preserves exact sequences. Equivalently, $\mathrm{Tor}_1^A(N, M) = 0$ for all $A$-modules $N$. Chapter 6.

**Frobenius element.** For an unramified prime $p$ in a Galois extension $L/K$, the Frobenius element $\mathrm{Frob}_\mathfrak{P}$ (for a prime $\mathfrak{P}$ of $\mathcal{O}_L$ above $p$) is the unique element of $\mathrm{Gal}(L/K)$ acting as $x \mapsto x^{|\kappa(p)|}$ on the residue field. Different $\mathfrak{P}$'s give conjugate Frobenius elements. Chapters 4, 8.

**Galois extension.** A field extension $L/K$ that is normal (contains splitting fields of all irreducibles in $K[x]$ with a root in $L$) and separable. Chapters 3, 5.

**Galois group.** For a Galois extension $L/K$, the group $\mathrm{Gal}(L/K)$ of $K$-algebra automorphisms of $L$. Order equals $[L:K]$. Chapters 3, 4, 5.

**Generator (of a cyclic group).** An element $g$ of a cyclic group $C$ such that every element of $C$ is a power of $g$. A cyclic group of order $n$ has $\varphi(n)$ generators. Chapter 4.

**Grothendieck topology.** A generalization of the notion of topology, consisting of a category (the "site") together with a rule for which families of morphisms count as "covers." Generalizes the open-cover topology by allowing more general morphisms. Chapter 6.

**Homomorphism.** A map between algebraic structures (groups, rings, modules, ...) preserving the structure. The image of a product or sum equals the product or sum of images. Chapters 3, 4.

**Inert prime.** In a Galois extension $L/K$, a prime $p$ of $K$ whose ideal $p\mathcal{O}_L$ remains prime (does not split). Equivalently, Frobenius has full order $|G|$. Chapter 8.

**Irreducible polynomial.** A polynomial $f$ that cannot be factored as a product of two non-constant polynomials in the same ring. Examples: cyclotomic polynomials $\Phi_n(x)$ are irreducible over $\mathbb{Q}$. Chapter 3.

**Kähler differentials.** For a morphism $Y \to X$, the sheaf $\Omega^1_{Y/X}$ encoding "infinitesimal deformations" of $Y$ over $X$. Its vanishing characterizes unramified morphisms. Chapter 6.

**Lattice.** In the sense of order theory: a partially ordered set in which every pair of elements has a supremum and infimum. Used in the theory of Galois closures. Chapter 5.

**L-function.** An analytic function of a complex variable $s$ attached to an arithmetic object (number field, Galois representation, modular form, etc.), generalizing the Riemann zeta function. Chapters 5, 8.

**Local ring.** A commutative ring with a unique maximal ideal. The stalk of the structure sheaf at a point is a local ring. Chapter 2, §2.2.

**Localization.** For a commutative ring $R$ and a multiplicative subset $S \subset R$, the localization $S^{-1}R$ is a ring where elements of $S$ become invertible. Generalizes the construction of the field of fractions. Chapter 2.

**Monomorphism (of schemes).** A morphism $f : Y \to X$ such that the diagonal $\Delta : Y \to Y \times_X Y$ is an isomorphism. Equivalently, for any scheme $Z$, the induced map $\mathrm{Hom}(Z, Y) \to \mathrm{Hom}(Z, X)$ is injective. Chapter 6.

**Multiplicative group.** For a field or ring $R$, the group $R^\times$ of invertible elements under multiplication. For $\mathbb{F}_p$: $\mathbb{F}_p^\times$ is cyclic of order $p-1$. Chapter 2, §2.2.

**Noetherian ring.** A commutative ring in which every ideal is finitely generated. The Hilbert basis theorem implies that if $A$ is Noetherian, then $A[T_1, \ldots, T_n]$ is Noetherian. Chapter 6.

**Open immersion.** A morphism $f : U \to X$ that factors as $U \cong V \hookrightarrow X$ where $V$ is an open subscheme of $X$. Chapter 6.

**Order of a group element.** For an element $g$ of a group $G$, the smallest positive integer $n$ (if it exists) such that $g^n = 1$. Chapter 3.

**Orthogonal group.** $O(d)$, the group of $d \times d$ real matrices $M$ with $M^T M = I$. Used as restriction group in certain Sheaf Neural Network models. Chapter 4.

**p-adic integer.** An element of the ring $\mathbb{Z}_p$, the completion of $\mathbb{Z}$ with respect to the $p$-adic metric. Chapter 2, §2.2.

**Prime ideal.** In a commutative ring $R$, an ideal $\mathfrak{p}$ such that $R/\mathfrak{p}$ is an integral domain. Points of $\mathrm{Spec}(R)$ correspond to prime ideals. Chapter 2, §2.2.

**Primitive root of unity.** An element $\zeta \in \mu_n$ of exact order $n$; equivalently, a generator of $\mu_n$. There are $\varphi(n)$ primitive $n$-th roots of unity. Chapter 3.

**Ramified prime.** In a Galois extension $L/K$, a prime $p$ of $K$ whose factorization in $\mathcal{O}_L$ has repeated factors. Ramified primes are finite in number, contained in the set of primes dividing the discriminant. Chapter 8.

**Residue field.** For a local ring $(R, \mathfrak{m})$, the field $R/\mathfrak{m}$. For a prime ideal $\mathfrak{p}$ of $\mathcal{O}_L$, the residue field is $\mathcal{O}_L/\mathfrak{p}$. Chapter 2, §2.2.

**Restriction map.** For a cellular sheaf on a CW complex, the linear map $\mathcal{F}(\tau \lhd \sigma) : \mathcal{F}(\tau) \to \mathcal{F}(\sigma)$ associated to an incidence $\tau \lhd \sigma$. Chapter 10.

**Scheme.** A locally ringed space $(X, \mathcal{O}_X)$ locally isomorphic to $\mathrm{Spec}(R)$ for commutative rings $R$. The fundamental object of modern algebraic geometry. Chapters 2, 6.

**Section (of a cellular sheaf).** A choice of elements $x_\sigma \in \mathcal{F}(\sigma)$ for each cell $\sigma$, consistent with the restriction maps along incidences. Chapter 10.

**Separable extension.** A field extension $L/K$ such that every element of $L$ is separable over $K$ (its minimal polynomial has distinct roots). All extensions of characteristic-zero fields and of finite fields are separable. Chapter 3.

**Sheaf (cellular).** See *Cellular sheaf*.

**Sheaf (étale).** A functor from the étale site of a scheme to a target category (e.g., abelian groups) satisfying a descent condition. Chapters 2, 6.

**Sheaf Laplacian.** For a cellular sheaf on a graph, a specific linear operator on sections generalizing the graph Laplacian. Used in Sheaf Neural Networks. Chapters 2, 9.

**Sheaf Neural Network (SNN).** A Graph Neural Network architecture using a cellular sheaf structure (stalks + restriction maps) as learnable parameters. Introduced by Bodnar et al. (2022). Chapters 2, 9, 10.

**Smooth morphism.** A flat morphism $f : Y \to X$ locally of finite presentation such that, at each point, the fiber is smooth. Étale morphisms are exactly smooth morphisms of relative dimension zero. Chapter 6.

**Spec.** For a commutative ring $R$, the scheme $\mathrm{Spec}(R)$ whose points are the prime ideals of $R$, with the Zariski topology. Chapter 2.

**Splitting field.** For a polynomial $f \in K[x]$, the smallest extension of $K$ in which $f$ factors as a product of linear factors. Unique up to isomorphism. Chapter 3.

**Stalk.** For a sheaf $\mathcal{F}$ on a topological space or scheme $X$ and a point $x \in X$, the direct limit $\mathcal{F}_x = \varinjlim \mathcal{F}(U)$ over open neighborhoods $U$ of $x$. For a cellular sheaf, the stalk at a cell $\sigma$ is $\mathcal{F}(\sigma)$. Chapter 10.

**Symmetric group.** $S_n$, the group of permutations of $n$ objects. Has order $n!$. Every Galois group of a polynomial of degree $n$ embeds in $S_n$. Chapter 5.

**Topos.** A category of sheaves on a Grothendieck site, or more generally, a Grothendieck topos. Étale topoi are central to modern algebraic geometry. Chapters 2, 10.

**Unramified (of morphism).** A morphism $f : Y \to X$ whose relative differentials $\Omega^1_{Y/X}$ vanish. Equivalently, residue field extensions are finite separable and "no ramification at the level of local rings." Chapter 6.

**Unramified (of prime).** For a Galois extension $L/K$, a prime $p$ of $K$ is unramified in $L$ if its factorization in $\mathcal{O}_L$ has no repeated factors. Chapter 8.

**Weil conjectures.** Four conjectures formulated by André Weil in 1949 concerning the number of solutions of polynomial equations over finite fields. Proved by Dwork (1960), Grothendieck-Deligne (partial), Deligne (1974). Chapters 2, 10.

**Zariski topology.** On a scheme $X$, the topology whose open sets are complements of zero loci of sections of the structure sheaf. For an affine scheme $\mathrm{Spec}(R)$, open sets are $D(f) = \{\mathfrak{p} : f \notin \mathfrak{p}\}$ for $f \in R$. Chapters 2, 9.

---

## Appendix B: Notation

The following symbolic conventions are used throughout these Companion Notes:

**Ordinary mathematical objects:**

- $\mathbb{Z}$: ring of integers.
- $\mathbb{Q}$: field of rational numbers.
- $\mathbb{R}$: field of real numbers.
- $\mathbb{C}$: field of complex numbers.
- $\mathbb{F}_p$: finite field with $p$ elements (where $p$ is prime).
- $\mathbb{F}_q$: finite field with $q = p^n$ elements.
- $\overline{\mathbb{F}}_p$: algebraic closure of $\mathbb{F}_p$.
- $\overline{\mathbb{Q}}$: algebraic closure of $\mathbb{Q}$.
- $\mathcal{O}_L$: ring of integers of a number field $L$.

**Group-theoretic notation:**

- $(\mathbb{Z}/n\mathbb{Z})^\times$: group of units modulo $n$, of order $\varphi(n)$.
- $\mathbb{Z}/n\mathbb{Z}$: cyclic group of order $n$.
- $S_n$: symmetric group on $n$ elements.
- $A_n$: alternating group on $n$ elements.
- $D_n$: dihedral group of order $2n$.
- $F_n$: Frobenius group of order $n$ (various).
- $\mu_n$: group of $n$-th roots of unity.
- $\zeta_n$: a fixed primitive $n$-th root of unity, typically $e^{2\pi i/n}$.
- $\mathrm{Aut}(G)$: automorphism group of the group $G$.
- $\mathrm{Gal}(L/K)$: Galois group of a Galois extension $L/K$.
- $|G|$: order of the group $G$.

**Functions and constants:**

- $\varphi(n)$: Euler's totient function.
- $\Phi_n(x)$: $n$-th cyclotomic polynomial.
- $\mathrm{disc}(f)$: discriminant of a polynomial $f$.

**Ring-theoretic notation:**

- $R^\times$: group of units of a ring $R$.
- $R[x]$: polynomial ring in one variable over $R$.
- $R[[x]]$: formal power series ring.
- $R/I$: quotient ring by an ideal $I$.
- $\mathrm{Spec}(R)$: spectrum of a ring $R$.
- $\mathrm{Spec}(R)_\text{red}$: reduced spectrum.
- $\mathcal{O}_X$: structure sheaf of a scheme $X$.
- $\mathfrak{m}$: maximal ideal of a local ring.
- $\kappa(x)$: residue field at a point $x$.
- $\mathcal{O}_{X,x}$: local ring at a point $x$ of a scheme.

**Scheme-theoretic notation:**

- $X \times_S Y$: fiber product of schemes.
- $\Delta : X \to X \times_S X$: diagonal morphism.
- $\Omega^1_{Y/X}$: sheaf of relative Kähler differentials.
- $\mathbb{A}^n_k$: affine $n$-space over $k$.
- $\mathbb{P}^n_k$: projective $n$-space over $k$.

**Galois-theoretic notation:**

- $\mathrm{Frob}_p$: Frobenius element at prime $p$, defined up to conjugacy.
- $\sigma_k$: the element of $\mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$ sending $\zeta_n \mapsto \zeta_n^k$.
- $[\mathrm{Frob}_p]$: Frobenius conjugacy class.

**Combinatorial notation:**

- $[n] = \{1, 2, \ldots, n\}$.
- $\binom{n}{k}$: binomial coefficient.
- $(a_1 a_2 \cdots a_k)$: $k$-cycle in cycle notation.

**Categorical notation:**

- $\mathrm{Hom}(X, Y)$: morphisms from $X$ to $Y$ in a given category.
- $\mathrm{Fun}(\mathcal{C}, \mathcal{D})$: functors from $\mathcal{C}$ to $\mathcal{D}$.

---

## Appendix C: Exercises and Solutions

This appendix collects exercises of varying difficulty, intended to reinforce the material of the main chapters. Solutions (or solution sketches) are provided at the end.

### C.1 Exercises on Chapter 3 (Cyclotomic Galois Groups)

**Exercise 3.1.** Compute $\Phi_1(x), \Phi_2(x), \Phi_3(x), \Phi_4(x), \Phi_5(x), \Phi_6(x), \Phi_8(x), \Phi_{12}(x)$ explicitly as polynomials in $x$.

**Exercise 3.2.** Prove that $\Phi_n(x)$ has integer coefficients.

**Exercise 3.3.** Prove that $\Phi_n(x)$ is irreducible over $\mathbb{Q}$ for all $n \geq 1$. (Hint: Use the fact that any root of a nontrivial factor must be a primitive $n$-th root of unity, and consider reductions modulo primes.)

**Exercise 3.4.** Determine $[\mathbb{Q}(\zeta_{100}) : \mathbb{Q}]$.

**Exercise 3.5.** Show that $\mathbb{Q}(\zeta_n) \cap \mathbb{R} = \mathbb{Q}(\zeta_n + \zeta_n^{-1})$, a subfield of index 2 in $\mathbb{Q}(\zeta_n)$ (for $n > 2$).

### C.2 Exercises on Chapter 4 (Generators vs. Galois Action)

**Exercise 4.1.** In $\mathbb{F}_{11}$, identify all four generators of $\mu_5 \subset \mathbb{F}_{11}^\times$. Compute the four automorphisms of $\mu_5$ (the Galois-like actions).

**Exercise 4.2.** In $\mathbb{F}_{13}$, determine the order of $3 \in \mathbb{F}_{13}^\times$. Is $3$ a generator of $\mathbb{F}_{13}^\times$?

**Exercise 4.3.** Compute explicitly the action of $\mathrm{Gal}(\mathbb{Q}(\zeta_7)/\mathbb{Q})$ on the 7th roots of unity, listing all six non-trivial elements and their permutations on the six primitive 7th roots.

**Exercise 4.4.** Show that the Galois group of the splitting field of $x^n - a$ (for $a \in \mathbb{Q}^\times$) over $\mathbb{Q}$ is generally *not* cyclic, but is a semidirect product involving $(\mathbb{Z}/n\mathbb{Z})^\times$ and a cyclic group.

### C.3 Exercises on Chapter 5 (Galois Groups as Permutations)

**Exercise 5.1.** For the polynomial $f(x) = x^3 - 3x + 1$, compute the Galois group of its splitting field over $\mathbb{Q}$. Is it $S_3$, $A_3$, or smaller?

**Exercise 5.2.** Prove that the Galois group of $x^4 + 1$ over $\mathbb{Q}$ is isomorphic to the Klein four-group $V_4$, and identify its image in $S_4$.

**Exercise 5.3.** Show that $x^5 - x - 1$ has Galois group $S_5$ over $\mathbb{Q}$. (Hint: Use that $S_5$ is generated by any $5$-cycle and any transposition, and count the cycle structure of Frobenius at small primes.)

**Exercise 5.4.** Let $p$ be prime. Show that if $f(x) \in \mathbb{Q}[x]$ is an irreducible polynomial of degree $p$ with exactly two non-real roots, then $\mathrm{Gal}(f) \cong S_p$.

### C.4 Exercises on Chapter 6 (Étale Morphisms)

**Exercise 6.1.** Verify that the morphism $\mathrm{Spec}(\mathbb{Q}(\sqrt{2})) \to \mathrm{Spec}(\mathbb{Q})$ is étale.

**Exercise 6.2.** Let $k$ be a field and consider the morphism $\mathrm{Spec}(k[y]/(y^2 - x)) \to \mathrm{Spec}(k[x])$. Determine where it is étale and where it fails to be.

**Exercise 6.3.** Show that the Frobenius endomorphism of $\mathrm{Spec}(\mathbb{F}_p[t])$ is flat but not étale.

**Exercise 6.4.** Prove that an étale morphism of schemes is an open map (sends open sets to open sets).

**Exercise 6.5.** Show that the composition of two étale morphisms is étale.

### C.5 Exercises on Chapter 8 (Chebotarev)

**Exercise 8.1.** For the polynomial $x^3 - x - 1$ over $\mathbb{Q}$, compute the Galois group of its splitting field, and verify the Chebotarev density predictions for small primes (up to $p = 50$) by computing the factorization types.

**Exercise 8.2.** Find, among the first 100 primes, the proportion for which $x^2 + 1$ splits (i.e., $p \equiv 1 \pmod 4$). Does your result match the Chebotarev prediction?

**Exercise 8.3.** Show that the Chebotarev density theorem implies Dirichlet's theorem on primes in arithmetic progressions.

### C.6 Exercises on Chapters 9–10 (Analogies and History)

**Exercise 9.1.** Write a short essay (~500 words) comparing the Zariski topology's "coarseness" and the oversmoothing problem in GNNs, being careful to distinguish genuine structural similarities from mere rhetorical analogies.

**Exercise 10.1.** Consult Grothendieck's *Récoltes et Semailles* (chapters relevant to scheme theory) and Deligne's *Weil I* paper. Construct a timeline of key developments from 1950 to 1975 that led to modern étale cohomology. Identify the three most influential papers and explain their contributions.

### C.7 Solutions and Solution Sketches

**Solution to Exercise 3.1 (partial):**

$\Phi_1(x) = x - 1$

$\Phi_2(x) = x + 1$

$\Phi_3(x) = x^2 + x + 1$

$\Phi_4(x) = x^2 + 1$

$\Phi_5(x) = x^4 + x^3 + x^2 + x + 1$

$\Phi_6(x) = x^2 - x + 1$

$\Phi_8(x) = x^4 + 1$

$\Phi_{12}(x) = x^4 - x^2 + 1$

The degree of $\Phi_n$ is $\varphi(n)$.

**Solution to Exercise 3.4:** $[\mathbb{Q}(\zeta_{100}) : \mathbb{Q}] = \varphi(100) = \varphi(4) \cdot \varphi(25) = 2 \cdot 20 = 40$.

**Solution to Exercise 4.1 (sketch):** The generators of $\mu_5 \subset \mathbb{F}_{11}^\times$ are elements of order 5. Computing: $3, 9, 5, 4$ are the four generators (each of order 5). The identification $\zeta_5 \leftrightarrow 3$ (say) gives: $\zeta_5^2 = 9, \zeta_5^3 = 5, \zeta_5^4 = 4$. The four Galois-like automorphisms are $\sigma_k : \zeta_5 \mapsto \zeta_5^k$ for $k = 1, 2, 3, 4$, corresponding in $\mathbb{F}_{11}$ to $x \mapsto x^k$ restricted to $\mu_5$.

**Solution to Exercise 5.3 (sketch):** By Eisenstein-like arguments, $x^5 - x - 1$ is irreducible. Reduce mod 2: $x^5 + x + 1 = (x^2 + x + 1)(x^3 + x^2 + 1)$, giving cycle type $(2,3)$. Reduce mod 3: irreducible, giving cycle type $(5)$. A subgroup of $S_5$ containing a $5$-cycle and a $(2,3)$-cycle is generated by those and equals $S_5$ (since $(2,3)^3 = (2)$, and $S_5$ is generated by a 5-cycle and a transposition).

**Solution to Exercise 6.1 (sketch):** $\mathbb{Q}(\sqrt{2}) = \mathbb{Q}[x]/(x^2 - 2)$. The derivative of $x^2 - 2$ is $2x$, which is nonzero in the quotient (since $x^2 = 2$ implies $x \neq 0$, so $2x \neq 0$ in characteristic 0). Hence the morphism is étale.

**Solution to Exercise 6.3 (sketch):** The Frobenius $F : \mathrm{Spec}(\mathbb{F}_p[t]) \to \mathrm{Spec}(\mathbb{F}_p[t])$ corresponds to the ring map $f \mapsto f^p$. This is flat (easy to check). But $\Omega^1 = \Omega^1_{\mathbb{F}_p[t]/\mathbb{F}_p[t^p]}$ is nonzero: $dt$ is a nontrivial differential. Hence $F$ is flat but not unramified, so not étale.

**Solution to Exercise 8.2 (sketch):** Primes $p \equiv 1 \pmod 4$ among the first 100 primes: $5, 13, 17, 29, 37, 41, 53, 61, 73, 89, 97, 101, 109, 113, 137, 149, 157, 173, 181, 193, 197, 229, 233, 241, 257, 269, 277, 281, 293, 313, 317, 337, 349, 353, 373, 389, 397, 401, 409, 421, 433, 449, 457, 461, 509$ — count these approximately 25 primes out of 100, i.e., about 25%, consistent with the Chebotarev prediction of $1/2 \cdot 1 = 1/2$ of primes split, divided by 2 for unramified primes... actually the Chebotarev prediction is that density $= 1/2$ of unramified primes have $p \equiv 1 \pmod 4$. Among the first 100 primes, approximately half should satisfy this, and counting confirms this.

---

## Appendix D: Further Reading

This appendix provides a structured guide to further reading, organized by level and topic.

### D.1 Preliminary Reading (before Part 1)

For readers who find Part 1 difficult without preparation:

- **Lang, S.** (1975). *Undergraduate Algebra*. Second edition, Springer. An accessible introduction to rings, fields, and elementary Galois theory.
- **Birkhoff, G., & Mac Lane, S.** (1997). *A Survey of Modern Algebra*. Fifth edition, CRC Press. Classical and elegant treatment of algebra.
- **Stewart, I.** (2015). *Galois Theory*. Fourth edition, Chapman & Hall/CRC. Gentle introduction to Galois theory.

### D.2 Galois Theory (Intermediate)

- **Lang, S.** (2002). *Algebra*. Third edition, Springer GTM 211. Standard graduate reference, Chapters V–VI.
- **Milne, J. S.** (2020). *Fields and Galois Theory*. Freely available online at [https://www.jmilne.org/math/CourseNotes/ft.html](https://www.jmilne.org/math/CourseNotes/ft.html). Concise and modern.
- **Weintraub, S. H.** (2009). *Galois Theory*. Second edition, Springer. Classical treatment with many examples.

### D.3 Algebraic Number Theory

- **Neukirch, J.** (1999). *Algebraic Number Theory*. Springer Grundlehren 322. Classic reference, covers Frobenius, Chebotarev, class field theory.
- **Marcus, D.** (1977). *Number Fields*. Springer Universitext. Computational and example-rich.
- **Washington, L. C.** (1997). *Introduction to Cyclotomic Fields*. Second edition, Springer GTM 83. Focused on cyclotomic theory.
- **Cohen, H.** (1993). *A Course in Computational Algebraic Number Theory*. Springer GTM 138. Algorithmic approach.

### D.4 Algebraic Geometry and Schemes

- **Hartshorne, R.** (1977). *Algebraic Geometry*. Springer GTM 52. The standard graduate reference, though notoriously dense.
- **Vakil, R.** (2017). *The Rising Sea: Foundations of Algebraic Geometry*. Freely available. A modern, reader-friendly alternative to Hartshorne.
- **Liu, Q.** (2002). *Algebraic Geometry and Arithmetic Curves*. Oxford Graduate Texts in Mathematics 6. Combines algebraic geometry and number theory.
- **Görtz, U., & Wedhorn, T.** (2010). *Algebraic Geometry I: Schemes with Examples and Exercises*. Vieweg+Teubner. Modern treatment with extensive exercises.
- **Milne, J. S.** (2017). *Algebraic Geometry*. Freely available online. Concise alternative.

### D.5 Étale Cohomology

- **Milne, J. S.** (1980). *Étale Cohomology*. Princeton Mathematical Series 33. Standard reference.
- **Freitag, E., & Kiehl, R.** (1988). *Étale Cohomology and the Weil Conjecture*. Springer. Focused on Weil conjectures.
- **Grothendieck, A., et al.** (1972). *SGA 4: Théorie des topos et cohomologie étale des schémas*. Lecture Notes in Mathematics 269, 270, 305. The original source.
- **Laumon, G., & Moret-Bailly, L.** (2000). *Champs algébriques*. Springer. Extension to algebraic stacks.

### D.6 Sheaf Theory (Cellular and Classical)

- **Curry, J. M.** (2014). *Sheaves, Cosheaves and Applications*. Ph.D. thesis, University of Pennsylvania. Available on arXiv.
- **Hansen, J., & Ghrist, R.** (2019). Toward a spectral theory of cellular sheaves. *Journal of Applied and Computational Topology*, 3(4), 315–358.
- **Hansen, J., & Ghrist, R.** (2020). Opinion dynamics on discourse sheaves. *SIAM Journal on Applied Mathematics*, 81(5), 2033–2060.
- **Bredon, G.** (1997). *Sheaf Theory*. Second edition, Springer GTM 170. Classical treatment.
- **Kashiwara, M., & Schapira, P.** (2006). *Categories and Sheaves*. Springer. Advanced, categorical treatment.

### D.7 Sheaf Neural Networks and Related AI

- **Bodnar, C., Di Giovanni, F., Chamberlain, B. P., Liò, P., & Bronstein, M. M.** (2022). Neural Sheaf Diffusion: A Topological Perspective on Heterophily and Oversmoothing in GNNs. *Advances in Neural Information Processing Systems*, 35.
- **Barbero, F., Bodnar, C., de Ocáriz Borde, H. S., Bronstein, M., Veličković, P., & Liò, P.** (2022). Sheaf Attention Networks. *NeurIPS 2022 Workshop on Learning on Graphs and Beyond*.
- **Gavranović, B., Lessard, P., Dudzik, A., von Glehn, T., Araújo, J. G. M., & Veličković, P.** (2024). Categorical Deep Learning: An Algebraic Theory of Architectures. *International Conference on Machine Learning*.
- **Fong, B., & Spivak, D. I.** (2019). *Seven Sketches in Compositionality: An Invitation to Applied Category Theory*. Cambridge University Press.
- **Velickovic, P.** (2023). Everything is connected: Graph neural networks. *Current Opinion in Structural Biology*, 79, 102538.

### D.8 Singular Learning Theory

- **Watanabe, S.** (2009). *Algebraic Geometry and Statistical Learning Theory*. Cambridge Monographs on Applied and Computational Mathematics. Cambridge University Press.
- **Watanabe, S.** (2018). *Mathematical Theory of Bayesian Statistics*. Chapman & Hall/CRC. Practical companion to the 2009 book.
- **Lau, E., Murfet, D., & Wei, S.** (2023). Quantifying Degeneracy in Singular Models via the Learning Coefficient. arXiv:2308.12108.

### D.9 Historical and Philosophical Readings

- **Grothendieck, A.** (1985–1987). *Récoltes et Semailles*. Unpublished manuscript, widely available. Autobiographical reflection on mathematics and scheme theory.
- **Cartier, P.** (2001). A mad day's work: From Grothendieck to Connes and Kontsevich. *Bulletin of the American Mathematical Society*, 38(4), 389–408.
- **Jackson, A.** (2004). Comme Appelé du Néant: As If Summoned from the Void: The Life of Alexandre Grothendieck. *Notices of the AMS*, 51(4), 1038–1056; (9), 1196–1212.
- **Dieudonné, J.** (1985). *History of Algebraic Geometry*. Wadsworth. Classical survey.

### D.10 Online Resources

- **The Stacks Project.** [https://stacks.math.columbia.edu](https://stacks.math.columbia.edu). Living encyclopedia of algebraic geometry.
- **nLab.** [https://ncatlab.org](https://ncatlab.org). Categorical perspective on mathematics.
- **J. S. Milne's Course Notes.** [https://www.jmilne.org/math/](https://www.jmilne.org/math/). Excellent notes on number theory, algebraic geometry, and related topics.
- **MathOverflow.** [https://mathoverflow.net](https://mathoverflow.net). Q&A for research-level mathematics.

---

## Consolidated Bibliography

This bibliography combines all references cited in Drafts 1 through 5 of the Companion Notes.

Artin, E. (1924). Über eine neue Art von L-Reihen. *Hamburger Abhandlungen*, 3, 89–108.

Artin, M., & Mazur, B. (1969). *Étale Homotopy*. Lecture Notes in Mathematics 100. Springer.

Atiyah, M. F., & Macdonald, I. G. (1969). *Introduction to Commutative Algebra*. Addison-Wesley.

Barbero, F., Bodnar, C., de Ocáriz Borde, H. S., Bronstein, M., Veličković, P., & Liò, P. (2022). Sheaf Attention Networks. *NeurIPS 2022 Workshop*.

Bodnar, C., Di Giovanni, F., Chamberlain, B. P., Liò, P., & Bronstein, M. M. (2022). Neural Sheaf Diffusion: A Topological Perspective on Heterophily and Oversmoothing in GNNs. *NeurIPS 2022*.

Birkhoff, G., & Mac Lane, S. (1997). *A Survey of Modern Algebra*. Fifth edition, CRC Press.

Bredon, G. (1997). *Sheaf Theory*. Second edition, Springer GTM 170.

Cartier, P. (2001). A mad day's work: From Grothendieck to Connes and Kontsevich. *Bulletin of the American Mathematical Society*, 38(4), 389–408.

Chebotarev, N. G. (1926). Die Bestimmung der Dichtigkeit einer Menge von Primzahlen, welche zu einer gegebenen Substitutionsklasse gehören. *Mathematische Annalen*, 95, 191–228.

Cohen, H. (1993). *A Course in Computational Algebraic Number Theory*. Springer GTM 138.

Curry, J. M. (2014). *Sheaves, Cosheaves and Applications*. PhD thesis, University of Pennsylvania. Available on arXiv.

Deligne, P. (1974). La conjecture de Weil I. *Publications Mathématiques de l'IHÉS*, 43, 273–307.

Dieudonné, J. (1985). *History of Algebraic Geometry*. Wadsworth.

Faltings, G. (1983). Endlichkeitssätze für abelsche Varietäten über Zahlkörpern. *Inventiones Mathematicae*, 73(3), 349–366.

Fong, B., & Spivak, D. I. (2019). *Seven Sketches in Compositionality: An Invitation to Applied Category Theory*. Cambridge University Press.

Freitag, E., & Kiehl, R. (1988). *Étale Cohomology and the Weil Conjecture*. Springer.

Gavranović, B., Lessard, P., Dudzik, A., von Glehn, T., Araújo, J. G. M., & Veličković, P. (2024). Categorical Deep Learning: An Algebraic Theory of Architectures. *ICML 2024*.

Görtz, U., & Wedhorn, T. (2010). *Algebraic Geometry I: Schemes with Examples and Exercises*. Vieweg+Teubner.

Grothendieck, A., & Dieudonné, J. (1960–1967). *Éléments de Géométrie Algébrique* (EGA). *Publications Mathématiques de l'IHÉS*, multiple volumes.

Grothendieck, A., et al. (1972). *SGA 4: Théorie des topos et cohomologie étale des schémas*. Lecture Notes in Mathematics 269, 270, 305.

Grothendieck, A. (1985–1987). *Récoltes et Semailles*. Unpublished manuscript.

Hansen, J., & Ghrist, R. (2019). Toward a spectral theory of cellular sheaves. *Journal of Applied and Computational Topology*, 3(4), 315–358.

Hansen, J., & Ghrist, R. (2020). Opinion dynamics on discourse sheaves. *SIAM Journal on Applied Mathematics*, 81(5), 2033–2060.

Hartshorne, R. (1977). *Algebraic Geometry*. Springer GTM 52.

Jackson, A. (2004). Comme Appelé du Néant. *Notices of the AMS*, 51(4), 1038–1056; (9), 1196–1212.

Kashiwara, M., & Schapira, P. (2006). *Categories and Sheaves*. Springer.

Lang, S. (1975). *Undergraduate Algebra*. Second edition, Springer.

Lang, S. (1994). *Algebraic Number Theory*. Second edition, Springer GTM 110.

Lang, S. (2002). *Algebra*. Third edition, Springer GTM 211.

Lau, E., Murfet, D., & Wei, S. (2023). Quantifying Degeneracy in Singular Models via the Learning Coefficient. arXiv:2308.12108.

Laumon, G., & Moret-Bailly, L. (2000). *Champs algébriques*. Springer.

Liu, Q. (2002). *Algebraic Geometry and Arithmetic Curves*. Oxford Graduate Texts in Mathematics 6.

Marcus, D. (1977). *Number Fields*. Springer Universitext.

Milne, J. S. (1980). *Étale Cohomology*. Princeton Mathematical Series 33.

Milne, J. S. (2017). *Algebraic Geometry*. Freely available online.

Milne, J. S. (2020). *Class Field Theory* (v4.03). Freely available online.

Milne, J. S. (2020). *Fields and Galois Theory* (v5.10). Freely available online.

Neukirch, J. (1999). *Algebraic Number Theory*. Springer Grundlehren 322.

Serre, J.-P. (1955–1956). Faisceaux algébriques cohérents. *Annals of Mathematics*, 61, 197–278.

Serre, J.-P. (1973). *A Course in Arithmetic*. Springer GTM 7.

Serre, J.-P. (1989). *Lectures on the Mordell–Weil Theorem*. Aspects of Mathematics E15. Vieweg.

Stewart, I. (2015). *Galois Theory*. Fourth edition, Chapman & Hall/CRC.

Vakil, R. (2017). *The Rising Sea: Foundations of Algebraic Geometry*. Freely available.

Veličković, P. (2023). Everything is connected: Graph neural networks. *Current Opinion in Structural Biology*, 79, 102538.

Washington, L. C. (1997). *Introduction to Cyclotomic Fields*. Second edition, Springer GTM 83.

Watanabe, S. (2009). *Algebraic Geometry and Statistical Learning Theory*. Cambridge.

Watanabe, S. (2018). *Mathematical Theory of Bayesian Statistics*. Chapman & Hall/CRC.

Weil, A. (1946). *Foundations of Algebraic Geometry*. AMS Colloquium Publications 29.

Weintraub, S. H. (2009). *Galois Theory*. Second edition, Springer.

Zariski, O. (1946). Algebraic foundations of algebraic geometry. Chapter 5 of *Collected Papers*, vol. 1.

---

## Subject Index

*The index below is a selective guide to the main topics of the Companion Notes. Page numbers are not provided; topics are referenced by chapter.*

**A**

abelian extension, 3, 4, 8
absolute Frobenius, 6, 10
affine scheme, 2, 6
algebraic closure, 2
algebraic geometry, historical perspective on, 10
Artin L-function, 5, 8
Artin reciprocity, 8

**B**

Bodnar–Di Giovanni–Chamberlain–Liò–Bronstein, 4, 10
Bourbaki tradition, Preface, 12
Brauer induction, 8

**C**

Category theory, Preface, 10
cellular sheaf, definition of, 10
Chebotarev density theorem, 5, 8
classical algebraic geometry, 10
cohomology, étale, 2, 10
conjugacy class, 5, 8
cyclotomic field, 3
cyclotomic polynomial, 3

**D**

Dedekind, 3
Dedekind zeta function, 8
degree of polynomial, 2, 3
Deligne, 10
density, natural vs. Dirichlet, 8
Dirichlet's theorem on APs, 8
discriminant, 8

**E**

eigenvalue of adjacency matrix, 9
Eisenstein criterion, 5
embedding, complex, 7
EGA, 6, 10
étale cohomology, 2, 10
étale morphism, 6
étale topology, 6
Euler's totient, 3, 4

**F**

Faltings, 10
fiber, 6
finite field, 2, 4
finite presentation, 6
finite type, 6
flat morphism, 6
Frobenius element, 4, 5, 8
Frobenius group, 4, 5

**G**

Galois group, general principles, 3, 4, 5
Galois representation, 4, 5, 8
Gavranović et al., 10
generator of cyclic group, 4
Grothendieck topology, 6
Grothendieck's EGA, 6, 10
Grothendieck's SGA, 10

**H**

Hartshorne, 6, 10
Hensel's lemma, 3
Hilbert basis theorem, 6
homomorphism, 3, 4

**I**

inert prime, 8
irreducible polynomial, 3, 5

**K**

Kähler differentials, 6
Klein four-group, 5

**L**

lattice of subfields, 5
L-function, 5, 8
Lang, 3, 5, 8
local ring, 2, 6
localization, 2, 6

**M**

Milne, 6, 10
minimal polynomial, 3, 5
monomorphism (of schemes), 6
multiplicative group, 4

**N**

Neukirch, 4, 8
Noetherian, 6

**O**

open immersion, 6
orbit (of Galois action), 4
orthogonal group, 4
oversmoothing, 9

**P**

$p$-adic integer, 2
Part 1, references to various sections, passim
permutation group, 5
prime ideal, 2
primitive root of unity, 3
proof sketch of Chebotarev, 8

**R**

ramified prime, 5, 8
relative Frobenius, 10
residue field, 2, 6, 8
restriction map, 10
Riemann surface, 10

**S**

scheme, 2, 6
Schemeskins theorem, 5
section, 10
separable extension, 3, 5
sheaf, cellular, 10
sheaf, étale, 2, 10
Sheaf Neural Network (SNN), 2, 4, 9, 10
smooth morphism, 6
splitting field, 3, 5
stalk, 10
symmetric group, 5

**T**

topological space, 2, 9
topos, 2, 10

**U**

unramified morphism, 6
unramified prime, 5, 8

**V**

van der Waerden, 5

**W**

Watanabe, Singular Learning Theory, 1, 2
Weil conjectures, 2, 10

**Z**

Zariski topology, 6, 9

---

## Conclusion and Prospectus

The present Companion Notes, in their current form (Drafts 1 through 5), provide a comprehensive refinement of *Buildings in the Desert — Part 1*. Covering the principal mathematical simplifications of Part 1, supplying the corresponding precise formulations, and offering a reading guide for diverse audiences, these notes aim to serve both as a self-contained reference and as a companion to Part 1 itself.

The author anticipates that a future edition of Part 1 — if and when prepared — will incorporate many of the refinements discussed here. Such incorporation need not be total: some refinements may be judged inappropriate for a pedagogical text, while others may naturally be absorbed as clarifying remarks or footnotes. The separation of Part 1 (pedagogical) from the Companion Notes (technical supplement) is not a defect but a feature: it preserves two distinct styles of mathematical exposition, each appropriate to its intended audience.

The tradition of publishing companion texts alongside principal works is, as noted in the Preface, a venerable one in mathematics. The present notes aspire to contribute modestly to that tradition.

The author thanks all readers who will, in due course, suggest further refinements through the GitHub repository. The intention is that Version 2.0 of these notes will reflect such collective input, progressing toward a mature text over time.

---

## Final Remarks

These Companion Notes are published alongside the article *Buildings in the Desert — Part 1*, which was originally published on Zenn at [https://zenn.dev/etalecohomology/articles/e65f08b5ba899e](https://zenn.dev/etalecohomology/articles/e65f08b5ba899e) on 15 March 2026.

The notes are offered in the spirit of intellectual honesty: Part 1 is a work of pedagogical exposition, which necessarily simplifies for accessibility; the present supplement refines those simplifications for readers who wish to pass to the primary mathematical literature.

Corrections and suggestions are warmly welcomed via the GitHub Issues interface.

---

*Total length: approximately 25,500 words.*

*Author: Étale Cohomology*

*Version 1.0, April 2026*

*License: CC BY 4.0*

*Canonical source of the main article: [https://zenn.dev/etalecohomology/articles/e65f08b5ba899e](https://zenn.dev/etalecohomology/articles/e65f08b5ba899e)*
