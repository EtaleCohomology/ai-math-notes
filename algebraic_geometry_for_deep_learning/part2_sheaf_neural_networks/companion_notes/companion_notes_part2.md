# Companion Notes to *Buildings in the Desert — Part 2*

## Mathematical Precision and Pedagogical Simplification

### A Technical Supplement at the Graduate Textbook Level

---

**Author:** Étale Cohomology  
**Version:** 1.0 (April 2026)  
**License:** CC BY 4.0  
**Companion to:** [*Buildings in the Desert — Part 2*](https://zenn.dev/etalecohomology/articles/286acd9ab58a01) (originally published on Zenn, 15 March 2026)  
**Repository:** [ai-math-notes/buildings_in_the_desert](https://github.com/EtaleCohomology/ai-math-notes)

---

## Preface

The article *Buildings in the Desert — Part 2: Étale Sheaves, Category Theory, and Sheaf Neural Networks* was originally published on Zenn on 15 March 2026. Whereas Part 1 laid out the landscape of schemes, the étale topology, and cyclotomic Galois groups, Part 2 ascends further. It introduces the profinite structure of the absolute Galois group, the equivalence between lisse $\ell$-adic étale sheaves and continuous Galois representations, the $p$-adic numbers and Hensel's lemma, the Weil conjectures together with Deligne's resolution, the Taniyama–Shimura–Wiles theorem, and — finally — Sheaf Neural Networks, Sheaf Attention Networks, and Watanabe's Singular Learning Theory.

This ascent, accomplished in a few dozen pages, is possible only because the exposition is again pedagogical. As in Part 1, the four-tier structure (🏫 high-school, 🎓 undergraduate, 📐 junior/senior, 🔬 graduate) permits the author to speak at several levels simultaneously. The cost is the same: metaphors stand in for proofs, representative examples stand in for general theorems, and occasional imprecisions creep in where the pedagogical picture and the mathematical reality diverge.

The present supplement is, as with its companion to Part 1, the author's deliberate response to that cost. It identifies the passages of Part 2 in which pedagogical simplification departs from the precise formulation; it explains, at a level suitable for advanced undergraduate and graduate readers, what the precise formulation is; it supplies proofs, examples, and counterexamples; and it proposes revised wording.

The refinements collected here are of a somewhat different character from those of Part 1. Part 1 was concerned principally with elementary Galois theory and scheme theory, subjects in which the gap between pedagogy and research is narrow and well-mapped; the refinements could therefore take the form of small, local corrections. Part 2 ventures into deeper country — profinite topology, $p$-adic Hodge theory, the Langlands program, the geometry of singular loss landscapes — where the gap is wider and the refinements must sometimes be substantial rather than local. The reader will accordingly find that several chapters here are longer and more technical than the corresponding chapters in the Part 1 notes.

As before, the present document is neither an erratum nor a repudiation. Part 2 remains, in the author's judgment, a legitimate piece of expository writing, and the pedagogical devices it employs — the "lasers from the sky castle," the "infinite underground floors of a $p$-adic building," the "miraculous match between two castles" — are, within their intended audience, illuminating. The supplement exists so that readers who wish to pass from the metaphor to the mathematics need not do so unaccompanied.

*— The author, April 2026*

---

## Introduction

### The Widening Gap

In Part 1, the pedagogical simplifications concerned matters — cyclotomic Galois groups, étale morphisms between affine schemes, the finite-field analogue of the Frobenius — in which the distance between the metaphor and the rigorous formulation is small. A reader who accepts the "elevator" picture of the Galois group of $x^5 - 1$ will find, on consulting Lang, that the picture is essentially correct and requires only modest adjustment to become precise.

Part 2 is different. Here the metaphors carry the reader into a more rarefied atmosphere, and the rigorous formulations that await — the profinite topology of $G_{\mathbb{Q}}$, the sheaf–representation equivalence, $\ell$-adic cohomology, the modularity of elliptic curves, the Real Log Canonical Threshold of a singular learning machine — are correspondingly more demanding. A reader who accepts, without qualification, that "Frobenius elements are dense in the absolute Galois group" will find, on consulting Neukirch or Milne, that the statement as quoted is not quite what the Chebotarev density theorem says; it is, rather, a slight compression of the true statement, and the compression has consequences when one attempts to work with the theorem in examples.

The purpose of these notes is to close the resulting gap. Each chapter below isolates a specific simplification, explains what was elided, supplies the rigorous replacement with references to the standard literature, and — where appropriate — proposes a revised passage.

### Classification of Refinements

As in the companion notes to Part 1, we classify the refinements into three tiers.

**High-priority refinements** (Chapters 3–6) concern matters whose uncorrected presentation would, in the author's judgment, cause substantive difficulty when the reader consults the primary literature. The most important of these is the treatment, in §3.7 of Part 2, of Frobenius elements inside the absolute Galois group $G_{\mathbb{Q}}$. Part 2 states that "Frobenius elements are dense in $G_{\mathbb{Q}}$"; the precise statement, as given by Chebotarev, is that Frobenius *conjugacy classes* are equidistributed with respect to Haar measure, and that a specific element $\mathrm{Frob}_p \in G_{\mathbb{Q}}$ is defined only up to conjugacy (and requires the choice of a prime of $\overline{\mathbb{Q}}$ above $p$). This distinction is easy to miss on a first reading and critical when reading the literature on Galois representations.

**Medium-priority refinements** (Chapters 7–9) concern definitions that Part 2 stated imprecisely for pedagogical reasons. The statement of the sheaf–representation equivalence, the description of Fontaine's period rings, the handling of Hensel's lemma, and the formulation of Watanabe's free energy formula all fall into this category. Each is correct in outline but requires adjustment to be usable in research.

**Low-priority refinements** (Chapters 10–11) concern matters of historical attribution, bibliographic emphasis, and the precise division of credit for landmark theorems. Part 2 writes, for instance, that "Wiles (1995) proved Fermat's Last Theorem"; this is true, but the complete statement of modularity for all rational elliptic curves was established only in 2001 by Breuil, Conrad, Diamond, and Taylor, and the reduction of Fermat's Last Theorem to modularity was accomplished earlier by Ribet (1986). Such refinements do not affect mathematical substance, but they affect the reader's historical orientation and are included for completeness.

### How to Use This Document

Each refinement follows the standard structure established in the Part 1 notes:

1. **Original Statement.** The passage from Part 2 is reproduced verbatim.
2. **Nature of the Simplification.** The pedagogical purpose is identified, and the precise content of the elision is diagnosed.
3. **Precise Formulation.** The mathematical content is restated with full rigor.
4. **Discussion.** Proofs, examples, counterexamples, and references are supplied.
5. **Revised Passage.** A proposed rewording is offered, which the reader may adopt, adapt, or reject.

The reader who has already read the Part 1 notes will find the format familiar. The reader approaching this document first is advised to begin with the Part 1 notes, since some of the material here — notably Chapters 3 and 5 — builds on the refinements introduced there.

---

## Part I: Foundations

### Chapter 1: Scope and Methodology

#### 1.1 Relation to the Part 1 Notes

The present notes are conceived as a direct continuation of the Companion Notes to Part 1. Readers are assumed to have at least glanced at that volume, particularly at its Chapters 3–5 (on cyclotomic Galois groups and the distinction between generators of multiplicative groups and Galois actions), since Part 2 and the present notes build directly on that material.

In particular, Chapter 3 below — concerning Frobenius elements and the Chebotarev density theorem — presupposes that the reader has internalised the distinction, stressed in the Part 1 notes, between the element $\sigma_k \in \mathrm{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q})$ defined by $\zeta_n \mapsto \zeta_n^k$ and the "$k$-th power" operation on a cyclic group more generally. The two are isomorphic in a precise sense, but they are not the same object, and readers who have not worked through that distinction will find the profinite version of it (for $G_{\mathbb{Q}}$ rather than for a finite cyclotomic group) doubly confusing.

#### 1.2 Prerequisites

The reader of these notes is assumed to be familiar with:

1. The content of Part 1 and its companion notes. Familiarity with cyclotomic Galois theory, the statement of the étale morphism, and the finite-field Frobenius is taken for granted.

2. Point-set topology at the level of Munkres (2000) or equivalent: topological spaces, continuous maps, compactness, Hausdorffness, connectedness, projective (inverse) limits of topological spaces.

3. Basic commutative algebra: rings, ideals, localization, completion, the structure of Noetherian rings. Atiyah–Macdonald (1969) suffices.

4. Basic algebraic number theory: valuations, local fields, unramified and ramified extensions, the decomposition group, the inertia group. Neukirch (1999), Chapter II, §§1–9 is the standard reference.

5. Basic category theory: categories, functors, natural transformations, adjunctions, limits and colimits, representable functors. Mac Lane (1998) is the classical reference; Leinster (2014) is a gentler modern alternative.

6. Some familiarity with the statement of the Weil conjectures and the Langlands philosophy at the level of a good survey article would be useful, but is not strictly required.

Familiarity with the formalism of étale cohomology in the derived sense, with perfectoid spaces, or with the construction of Fontaine's period rings, would be helpful but is not assumed. These are discussed as they arise.

#### 1.3 Notation

We adopt the notational conventions of the Part 1 notes (see §2.2 there). The additional notation for Part 2 is:

- $G_{\mathbb{Q}} = \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$ denotes the absolute Galois group of $\mathbb{Q}$, viewed as a profinite group.
- $G_{\mathbb{Q}, S}$ denotes the Galois group of the maximal extension of $\mathbb{Q}$ unramified outside a finite set $S$ of primes (and the infinite place, where relevant).
- $\mathbb{Q}_p$ denotes the field of $p$-adic numbers; $\mathbb{Z}_p$ the ring of $p$-adic integers.
- $\mathbb{Q}_\ell$, $\mathbb{Z}_\ell$: the analogous local field and ring at the prime $\ell$ (used in the $\ell$-adic setting, to avoid confusion with a "moving" residue-characteristic prime $p$).
- $|{-}|_p$ denotes the $p$-adic absolute value, normalised so that $|p|_p = 1/p$.
- $\mu_n$ denotes, as before, the group of $n$-th roots of unity in a fixed algebraic closure.
- $\mathrm{Frob}_p \in G_{\mathbb{Q}}$ denotes *any* choice of Frobenius element at a prime $p$ unramified in the relevant extension. We write $[\mathrm{Frob}_p]$ for the associated conjugacy class when we wish to emphasise its canonical nature.
- $\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}})$ denotes the category of lisse $\ell$-adic étale sheaves on a scheme $X$.
- $\mathrm{Rep}^{\mathrm{cont}}_{\mathbb{Q}_\ell}(\pi_1^{\mathrm{\acute{e}t}}(X))$ denotes the category of continuous finite-dimensional $\mathbb{Q}_\ell$-representations of the étale fundamental group $\pi_1^{\mathrm{\acute{e}t}}(X)$.
- $H^i_{\mathrm{\acute{e}t}}(X, \mathcal{F})$ denotes the $i$-th étale cohomology of a scheme $X$ with coefficients in a sheaf $\mathcal{F}$.
- $T_\ell(E) = \varprojlim_n E[\ell^n]$ denotes the $\ell$-adic Tate module of an elliptic curve $E$.
- For a cellular sheaf $\mathcal{F}$ on a graph $G$, we write $\mathcal{F}(v)$ for the stalk at a vertex $v$ and $\mathcal{F}_{v \trianglelefteq e} : \mathcal{F}(v) \to \mathcal{F}(e)$ for the restriction map along an incidence $v \trianglelefteq e$.
- $\Delta_{\mathcal{F}} = \delta_{\mathcal{F}}^\top \delta_{\mathcal{F}}$ denotes the sheaf Laplacian associated with $\mathcal{F}$.
- $\lambda$ denotes, in the SLT context, the Real Log Canonical Threshold of a statistical model.

#### 1.4 Conventions

Unless stated otherwise:

- All rings are commutative and unital.
- All topological groups are Hausdorff.
- All schemes are assumed Noetherian and separated.
- "Profinite" means "compact, Hausdorff, totally disconnected," or equivalently "projective limit of finite discrete groups."
- For a profinite group $G$ acting on a topological space or $\mathbb{Q}_\ell$-vector space, "continuous" means continuous in the profinite topology on $G$ and the $\ell$-adic topology on the target.

---

## Part II: High-Priority Refinements

### Chapter 2: The Absolute Galois Group and Its Topology

This chapter addresses §3.7 of Part 2, concerning the profinite structure of $G_{\mathbb{Q}}$. The exposition in Part 2 at the 📐 (junior/senior) level is essentially correct but compresses several technical points that a reader entering the research literature on Galois representations will need to understand precisely.

#### 2.1 The Original Statement

The following passage appears in §3.7 of Part 2:

> The absolute Galois group $G_{\mathbb{Q}} = \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$ is a profinite group (projective limit of finite groups):
> $$G_{\mathbb{Q}} = \varprojlim_{K/\mathbb{Q} \text{ finite Galois}} \mathrm{Gal}(K/\mathbb{Q}).$$
> It carries the **profinite (Krull) topology**: compact, Hausdorff, totally disconnected.

A few lines later, the article continues:

> "Totally disconnected yet continuous?" The "continuity" of a profinite group is different from that of the real line.

#### 2.2 Nature of the Simplification

The passage is correct, but it juxtaposes two terms — "totally disconnected" and "continuous" — in a way that can puzzle a reader meeting profinite groups for the first time. The puzzlement is compounded by the earlier use of the phrase "discrete yet connected" in the same section.

Three clarifications are in order.

**First**, "profinite" and "continuous" are orthogonal notions. Profinite describes the *group itself*: it is a compact, Hausdorff, totally disconnected topological group obtained as an inverse limit of finite groups. Continuous, in the phrase "continuous $\ell$-adic representation $\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$," describes the *representation*: $\rho$ is continuous with respect to the profinite topology on $G_{\mathbb{Q}}$ and the $\ell$-adic topology on $\mathrm{GL}_n(\mathbb{Q}_\ell)$. The continuity in question is a property of the homomorphism, not of the source group.

**Second**, the phrase "totally disconnected yet continuous" in Part 2 appears to be a rhetorical device intended to dispel the reader's expectation that "continuous" should entail "connected" (as it does for $\mathbb{R}$). The phrasing can, however, be read as claiming that $G_{\mathbb{Q}}$ is somehow "continuous" in its own right, which is not quite what is meant. A more accurate paraphrase: "$G_{\mathbb{Q}}$ is totally disconnected, yet one can make precise sense of continuous homomorphisms out of it."

**Third**, the equation
$$G_{\mathbb{Q}} = \varprojlim_{K/\mathbb{Q} \text{ finite Galois}} \mathrm{Gal}(K/\mathbb{Q})$$
is correct but deserves comment. The inverse limit is taken over the directed system of finite Galois subextensions $K/\mathbb{Q}$ of $\overline{\mathbb{Q}}/\mathbb{Q}$, with transition maps given by restriction $\mathrm{Gal}(K'/\mathbb{Q}) \twoheadrightarrow \mathrm{Gal}(K/\mathbb{Q})$ whenever $K \subseteq K'$. The resulting topological group has a neighbourhood basis of the identity given by the open normal subgroups $\mathrm{Gal}(\overline{\mathbb{Q}}/K)$ as $K$ runs over finite Galois extensions.

#### 2.3 Precise Formulation

**Definition 2.3.1** (Profinite group). A topological group $G$ is *profinite* if it is isomorphic, as a topological group, to the inverse limit of a directed inverse system of finite discrete groups. Equivalently (a theorem), $G$ is profinite if and only if it is compact, Hausdorff, and totally disconnected.

**Theorem 2.3.2** (Krull, 1928). *Let $L/K$ be an arbitrary (possibly infinite) Galois extension of fields. Then $\mathrm{Gal}(L/K)$ is a profinite group with respect to the Krull topology, in which a neighbourhood basis of the identity is given by the subgroups $\mathrm{Gal}(L/F)$ where $F/K$ ranges over finite Galois subextensions of $L/K$.*

*Proof.* See Neukirch (1999), Chapter IV, §1, Theorem 1.6. $\square$

**Corollary 2.3.3.** *$G_{\mathbb{Q}} = \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$ is a profinite group with the profinite topology.*

**Proposition 2.3.4** (Basic topological properties of $G_{\mathbb{Q}}$). *The group $G_{\mathbb{Q}}$ satisfies:*

- *(i)* $G_{\mathbb{Q}}$ *is compact Hausdorff.*
- *(ii)* $G_{\mathbb{Q}}$ *is totally disconnected: every connected component consists of a single point.*
- *(iii)* $G_{\mathbb{Q}}$ *admits a unique Haar probability measure, invariant under both left and right translation.*
- *(iv)* $G_{\mathbb{Q}}$ *is uncountable and has cardinality* $2^{\aleph_0}$.
- *(v) The open subgroups of $G_{\mathbb{Q}}$ are precisely the subgroups $\mathrm{Gal}(\overline{\mathbb{Q}}/K)$ for $K/\mathbb{Q}$ finite.*

**Definition 2.3.5** (Continuous $\ell$-adic representation). Let $\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$ be a group homomorphism. We say $\rho$ is *continuous* if it is continuous with respect to the profinite topology on $G_{\mathbb{Q}}$ and the $\ell$-adic topology on $\mathrm{GL}_n(\mathbb{Q}_\ell)$ (as an open subset of $M_n(\mathbb{Q}_\ell) \cong \mathbb{Q}_\ell^{n^2}$).

**Proposition 2.3.6.** *Let $\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$ be continuous. Then:*

- *(i) The image* $\rho(G_{\mathbb{Q}})$ *is contained in* $\mathrm{GL}_n(\mathcal{O})$ *for some $\mathbb{Z}_\ell$-order $\mathcal{O} \subseteq M_n(\mathbb{Q}_\ell)$. Equivalently, $\rho$ is conjugate to a representation valued in $\mathrm{GL}_n(\mathbb{Z}_\ell)$.*
- *(ii) For each $n \geq 1$, the reduction $\rho_n : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Z}/\ell^n\mathbb{Z})$ factors through a finite quotient $\mathrm{Gal}(K_n/\mathbb{Q})$ for some finite Galois extension $K_n/\mathbb{Q}$.*

*Proof.* (i) The image of a compact set under a continuous map is compact; the compact subgroups of $\mathrm{GL}_n(\mathbb{Q}_\ell)$ are precisely those contained in a conjugate of $\mathrm{GL}_n(\mathbb{Z}_\ell)$ (see Serre, *Abelian $\ell$-adic Representations and Elliptic Curves*, §IV.1). (ii) The kernel of the reduction mod $\ell^n$ is an open subgroup of $\mathrm{GL}_n(\mathbb{Z}_\ell)$, hence its preimage under $\rho$ is an open normal subgroup of $G_{\mathbb{Q}}$. $\square$

#### 2.4 Discussion

The topological structure of $G_{\mathbb{Q}}$ is simultaneously rich and subtle. Some useful orienting remarks:

**Remark 2.4.1** (Why "total disconnectedness" does not preclude interesting continuous maps). The analogy with $\mathbb{R}$ is misleading in both directions. In $\mathbb{R}$, continuity and connectedness are intimately linked: continuous images of connected sets are connected, so continuous functions on $\mathbb{R}$ are forced to be highly non-trivial. In a totally disconnected space, continuity is a much weaker condition — locally, every continuous function is approximately constant — but profinite groups compensate by having a rich supply of *open subgroups* (all the Galois subextensions), and continuous homomorphisms are determined by their behaviour on these. The resulting notion of continuity is strong enough to yield deep theorems (Chebotarev, Tate, Deligne) but weak enough to admit non-trivial examples (all the $\ell$-adic representations arising from étale cohomology).

**Remark 2.4.2** (The distinction from $\widehat{\mathbb{Z}}$). The group $\widehat{\mathbb{Z}} = \varprojlim_n \mathbb{Z}/n\mathbb{Z} \cong \prod_p \mathbb{Z}_p$ is also profinite, abelian, and totally disconnected. One might ask: is $G_{\mathbb{Q}}$ abelian, like $\widehat{\mathbb{Z}}$? The answer is no: the abelianisation $G_{\mathbb{Q}}^{\mathrm{ab}}$ is isomorphic to $\widehat{\mathbb{Z}}^\times$, by the Kronecker–Weber theorem together with class field theory, but $G_{\mathbb{Q}}$ itself is highly non-abelian. The non-abelianness is the reason the study of two-dimensional Galois representations (the subject of the Langlands program, Wiles's theorem, etc.) is so much deeper than the study of one-dimensional ones (Dirichlet characters, class field theory).

**Remark 2.4.3** (The role of $S$ in $G_{\mathbb{Q}, S}$). Part 2 writes $\pi_1^{\mathrm{\acute{e}t}}(X) \cong G_{\mathbb{Q}, S}$ for $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$. Here $G_{\mathbb{Q}, S}$ denotes the Galois group of the maximal subextension of $\overline{\mathbb{Q}}/\mathbb{Q}$ unramified outside $S$ (and, by convention, unramified at the archimedean place). Concretely, $G_{\mathbb{Q}, S}$ is the quotient $G_{\mathbb{Q}}/N_S$, where $N_S$ is the closed normal subgroup generated by all inertia groups at primes not in $S$. The isomorphism $\pi_1^{\mathrm{\acute{e}t}}(\mathrm{Spec}\,\mathbb{Z}[1/S]) \cong G_{\mathbb{Q}, S}$ (with a choice of geometric base point) is a theorem of Grothendieck (SGA 1, Exposé V). See Milne (1980), Chapter I, §5 for a careful exposition.

#### 2.5 Revised Passage

The author proposes the following revised wording for §3.7 of Part 2, at the 📐 (junior/senior) level:

> The absolute Galois group $G_{\mathbb{Q}} = \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$ is the inverse limit
> $$G_{\mathbb{Q}} = \varprojlim_{K/\mathbb{Q} \text{ finite Galois}} \mathrm{Gal}(K/\mathbb{Q})$$
> taken over the directed system of finite Galois subextensions $K/\mathbb{Q}$ of $\overline{\mathbb{Q}}/\mathbb{Q}$, with transition maps given by restriction. With its natural topology (the Krull topology, in which a neighbourhood basis of the identity is given by the open subgroups $\mathrm{Gal}(\overline{\mathbb{Q}}/K)$ for $K/\mathbb{Q}$ finite Galois), $G_{\mathbb{Q}}$ is a *profinite group*: compact, Hausdorff, totally disconnected.
>
> The "total disconnectedness" of $G_{\mathbb{Q}}$ does not preclude the existence of interesting continuous homomorphisms out of it. Continuity for a representation
> $$\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$$
> is defined as continuity with respect to the profinite topology on the source and the $\ell$-adic topology on the target. Concretely, $\rho$ is continuous if and only if, for each $n \geq 1$, the composition with reduction mod $\ell^n$ factors through a finite quotient of $G_{\mathbb{Q}}$ — that is, through $\mathrm{Gal}(K_n/\mathbb{Q})$ for some finite Galois extension $K_n/\mathbb{Q}$. The strength of the continuity condition lies in this finite-quotient compatibility across all $n$ simultaneously.

---

### Chapter 3: Frobenius Elements and the Chebotarev Density Theorem

This chapter addresses one of the most consequential simplifications in Part 2: the description, in §3.7, of Frobenius elements as individual elements of $G_{\mathbb{Q}}$, and the statement of Chebotarev's theorem in terms of their density.

#### 3.1 The Original Statement

The following passage appears in §3.7 of Part 2, at the 📐 (junior/senior) level:

> The Frobenius elements $\mathrm{Frob}_p$ for $p = 3, 5, 7, 13, 17, \ldots$ are **dense** in $G_{\mathbb{Q}}$ (Chebotarev density theorem). In every open neighbourhood of $G_{\mathbb{Q}}$, some prime's Frobenius resides.
>
> ***This is the true identity of "discrete yet connected."*** The buildings (primes) are discrete, but the corresponding Frobenius elements are dense in $G_{\mathbb{Q}}$ (the sky castle), and $G_{\mathbb{Q}}$ is compact in the profinite topology. "Inside the castle, Frobenius elements are everywhere."

#### 3.2 Nature of the Simplification

Two issues arise.

**First**, the Frobenius element $\mathrm{Frob}_p \in G_{\mathbb{Q}}$ is *not* a canonically defined element. Given a prime $p$ unramified in a finite Galois extension $K/\mathbb{Q}$, the Frobenius at $p$ is well-defined as an element of $\mathrm{Gal}(K/\mathbb{Q})$ only after a choice of prime $\mathfrak{P}$ of $K$ above $p$. Different choices of $\mathfrak{P}$ yield different Frobenius elements, related by conjugation. The Frobenius is therefore intrinsically a *conjugacy class* in $\mathrm{Gal}(K/\mathbb{Q})$, denoted $[\mathrm{Frob}_p]_K$, and the same is true in the infinite Galois group $G_{\mathbb{Q}}$ after passing to the inverse limit.

**Second**, Chebotarev's theorem does not assert that "Frobenius elements are dense in $G_{\mathbb{Q}}$" as a bare topological statement. It asserts a much stronger quantitative statement: Frobenius conjugacy classes are *equidistributed* with respect to Haar measure. Density is a corollary of equidistribution but is considerably weaker.

The combination of these two simplifications — dropping the conjugacy-class qualifier and weakening equidistribution to density — makes the passage readable at the 📐 level but misrepresents the content of Chebotarev's theorem in a way that will mislead any reader attempting to use the theorem in practice.

#### 3.3 Precise Formulation

We begin with the finite-field case, following Neukirch (1999), Chapter I, §§8–9.

**Proposition 3.3.1** (Frobenius at an unramified prime, finite case). *Let $K/\mathbb{Q}$ be a finite Galois extension, let $p$ be a prime of $\mathbb{Z}$ unramified in $K$, and let $\mathfrak{P}$ be a prime of $\mathcal{O}_K$ above $p$. Then there exists a unique element $\mathrm{Frob}_{\mathfrak{P}} \in \mathrm{Gal}(K/\mathbb{Q})$ such that*
$$\mathrm{Frob}_{\mathfrak{P}}(x) \equiv x^p \pmod{\mathfrak{P}}\qquad \text{for all } x \in \mathcal{O}_K.$$
*The element $\mathrm{Frob}_{\mathfrak{P}}$ generates the decomposition group $D_{\mathfrak{P}} = \{\sigma \in \mathrm{Gal}(K/\mathbb{Q}) : \sigma(\mathfrak{P}) = \mathfrak{P}\}$ cyclically.*

**Proposition 3.3.2** (Dependence on $\mathfrak{P}$). *Under the hypotheses of Proposition 3.3.1, if $\mathfrak{P}'$ is another prime of $\mathcal{O}_K$ above $p$, then $\mathfrak{P}' = \sigma(\mathfrak{P})$ for some $\sigma \in \mathrm{Gal}(K/\mathbb{Q})$, and*
$$\mathrm{Frob}_{\mathfrak{P}'} = \sigma \circ \mathrm{Frob}_{\mathfrak{P}} \circ \sigma^{-1}.$$
*In particular, the elements $\{\mathrm{Frob}_{\mathfrak{P}} : \mathfrak{P} \mid p\}$ form a single conjugacy class in $\mathrm{Gal}(K/\mathbb{Q})$, denoted $[\mathrm{Frob}_p]_K$ and called the Frobenius conjugacy class at $p$.*

*Proof.* See Neukirch (1999), Chapter I, §9, Proposition 9.2. $\square$

**Definition 3.3.3** (Frobenius in the absolute Galois group). Let $p$ be a rational prime. A *Frobenius element* at $p$ in $G_{\mathbb{Q}}$ is an element $\mathrm{Frob}_p \in G_{\mathbb{Q}}$ obtained as follows: fix, once and for all, a prime $\overline{\mathfrak{P}}$ of $\overline{\mathbb{Q}}$ above $p$ (that is, a nested compatible system $(\mathfrak{P}_K)_K$ of primes $\mathfrak{P}_K \subset \mathcal{O}_K$ above $p$, one for each finite extension $K/\mathbb{Q}$ contained in $\overline{\mathbb{Q}}$). Then $\mathrm{Frob}_p \in G_{\mathbb{Q}}$ is defined by the compatibility
$$\mathrm{Frob}_p|_K = \mathrm{Frob}_{\mathfrak{P}_K} \in \mathrm{Gal}(K/\mathbb{Q}) \quad \text{for every finite Galois } K/\mathbb{Q} \text{ in which } p \text{ is unramified}.$$

The element $\mathrm{Frob}_p$ depends on the choice of $\overline{\mathfrak{P}}$; different choices yield conjugate elements. The conjugacy class $[\mathrm{Frob}_p] \subseteq G_{\mathbb{Q}}$ (topological closure, in the profinite topology) is, however, canonically defined.

**Theorem 3.3.4** (Chebotarev density, 1922). *Let $K/\mathbb{Q}$ be a finite Galois extension with group $G = \mathrm{Gal}(K/\mathbb{Q})$. Let $C \subseteq G$ be a conjugacy class. Then the set of primes $p$ (unramified in $K$) with Frobenius conjugacy class $[\mathrm{Frob}_p]_K = C$ has natural density*
$$\lim_{x \to \infty} \frac{\#\{p \leq x : [\mathrm{Frob}_p]_K = C\}}{\#\{p \leq x\}} = \frac{|C|}{|G|}.$$

*Proof.* The classical proof uses Artin $L$-functions; see Neukirch (1999), Chapter VII, §13. For a modern, measure-theoretic formulation in terms of Haar measure on $G_{\mathbb{Q}}$, see Serre (1981). $\square$

**Theorem 3.3.5** (Chebotarev, profinite form). *Let $\mu$ be the unique Haar probability measure on $G_{\mathbb{Q}}$. Then for every continuous class function $f : G_{\mathbb{Q}} \to \mathbb{C}$,*
$$\lim_{x \to \infty} \frac{1}{\pi(x)} \sum_{p \leq x, \text{ unram.}} f(\mathrm{Frob}_p) = \int_{G_{\mathbb{Q}}} f \, d\mu,$$
*where the Frobenius on the left may be taken arbitrarily within its conjugacy class (the value $f(\mathrm{Frob}_p)$ is independent of this choice).*

**Corollary 3.3.6** (Density of Frobenius conjugacy classes). *The union*
$$\bigcup_{p \text{ unram.}} [\mathrm{Frob}_p]$$
*is dense in $G_{\mathbb{Q}}$.*

*Proof.* If not, there would be a non-empty open subset $U \subseteq G_{\mathbb{Q}}$ disjoint from all Frobenius conjugacy classes. By the regularity of Haar measure, $\mu(U) > 0$, and the indicator function of $U$ (or a continuous approximation thereof) would contradict Theorem 3.3.5. $\square$

#### 3.4 Discussion

The passage from Part 2 quoted in §3.1 can be read as an informal version of Corollary 3.3.6. As such, it is not "wrong" — it is a true statement, if understood carefully. But the careful understanding requires three caveats that a literal reading of Part 2 elides:

1. The individual element $\mathrm{Frob}_p$ depends on a choice of prime above $p$ in $\overline{\mathbb{Q}}$. The intrinsic object is the conjugacy class $[\mathrm{Frob}_p]$.

2. "Density" is a consequence of Chebotarev's theorem; the theorem itself says more. Specifically, it says that the conjugacy classes are *equidistributed* with respect to Haar measure — that is, the proportion of primes with given Frobenius conjugacy class $C$ is exactly $|C|/|G|$ for any finite quotient $G$.

3. The density statement concerns the *union of conjugacy classes*, not the set of individual Frobenius elements (which is not intrinsically defined).

The mathematical pay-off of these clarifications is not merely pedantic. In the Langlands program and in the modern theory of Galois representations, one routinely considers invariants of a continuous representation $\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$ — such as the characteristic polynomial of $\rho(\mathrm{Frob}_p)$ — that are well-defined because they are *class functions*. The characteristic polynomial does not depend on which element of the conjugacy class one evaluates on. Losing sight of the conjugacy-class nature of Frobenius makes it difficult to understand why such invariants are intrinsically attached to $\rho$ and the prime $p$ rather than to a specific choice of embedding.

**Example 3.4.1** (Quadratic fields). Let $K = \mathbb{Q}(\sqrt{d})$ for a squarefree integer $d \neq 0, 1$, so $G = \mathrm{Gal}(K/\mathbb{Q}) \cong \mathbb{Z}/2\mathbb{Z} = \{e, \tau\}$, where $\tau$ is complex conjugation (if $d < 0$) or conjugation $\sqrt{d} \mapsto -\sqrt{d}$ (in general). Every conjugacy class is a singleton.

For $p$ unramified in $K$ (equivalently, $p \nmid 2d$), Chebotarev says:
- Density $1/2$ of primes have $\mathrm{Frob}_p = e$ (split primes: $p = \mathfrak{p}_1 \mathfrak{p}_2$ in $\mathcal{O}_K$).
- Density $1/2$ of primes have $\mathrm{Frob}_p = \tau$ (inert primes: $p$ remains prime in $\mathcal{O}_K$).

For $K = \mathbb{Q}(i)$, this recovers Fermat's theorem: primes with $p \equiv 1 \pmod 4$ are split (and writable as $p = a^2 + b^2$), those with $p \equiv 3 \pmod 4$ are inert. The density-$1/2$ statement is the quantitative refinement.

**Example 3.4.2** (Cubic non-Galois extensions and $S_3$). Let $f(x) = x^3 - x - 1$, with splitting field $K$ and $\mathrm{Gal}(K/\mathbb{Q}) \cong S_3$. The conjugacy classes of $S_3$ are $\{e\}$, the three transpositions $T = \{(12), (13), (23)\}$, and the two $3$-cycles $R = \{(123), (132)\}$, with $|e| = 1, |T| = 3, |R| = 2$.

Chebotarev then predicts:
- Density $1/6$: primes $p$ with $[\mathrm{Frob}_p] = \{e\}$ (totally split).
- Density $1/2$: primes $p$ with $[\mathrm{Frob}_p] = T$ (one linear and one irreducible quadratic factor of $f \bmod p$).
- Density $1/3$: primes $p$ with $[\mathrm{Frob}_p] = R$ ($f$ irreducible mod $p$).

Empirical verification: among primes $p \leq 1000$, one finds roughly $1/6 \approx 16.7\%$ split completely, roughly $1/2 = 50\%$ give cycle type $(2,1)$, and roughly $1/3 \approx 33.3\%$ give cycle type $(3)$. This is among the most accessible numerical tests of the Chebotarev theorem.

**Remark 3.4.3** (Relation to PCP and modern refinements). Effective versions of Chebotarev's theorem (Lagarias–Odlyzko 1977, conditional on GRH) give explicit error bounds. Unconditional effective Chebotarev is a major open problem in analytic number theory; the unconditional bounds currently known (of Murty, Rajan, and others) are significantly weaker than the GRH-conditional ones.

#### 3.5 Revised Passage

The author proposes the following revised version of the passage at the 📐 level in §3.7 of Part 2:

> For each rational prime $p$, and each finite Galois extension $K/\mathbb{Q}$ in which $p$ is unramified, the Frobenius at $p$ is well-defined as a *conjugacy class* $[\mathrm{Frob}_p]_K \subseteq \mathrm{Gal}(K/\mathbb{Q})$. Passing to the inverse limit over all such $K$, one obtains a canonical conjugacy class $[\mathrm{Frob}_p] \subseteq G_{\mathbb{Q}}$.
>
> An individual element $\mathrm{Frob}_p \in [\mathrm{Frob}_p]$ is defined only after a choice of prime of $\overline{\mathbb{Q}}$ above $p$; different choices yield conjugate elements. Class functions of the absolute Galois group — such as the characteristic polynomial of a Galois representation at a Frobenius — are therefore well-defined at each $\mathrm{Frob}_p$, independent of the choice.
>
> *Chebotarev's density theorem* asserts that these Frobenius conjugacy classes are equidistributed with respect to Haar measure on $G_{\mathbb{Q}}$: for any finite Galois quotient $\mathrm{Gal}(K/\mathbb{Q})$ and any conjugacy class $C \subseteq \mathrm{Gal}(K/\mathbb{Q})$, the density of primes $p$ with $[\mathrm{Frob}_p]_K = C$ is exactly $|C|/|\mathrm{Gal}(K/\mathbb{Q})|$. It follows, in particular, that the union of Frobenius conjugacy classes is dense in $G_{\mathbb{Q}}$.
>
> *This is the precise form of the "discrete yet connected" phenomenon.* The primes $p$ themselves are discrete objects in $\mathrm{Spec}\,\mathbb{Z}$, but their Frobenius conjugacy classes cover the compact profinite group $G_{\mathbb{Q}}$ uniformly — so that statistical questions about primes can be answered by computing integrals over $G_{\mathbb{Q}}$ with Haar measure.

---

### Chapter 4: The Sheaf–Representation Equivalence

This chapter addresses §3.7 of Part 2, concerning the equivalence between lisse $\ell$-adic étale sheaves on $\mathrm{Spec}\,\mathbb{Z}[1/S]$ and continuous $\ell$-adic representations of the étale fundamental group.

#### 4.1 The Original Statement

The following passage appears at the 🔬 (graduate) level in §3.7 of Part 2:

> The category of lisse $\ell$-adic étale sheaves on $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$ is equivalent to the category of continuous $\ell$-adic representations of $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$:
> $$\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}}) \simeq \mathrm{Rep}^{\mathrm{cont}}_{\mathbb{Q}_\ell}(\pi_1^{\mathrm{\acute{e}t}}(X))$$
> For $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$, $\pi_1^{\mathrm{\acute{e}t}}(X) \cong G_{\mathbb{Q}, S}$ (the quotient of $G_{\mathbb{Q}}$ unramified outside $S$).
>
> ***This equivalence is the mathematically precise statement that "étale sheaves" and "Galois representations" are two faces of the same coin.***

#### 4.2 Nature of the Simplification

The statement is correct up to two elisions which, while appropriate at the pedagogical level, would cause difficulty for a reader passing to Milne's *Étale Cohomology* or to SGA 1:

**First**, the fundamental group $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$ depends on a choice of geometric base point $\bar{x}$. Different choices yield isomorphic groups, but the isomorphism is canonical only up to inner automorphism. In the equivalence with Galois representations, this inner-automorphism ambiguity corresponds to the conjugacy-class ambiguity in the choice of Frobenius (discussed in Chapter 3 above).

**Second**, the notation $\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}})$ requires clarification. A lisse $\ell$-adic sheaf is *not* an étale sheaf of $\mathbb{Q}_\ell$-vector spaces in the naive sense; rather, it is a compatible system of locally constant étale sheaves with values in $\mathbb{Z}/\ell^n\mathbb{Z}$-modules, suitably formalised. The equivalence as stated therefore involves an implicit passage from $\mathbb{Q}_\ell$-sheaves (undefined naively on the étale site) to $\mathbb{Z}_\ell$-systems (which are definable) and thence to $\mathbb{Q}_\ell$-representations (by tensoring).

#### 4.3 Precise Formulation

**Setup.** Let $X$ be a connected, locally Noetherian scheme, and fix a geometric base point $\bar{x} : \mathrm{Spec}\,\Omega \to X$, where $\Omega$ is a separably closed field.

**Definition 4.3.1** (Étale fundamental group). The *étale fundamental group* of $X$ at $\bar{x}$, denoted $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$, is the automorphism group of the fibre functor
$$F_{\bar{x}} : \mathrm{F\acute{E}t}(X) \to \mathrm{Set}, \qquad (Y \to X) \mapsto Y_{\bar{x}} = Y \times_X \mathrm{Spec}\,\Omega,$$
where $\mathrm{F\acute{E}t}(X)$ is the category of finite étale covers of $X$. With the profinite topology — the coarsest making every map $\mathrm{Aut}(F_{\bar{x}}) \to \mathrm{Aut}(F_{\bar{x}}(Y))$ continuous for $Y \to X$ finite étale — the group $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$ is profinite.

**Theorem 4.3.2** (Grothendieck's Galois correspondence, SGA 1, Exposé V). *The fibre functor $F_{\bar{x}}$ induces an equivalence of categories*
$$\mathrm{F\acute{E}t}(X) \xrightarrow{\sim} \pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})\text{-}\mathrm{FinSet}$$
*between finite étale covers of $X$ and finite sets equipped with a continuous action of $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$.*

**Proposition 4.3.3** (The case $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$). *Let $S$ be a finite set of rational primes, and $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$. Fix a geometric base point $\bar{x}$ corresponding to a choice of algebraic closure $\overline{\mathbb{Q}}$ of $\mathbb{Q}$. Then there is a canonical isomorphism of profinite groups*
$$\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x}) \cong G_{\mathbb{Q}, S},$$
*where $G_{\mathbb{Q}, S} = \mathrm{Gal}(\mathbb{Q}^{\mathrm{unr},S}/\mathbb{Q})$ is the Galois group of the maximal subextension $\mathbb{Q}^{\mathrm{unr},S} \subseteq \overline{\mathbb{Q}}$ unramified outside $S$.*

*Proof.* The finite étale covers of $\mathrm{Spec}\,\mathbb{Z}[1/S]$ correspond bijectively to finite extensions of $\mathbb{Q}$ unramified outside $S$, by classical algebraic number theory (Neukirch 1999, Chapter I). Passing to inverse limits gives the isomorphism. $\square$

**Definition 4.3.4** (Lisse $\ell$-adic sheaf). A *lisse $\ell$-adic sheaf* on $X$ is a compatible system $\mathcal{F} = (\mathcal{F}_n)_{n \geq 1}$, where:
- each $\mathcal{F}_n$ is a locally constant constructible sheaf of $\mathbb{Z}/\ell^n\mathbb{Z}$-modules on $X_{\mathrm{\acute{e}t}}$ whose stalks are finite free $\mathbb{Z}/\ell^n\mathbb{Z}$-modules of a fixed rank $r$ (independent of $n$);
- the system is compatible in the sense that $\mathcal{F}_n \otimes_{\mathbb{Z}/\ell^{n}\mathbb{Z}} \mathbb{Z}/\ell^{n-1}\mathbb{Z} \cong \mathcal{F}_{n-1}$.

One then defines $\mathcal{F}_{\mathbb{Z}_\ell} := \varprojlim_n \mathcal{F}_n$ and $\mathcal{F}_{\mathbb{Q}_\ell} := \mathcal{F}_{\mathbb{Z}_\ell} \otimes_{\mathbb{Z}_\ell} \mathbb{Q}_\ell$. The category of lisse $\ell$-adic sheaves on $X$, with $\mathbb{Q}_\ell$-coefficients, is denoted $\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}})$.

**Theorem 4.3.5** (Sheaf–representation equivalence). *Let $X$ be a connected scheme with geometric base point $\bar{x}$. There is a natural equivalence of categories*
$$\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}}) \xrightarrow{\sim} \mathrm{Rep}^{\mathrm{cont}}_{\mathbb{Q}_\ell}\!\bigl(\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})\bigr)$$
*given by $\mathcal{F} \mapsto \mathcal{F}_{\mathbb{Q}_\ell, \bar{x}}$, the stalk at $\bar{x}$, equipped with its natural continuous action of $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$.*

*Proof sketch.* The case of finite constant coefficients follows from Theorem 4.3.2 and the observation that a locally constant sheaf of finite sets is determined by its stalk at $\bar{x}$ as a $\pi_1^{\mathrm{\acute{e}t}}$-set. Passing to inverse limits and tensoring with $\mathbb{Q}_\ell$ gives the general case. For details, see Milne (1980), Chapter V, §1, or Freitag–Kiehl (1988). $\square$

**Specialisation to $\mathrm{Spec}\,\mathbb{Z}[1/S]$.** Combining Proposition 4.3.3 and Theorem 4.3.5:
$$\mathrm{Loc}_{\mathbb{Q}_\ell}(\mathrm{Spec}\,\mathbb{Z}[1/S]_{\mathrm{\acute{e}t}}) \simeq \mathrm{Rep}^{\mathrm{cont}}_{\mathbb{Q}_\ell}(G_{\mathbb{Q}, S}).$$

#### 4.4 Discussion

The pedagogical statement of Part 2 — "étale sheaves and Galois representations are two faces of the same coin" — is a vivid and essentially correct summary of Theorem 4.3.5. The refinements above are a matter of mathematical hygiene rather than substance.

**Remark 4.4.1** (Base point dependence). The dependence of $\pi_1^{\mathrm{\acute{e}t}}$ on the base point $\bar{x}$ is analogous to the dependence of the topological fundamental group $\pi_1$ on a base point. Just as in the topological case, $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x}) \cong \pi_1^{\mathrm{\acute{e}t}}(X, \bar{x}')$ for any two geometric base points, with an isomorphism canonical up to inner automorphism. Accordingly, the equivalence of categories in Theorem 4.3.5 depends on the base point, but only up to natural isomorphism. In practice, when speaking of "the" equivalence, a base point has been implicitly fixed.

**Remark 4.4.2** (Why $\mathbb{Z}_\ell$ rather than $\mathbb{Q}_\ell$ at the sheaf level). The definition of a "lisse $\ell$-adic sheaf" bypasses $\mathbb{Q}_\ell$-coefficients because étale sheaves are defined for reasonable coefficient rings (finite discrete rings, in particular), and $\mathbb{Q}_\ell$ is not such a ring. The passage from compatible systems to $\mathbb{Q}_\ell$-sheaves is achieved by an inverse-limit-and-tensor construction. In the modern formalism of pro-étale cohomology (Bhatt–Scholze 2015), one can define $\mathbb{Q}_\ell$-sheaves directly on the pro-étale site, but this requires a larger site and more machinery.

**Remark 4.4.3** (Connection to Chapter 3). The Frobenius conjugacy class $[\mathrm{Frob}_p] \subseteq G_{\mathbb{Q}, S}$ (for $p \notin S$), under the sheaf–representation equivalence, corresponds to a conjugacy class of automorphisms of the stalk $\mathcal{F}_{\bar{x}}$ — equivalently, to a well-defined characteristic polynomial $\det(1 - \rho(\mathrm{Frob}_p) T) \in \mathbb{Q}_\ell[T]$, independent of the choice of prime above $p$. This is why "the Frobenius eigenvalues at $p$" is a meaningful phrase, and why the Weil conjectures (discussed in Chapter 5 below) can be formulated in terms of these eigenvalues.

#### 4.5 Revised Passage

The author proposes the following revised version of §3.7 of Part 2, at the 🔬 (graduate) level:

> Fix a geometric base point $\bar{x}$ of $X = \mathrm{Spec}\,\mathbb{Z}[1/S]$, corresponding to a choice of algebraic closure $\overline{\mathbb{Q}}$ of $\mathbb{Q}$ with a prescribed system of primes above each rational prime. Under this choice, the étale fundamental group of $X$ is canonically identified with the Galois group of the maximal subextension of $\overline{\mathbb{Q}}/\mathbb{Q}$ unramified outside $S$:
> $$\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x}) \cong G_{\mathbb{Q}, S}.$$
> Different choices of $\bar{x}$ yield isomorphic groups, with isomorphisms canonical up to inner automorphism.
>
> A *lisse $\ell$-adic sheaf* on $X$ is a compatible system $(\mathcal{F}_n)_{n \geq 1}$ of locally constant $\mathbb{Z}/\ell^n\mathbb{Z}$-étale sheaves of fixed rank, with $\mathbb{Q}_\ell$-coefficients obtained by the standard inverse-limit-and-tensor construction. The resulting category $\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}})$ carries a *stalk-at-$\bar{x}$* functor, which gives a continuous action of $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$ on a finite-dimensional $\mathbb{Q}_\ell$-vector space.
>
> *Grothendieck's sheaf–representation equivalence* asserts that the stalk functor yields an equivalence
> $$\mathrm{Loc}_{\mathbb{Q}_\ell}(X_{\mathrm{\acute{e}t}}) \xrightarrow{\sim} \mathrm{Rep}^{\mathrm{cont}}_{\mathbb{Q}_\ell}(G_{\mathbb{Q}, S}).$$
> Under this equivalence, the Frobenius conjugacy class $[\mathrm{Frob}_p]$ for $p \notin S$ corresponds to a well-defined conjugacy class of automorphisms of the stalk, and invariants such as the characteristic polynomial of Frobenius are intrinsic to the sheaf.
>
> *This equivalence is the mathematically precise statement that "étale sheaves" and "Galois representations" are two faces of the same coin.*

---

### Chapter 5: The $p$-adic Numbers, Hensel's Lemma, and the Numerical Example

This chapter addresses §3.7b of Part 2, concerning $p$-adic numbers, the construction of $\mathbb{Z}_p$ as a projective limit, and the explicit lift of $\sqrt{2}$ in $\mathbb{Q}_7$.

#### 5.1 The Original Statement

The relevant passages appear at the 🎓 and 📐 levels in §3.7b. At the 🎓 level:

> $\mathbb{Z}_p$ is defined as the projective limit $\mathbb{Z}_p = \varprojlim_n \mathbb{Z}/p^n\mathbb{Z}$. Its elements have "$p$-adic expansions" $a_0 + a_1 p + a_2 p^2 + \cdots$ ($0 \leq a_i < p$).
>
> **Example:** Lift $x = 3$ (solution of $x^2 = 2$ in $\mathbb{F}_7$) to $\mathbb{Z}_7$:
>
> 1. $3^2 = 9 = 7 + 2$, so $3^2 \equiv 2 \pmod 7$ ✓ (ground floor)
> 2. By Hensel's lemma: $x \equiv 10 \pmod{49}$, and $10^2 = 100 \equiv 2 \pmod{49}$ ✓ (underground level 1)
> 3. Continuing: $x \equiv 108 \pmod{343}$, and $108^2 = 11664 \equiv 2 \pmod{343}$ ✓ (underground level 2)
>
> The limit of this infinite lifting gives the 7-adic expansion of $\sqrt{2}$. Indeed $\sqrt{2} \in \mathbb{Q}_7$.

#### 5.2 Nature of the Simplification

The passage is numerically correct and pedagogically effective. Three refinements will, however, be useful to the reader consulting a reference such as Gouvêa (1997) or Serre (1973).

**First**, Hensel's lemma is stated informally, without its hypothesis. The hypothesis — that the derivative $f'(x_0)$ be a unit modulo $p$ — is what allows the lifting. For $f(x) = x^2 - 2$, we have $f'(x) = 2x$, and at $x_0 = 3$ we compute $f'(3) = 6$, which is a unit in $\mathbb{F}_7$ (since $\gcd(6, 7) = 1$). Hence Hensel applies; but the reader deserves to see why.

**Second**, the equation $x^2 = 2$ over $\mathbb{F}_7$ has *two* solutions, $x = 3$ and $x = -3 \equiv 4$, and each lifts independently to a $7$-adic square root of $2$. The two lifts satisfy $\alpha + \beta = 0$ in $\mathbb{Q}_7$, so that $\mathbb{Q}_7$ contains both $\sqrt{2}$ and $-\sqrt{2}$, as expected.

**Third**, the reader may profitably be shown the full content of Hensel's lemma, together with the explicit iteration that yields the successive approximations $3, 10, 108, \ldots$. The iteration is a form of Newton's method, as noted in most references.

#### 5.3 Precise Formulation

**Theorem 5.3.1** (Hensel's lemma, classical form). *Let $f(x) \in \mathbb{Z}_p[x]$, and suppose $x_0 \in \mathbb{Z}_p$ satisfies*
$$f(x_0) \equiv 0 \pmod p, \qquad f'(x_0) \not\equiv 0 \pmod p.$$
*Then there exists a unique $\alpha \in \mathbb{Z}_p$ with $\alpha \equiv x_0 \pmod p$ and $f(\alpha) = 0$. The element $\alpha$ is given explicitly as the limit of the Newton iteration*
$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)} \in \mathbb{Z}_p.$$

*Proof.* See Gouvêa (1997), §3.4, Theorem 3.4.1, or Serre (1973), Chapter II, §2. $\square$

**Example 5.3.2** (Square root of $2$ in $\mathbb{Q}_7$). Let $f(x) = x^2 - 2$ and $x_0 = 3 \in \mathbb{Z}_7$.

**Verification of hypotheses.** $f(3) = 9 - 2 = 7 \equiv 0 \pmod 7$. $f'(x) = 2x$, so $f'(3) = 6 \not\equiv 0 \pmod 7$. Hensel applies.

**Explicit iteration.** Using $x_{n+1} = x_n - f(x_n)/f'(x_n) = x_n - (x_n^2 - 2)/(2 x_n) = (x_n^2 + 2)/(2 x_n)$ (computed in $\mathbb{Z}_7$):

*Step 1:* $x_0 = 3$. $f(3) = 7$. $f'(3) = 6$. In $\mathbb{Z}_7$, $6^{-1} \equiv 6 \pmod 7$ (since $6 \cdot 6 = 36 = 35 + 1$), so modulo $49$:
$$x_1 \equiv 3 - 7 \cdot 6 \pmod{49} \equiv 3 - 42 \equiv -39 \equiv 10 \pmod{49}.$$
Check: $10^2 = 100 = 2 \cdot 49 + 2 = 98 + 2$, so $10^2 \equiv 2 \pmod{49}$. ✓

*Step 2:* Newton at $x_1 = 10$: $f(10) = 98$, $f'(10) = 20$. In $\mathbb{Z}_7$, $20 \equiv 6 \pmod 7$, so $20^{-1} \equiv 6 \pmod 7$, and more precisely $20^{-1} \equiv 27 \pmod{49}$ (since $20 \cdot 27 = 540 = 11 \cdot 49 + 1$). Then
$$x_2 \equiv 10 - 98 \cdot 27 \cdot \left[\text{adjusted to the right precision}\right] \pmod{343}.$$
A direct computation yields $x_2 \equiv 108 \pmod{343}$, and $108^2 = 11664 = 34 \cdot 343 + 2$, so $108^2 \equiv 2 \pmod{343}$. ✓

**Continuing indefinitely** yields a Cauchy sequence $3, 10, 108, 2166, \ldots$ in $\mathbb{Z}_7$ whose $7$-adic limit $\alpha \in \mathbb{Z}_7$ satisfies $\alpha^2 = 2$.

**The second square root.** The polynomial $x^2 - 2$ has a second root modulo $7$, namely $-3 \equiv 4 \pmod 7$ (since $4^2 = 16 = 2 \cdot 7 + 2$). Hensel lifts this to a second $7$-adic square root $\beta \in \mathbb{Z}_7$ with $\beta \equiv 4 \pmod 7$. One has $\alpha + \beta = 0$ in $\mathbb{Q}_7$, so $\beta = -\alpha$.

**Proposition 5.3.3.** *An element $a \in \mathbb{Z}_p^\times$ (where $p$ is an odd prime) has a square root in $\mathbb{Z}_p$ if and only if its image in $\mathbb{F}_p$ is a quadratic residue. Equivalently, $(\mathbb{Z}_p^\times)^2$ has index $2$ in $\mathbb{Z}_p^\times$, and the quotient is generated by the Legendre symbol mod $p$.*

*Proof.* Sufficient: if $\bar{a} \in \mathbb{F}_p^\times$ is a square, pick $x_0 \in \mathbb{Z}$ with $x_0^2 \equiv a \pmod p$; then $f(x) = x^2 - a$ satisfies $f(x_0) \equiv 0 \pmod p$ and $f'(x_0) = 2 x_0 \not\equiv 0 \pmod p$ (since $p$ is odd and $x_0 \not\equiv 0$). Hensel gives the lift. Necessary: a square in $\mathbb{Z}_p^\times$ reduces to a square in $\mathbb{F}_p^\times$. $\square$

#### 5.4 Discussion

**Remark 5.4.1** ($p = 2$ is exceptional). The criterion of Proposition 5.3.3 fails at $p = 2$, because $f'(x_0) = 2 x_0$ is never a unit in $\mathbb{Z}_2$. In $\mathbb{Z}_2$, the condition for $a \in \mathbb{Z}_2^\times$ to be a square is $a \equiv 1 \pmod 8$. This "exceptional" behaviour at $p = 2$ is a running theme in $p$-adic analysis and $p$-adic Hodge theory.

**Remark 5.4.2** (Non-existence elsewhere). The square $\sqrt{2}$ exists in $\mathbb{Q}_7$ because $2$ is a quadratic residue mod $7$. The list of primes $p$ for which $\sqrt{2} \in \mathbb{Q}_p$ consists of those $p$ with $2$ a quadratic residue mod $p$; by quadratic reciprocity, this is the set $\{p : p \equiv \pm 1 \pmod 8\}$ together with $p = 2$ (in which case $\sqrt{2} \in \mathbb{Q}_2$ is false; but $\sqrt{2} \in \mathbb{Q}_2(\sqrt{2})$, a ramified quadratic extension). For other primes, $\mathbb{Q}_p(\sqrt{2})/\mathbb{Q}_p$ is an unramified quadratic extension. This dichotomy is the $p$-adic version of the Gaussian result that a rational prime splits in $\mathbb{Z}[i]$ iff $p \equiv 1 \pmod 4$.

**Remark 5.4.3** (Hensel as Newton). The Newton iteration $x_{n+1} = x_n - f(x_n)/f'(x_n)$ converges in $\mathbb{Q}_p$ with *quadratic* rate: $v_p(f(x_{n+1})) \geq 2 v_p(f(x_n))$, where $v_p$ denotes the $p$-adic valuation. This is the $p$-adic analogue of the real Newton method's quadratic convergence near simple roots.

#### 5.5 Revised Passage

The author proposes the following revised version of §3.7b at the 🎓 level:

> $\mathbb{Z}_p$ is defined as the projective limit $\mathbb{Z}_p = \varprojlim_n \mathbb{Z}/p^n\mathbb{Z}$. Its elements have unique *$p$-adic expansions* $a_0 + a_1 p + a_2 p^2 + \cdots$ with $0 \leq a_i < p$.
>
> **Hensel's lemma** provides the basic lifting mechanism: if $f(x) \in \mathbb{Z}_p[x]$ and $x_0 \in \mathbb{Z}_p$ satisfies $f(x_0) \equiv 0 \pmod p$ and $f'(x_0) \not\equiv 0 \pmod p$, then there exists a unique $\alpha \in \mathbb{Z}_p$ with $\alpha \equiv x_0 \pmod p$ and $f(\alpha) = 0$. The root $\alpha$ is obtained as the limit of the Newton iteration
> $$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}.$$
>
> **Example (Lifting $\sqrt{2}$ to $\mathbb{Z}_7$).** For $f(x) = x^2 - 2$ and $x_0 = 3$, we verify $f(3) = 7 \equiv 0 \pmod 7$ and $f'(3) = 6 \not\equiv 0 \pmod 7$; Hensel applies. Explicit Newton iteration yields
> $$3 \mapsto 10 \mapsto 108 \mapsto 2166 \mapsto \cdots,$$
> with $10^2 \equiv 2 \pmod{49}$, $108^2 \equiv 2 \pmod{343}$, etc. The limit $\alpha \in \mathbb{Z}_7$ satisfies $\alpha^2 = 2$, so $\sqrt{2} \in \mathbb{Q}_7$. A second square root $-\alpha$ is obtained by lifting the other mod-$7$ root $4$.
>
> **Criterion for squares.** For odd $p$, an element $a \in \mathbb{Z}_p^\times$ is a square in $\mathbb{Z}_p$ iff its reduction in $\mathbb{F}_p$ is a quadratic residue. (The criterion at $p = 2$ is more subtle: $a \equiv 1 \pmod 8$.)

---

## Part III: Medium-Priority Refinements

### Chapter 6: The Weil Conjectures and Deligne's Bound

This chapter addresses §3.8 of Part 2, concerning the Weil conjectures and their resolution by Deligne.

#### 6.1 The Original Statement

The following passage appears at the 🎓🏫 level in §3.8 of Part 2:

> **Problem (Weil, 1949):** How does the number of solutions $N_q$ of an equation over $\mathbb{F}_q$ grow as $q$ increases?
>
> **Solution (Deligne, 1974):** The eigenvalues $\alpha_i$ of the Frobenius acting on $H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{F}}_q}, \mathbb{Q}_\ell)$ satisfy $|\alpha_i| = q^{i/2}$.

#### 6.2 Nature of the Simplification

The statement is correct but considerably compressed. Three refinements help the reader situate Deligne's theorem within the larger Weil programme:

**First**, Weil's 1949 paper proposed *four* conjectures, of which the Riemann Hypothesis component (the one about $|\alpha_i| = q^{i/2}$) was the deepest. The others — rationality of the zeta function, functional equation, and Betti-number interpretation — were proved earlier, primarily by Dwork (1960, rationality), Artin–Grothendieck (1960s, functional equation), and followed from the construction of $\ell$-adic cohomology (Grothendieck, 1964+).

**Second**, the statement should specify that $X$ is a *smooth projective* variety over $\mathbb{F}_q$. Without smoothness, $|\alpha_i|$ may be $q^{j/2}$ for some $j \leq i$ (the "mixed" case), and the sharp statement fails.

**Third**, the $\alpha_i$ are algebraic integers: they are eigenvalues of a Frobenius acting on an $\ell$-adic cohomology group, and a cornerstone of Deligne's theorem is that the characteristic polynomial of Frobenius has coefficients in $\mathbb{Z}$ (independent of $\ell$).

#### 6.3 Precise Formulation

**Theorem 6.3.1** (Weil conjectures, Deligne 1974). *Let $X$ be a smooth projective variety of dimension $d$ over $\mathbb{F}_q$. For $\ell \neq \mathrm{char}(\mathbb{F}_q)$, let $\mathrm{Frob}_q$ denote the geometric Frobenius acting on $H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{F}}_q}, \mathbb{Q}_\ell)$. Then:*

*(i) Rationality:*
$$Z(X/\mathbb{F}_q, T) = \exp\left(\sum_{n \geq 1} \frac{|X(\mathbb{F}_{q^n})|}{n} T^n\right) = \prod_{i=0}^{2d} P_i(T)^{(-1)^{i+1}}$$
*where $P_i(T) = \det(1 - T \cdot \mathrm{Frob}_q \mid H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{F}}_q}, \mathbb{Q}_\ell))$ is a polynomial with integer coefficients, independent of $\ell$.*

*(ii) Functional equation:*
$$Z(X/\mathbb{F}_q, 1/(q^d T)) = \pm q^{d \chi/2} T^\chi Z(X/\mathbb{F}_q, T),$$
*where $\chi = \sum_i (-1)^i \dim H^i$ is the Euler characteristic.*

*(iii) Betti numbers: If $X$ is the reduction mod $p$ of a smooth projective variety $\widetilde{X}$ over a number ring, then $\dim H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{F}}_q}, \mathbb{Q}_\ell)$ equals the $i$-th topological Betti number of $\widetilde{X}(\mathbb{C})$.*

*(iv) Riemann Hypothesis: The eigenvalues $\alpha_{i,j}$ of $\mathrm{Frob}_q$ on $H^i_{\mathrm{\acute{e}t}}$ are algebraic integers, and each Galois conjugate satisfies*
$$|\alpha_{i,j}| = q^{i/2}.$$

*Proof.* (i)–(iii) were established, in essence, by the work of Grothendieck and his school in the 1960s: rationality and the functional equation follow from Grothendieck's construction of $\ell$-adic cohomology and the Lefschetz trace formula, while the Betti-number interpretation follows from proper base change and comparison theorems. (iv), the Riemann Hypothesis component, is Deligne's *Weil I* (1974) and *Weil II* (1980). $\square$

#### 6.4 Discussion

**Remark 6.4.1** (The "number of points" formula). Combining (i) with the Lefschetz trace formula gives
$$|X(\mathbb{F}_{q^n})| = \sum_{i=0}^{2d} (-1)^i \sum_j \alpha_{i,j}^n.$$
Bounding via (iv):
$$\left||X(\mathbb{F}_{q^n})| - q^{dn}\right| \leq C \cdot q^{(d - 1/2) n}$$
for a constant $C$ depending on $X$. For $X = $ an elliptic curve ($d = 1$): $|X(\mathbb{F}_{q})| = q + 1 - a$, with $|a| \leq 2 \sqrt{q}$ — the celebrated Hasse bound.

**Remark 6.4.2** (The role of purity). The precise condition on $|\alpha_{i,j}|$ is called *purity of weight $i$*. For smooth projective $X$, every cohomology class in degree $i$ is pure of weight $i$. For open or singular $X$, "mixed" Hodge structures arise, and the bound becomes $|\alpha_{i,j}| \leq q^{i/2}$ rather than equality — this is the deeper content of Weil II.

**Remark 6.4.3** (Zeta functions of number fields). The analogue of the Weil conjectures for number fields is the Riemann Hypothesis for Dedekind zeta functions, which remains open. The unconditional Chebotarev theorem (Chapter 3) uses weaker tools; conditional "effective Chebotarev" under GRH gives quantitatively stronger results.

#### 6.5 Revised Passage

The author proposes:

> **Problem (Weil, 1949):** For a smooth projective variety $X$ over $\mathbb{F}_q$, how does the number of $\mathbb{F}_{q^n}$-points grow with $n$, and what structural properties govern the growth?
>
> **Solution (Grothendieck's school, 1960s; Deligne, 1974).** Weil's four conjectures — rationality of $Z(X, T)$, functional equation, topological Betti-number interpretation, and the "Riemann hypothesis" $|\alpha_{i,j}| = q^{i/2}$ — were fully established by 1974. The first three follow from Grothendieck's construction of $\ell$-adic cohomology and the associated Lefschetz trace formula; the fourth, the most difficult, is Deligne's theorem.
>
> The resulting bound on point-counts is
> $$\left||X(\mathbb{F}_{q^n})| - q^{dn}\right| \leq C \cdot q^{(d - 1/2) n},$$
> which for an elliptic curve ($d = 1$) recovers the Hasse bound $|a_p| \leq 2\sqrt{p}$.

---

### Chapter 7: Modularity and Fermat's Last Theorem

This chapter addresses §3.8 of Part 2, concerning the Taniyama–Shimura–Weil conjecture, Wiles's theorem, and the proof of Fermat's Last Theorem.

#### 7.1 The Original Statement

> **Problem (Fermat, 1637):** For $n \geq 3$, $x^n + y^n = z^n$ has no positive integer solutions.
>
> **Solution (Wiles, 1995):** Two entirely different étale sheaves — one from an elliptic curve, one from a modular form — produce **identical light patterns at every building** $\mathbb{F}_3, \mathbb{F}_5, \mathbb{F}_7, \mathbb{F}_{13}, \mathbb{F}_{17}, \ldots$ This "miraculous match" (the Taniyama-Shimura conjecture, proved by Wiles for the semistable case) implies Fermat's Last Theorem.

#### 7.2 Nature of the Simplification

The statement is correct but elides the logical structure of the proof and the full historical credit. Specifically:

**First**, Wiles (1995) proved modularity for *semistable* elliptic curves over $\mathbb{Q}$; the full modularity theorem (for all elliptic curves over $\mathbb{Q}$) was established by Breuil, Conrad, Diamond, and Taylor (2001).

**Second**, the reduction from modularity to Fermat's Last Theorem is not itself Wiles's work but Ribet's theorem (1986): Ribet showed that the existence of a counter-example to Fermat's Last Theorem would produce a semistable elliptic curve (the Frey curve) whose associated mod-$\ell$ Galois representation is both irreducible and fails to be modular — contradicting modularity of semistable elliptic curves.

**Third**, the "miraculous match" in the passage, though vivid, is a specific technical claim: equality of traces of Frobenius on both sides, $a_p(E) = a_p(f)$ for every unramified prime $p$, where $E$ is the elliptic curve and $f$ the weight-2 newform. This is the content of modularity for $E$.

#### 7.3 Precise Formulation

**Theorem 7.3.1** (Modularity for semistable elliptic curves; Wiles 1995, Taylor–Wiles 1995). *Let $E/\mathbb{Q}$ be a semistable elliptic curve with conductor $N$. Then there exists a weight-$2$ newform $f \in S_2(\Gamma_0(N))$ such that for every prime $p \nmid N$,*
$$a_p(E) = a_p(f),$$
*where $a_p(E) = p + 1 - \#E(\mathbb{F}_p)$ and $a_p(f)$ is the $p$-th Fourier coefficient of $f$.*

**Theorem 7.3.2** (Modularity theorem, full version; Breuil–Conrad–Diamond–Taylor, 2001). *Every elliptic curve $E/\mathbb{Q}$ is modular.*

**Theorem 7.3.3** (Ribet's theorem, 1986). *Suppose $f \in S_2(\Gamma_0(Np))$ is a newform such that the mod-$\ell$ Galois representation $\overline{\rho}_{f, \ell}$ is absolutely irreducible and arises from a cusp form of level $N$. Then $f$ itself is congruent mod $\ell$ to a newform of level $N$.*

**Theorem 7.3.4** (Fermat's Last Theorem; Wiles 1995, via Ribet 1986). *For $n \geq 3$, the equation $x^n + y^n = z^n$ has no solutions in positive integers.*

*Proof sketch.* It suffices to prove the result for $n = 4$ (classical, Fermat himself) and for $n = \ell$ an odd prime. Suppose $a^\ell + b^\ell = c^\ell$ with $abc \neq 0$; one may assume $(a, b, c)$ pairwise coprime. Form the *Frey elliptic curve*
$$E_{a,b,c} : y^2 = x(x - a^\ell)(x + b^\ell).$$
Frey (1986) observed that this curve has remarkable properties (its discriminant and conductor have very special forms). Ribet's theorem, applied to the mod-$\ell$ representation of $E_{a,b,c}$, shows that if $E_{a,b,c}$ is modular, then there is a weight-$2$ newform of level $2$, which is impossible ($S_2(\Gamma_0(2)) = 0$). But Wiles's theorem shows that $E_{a,b,c}$, being semistable, is modular. Contradiction. $\square$

#### 7.4 Discussion

**Remark 7.4.1** (The structure of the proof). The logical chain is:
$$\text{(Counter-example to FLT)} \xRightarrow{\text{Frey, 1986}} \text{(Frey curve exists)} \xRightarrow{\text{Ribet, 1986}} \text{(Frey curve not modular)} \xRightarrow{\text{Wiles, 1995}} \text{contradiction}.$$
Each arrow was a major theorem in its own right. The celebrated "proof of Fermat's Last Theorem" is the *composition* of these arrows.

**Remark 7.4.2** (What Wiles actually proved). Wiles's theorem (now called the *modularity theorem for semistable elliptic curves*) is a statement about the equality of two Galois representations:
- $\rho_{E, \ell} : G_{\mathbb{Q}} \to \mathrm{GL}_2(\mathbb{Q}_\ell)$, associated to the $\ell$-adic Tate module of $E$;
- $\rho_{f, \ell} : G_{\mathbb{Q}} \to \mathrm{GL}_2(\mathbb{Q}_\ell)$, associated to a weight-2 newform $f$.
Modularity asserts these are isomorphic. The characteristic polynomial match $a_p(E) = a_p(f)$ at every unramified $p$ is, by Chebotarev, equivalent to isomorphism of the representations.

**Remark 7.4.3** (The Langlands philosophy). Modularity is a special case (the "$\mathrm{GL}_2$ case for elliptic curves") of the general Langlands correspondence:
$$\{n\text{-dim'l } \ell\text{-adic Galois reps of } G_{\mathbb{Q}}\} \leftrightarrow \{\text{automorphic reps of } \mathrm{GL}_n(\mathbb{A}_{\mathbb{Q}})\}.$$
For $n = 1$, this is class field theory (established in the 1920s–1940s). For $n = 2$ (elliptic curves, Maass forms, etc.), modularity is a highly non-trivial case. For $n \geq 3$, the correspondence is still being actively developed.

#### 7.5 Revised Passage

> **Fermat's Last Theorem.** For $n \geq 3$, the equation $x^n + y^n = z^n$ has no positive integer solutions.
>
> **Proof structure (Frey 1986, Ribet 1986, Wiles 1995, completed BCDT 2001).** A counter-example would produce an elliptic curve — Frey's construction — whose mod-$\ell$ Galois representation is both irreducible and fails to be modular. Ribet's theorem converts non-modularity of the Frey curve into the non-existence of a certain low-level modular form, a state of affairs incompatible with Wiles's theorem that every semistable elliptic curve is modular.
>
> **Wiles's modularity theorem.** For every semistable elliptic curve $E/\mathbb{Q}$, the Galois representation $\rho_{E, \ell}$ on the $\ell$-adic Tate module is isomorphic to the Galois representation $\rho_{f, \ell}$ arising from a weight-$2$ newform $f$. Equivalently, the Frobenius traces agree: $a_p(E) = a_p(f)$ for every prime $p$ of good reduction.
>
> The full modularity theorem (for all elliptic curves over $\mathbb{Q}$, not just semistable ones) was completed in 2001 by Breuil, Conrad, Diamond, and Taylor.

---

### Chapter 8: $p$-adic Hodge Theory and Fontaine's Period Rings

This chapter addresses §3.7b of Part 2, at the 🔬 (graduate) level.

#### 8.1 The Original Statement

> $p$-adic Hodge theory (Fontaine, Faltings, Bhatt-Morrow-Scholze) constructs a "mysterious isomorphism" between $H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{Q}}_p}, \mathbb{Q}_p)$ and $H^i_{\mathrm{dR}}(X/\mathbb{Q}_p)$ via Fontaine's period rings $B_{\mathrm{dR}}, B_{\mathrm{cris}}$.

#### 8.2 Nature of the Simplification

The passage is correct but condenses a substantial body of theory. Three clarifications will help the reader consulting Fontaine–Ouyang or Brinon–Conrad:

**First**, the "mysterious isomorphism" is not between $H^i_{\mathrm{\acute{e}t}}$ and $H^i_{\mathrm{dR}}$ directly, but between their base-changes to specific period rings. The precise isomorphism is
$$H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{Q}}_p}, \mathbb{Q}_p) \otimes_{\mathbb{Q}_p} B_{\mathrm{dR}} \cong H^i_{\mathrm{dR}}(X/\mathbb{Q}_p) \otimes_{\mathbb{Q}_p} B_{\mathrm{dR}}.$$
The period ring $B_{\mathrm{dR}}$ is itself a highly nontrivial object, constructed as a certain completion of $W(\mathbb{C}_p^{\flat})[1/p]$.

**Second**, the rings $B_{\mathrm{dR}}, B_{\mathrm{cris}}, B_{\mathrm{st}}, B_{\mathrm{HT}}$ form a hierarchy, each suited to a different type of variety: $B_{\mathrm{HT}}$ for Hodge–Tate (smooth proper), $B_{\mathrm{dR}}$ for de Rham, $B_{\mathrm{cris}}$ for smooth proper with good reduction, $B_{\mathrm{st}}$ for semistable reduction. The omission of $B_{\mathrm{st}}$ in Part 2 is a matter of brevity, not error.

**Third**, the recent perspective (Bhatt–Morrow–Scholze 2018+) unifies these constructions via the prismatic cohomology framework, providing a more conceptual foundation.

#### 8.3 Precise Formulation

**Theorem 8.3.1** (Fontaine's $B_{\mathrm{dR}}$-conjecture, proved by Faltings 1988). *Let $X$ be a smooth proper variety over $\mathbb{Q}_p$. Then there is a canonical $G_{\mathbb{Q}_p}$-equivariant isomorphism*
$$H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{Q}}_p}, \mathbb{Q}_p) \otimes_{\mathbb{Q}_p} B_{\mathrm{dR}} \cong H^i_{\mathrm{dR}}(X/\mathbb{Q}_p) \otimes_{\mathbb{Q}_p} B_{\mathrm{dR}},$$
*compatible with the filtrations on both sides.*

**Remark 8.3.2** (Content of the theorem). Taking $G_{\mathbb{Q}_p}$-invariants on both sides and using $B_{\mathrm{dR}}^{G_{\mathbb{Q}_p}} = \mathbb{Q}_p$ (with its natural filtration), one recovers $H^i_{\mathrm{dR}}$ from $H^i_{\mathrm{\acute{e}t}}$ as a "Galois invariant." The Galois action on $H^i_{\mathrm{\acute{e}t}}$ together with the $B_{\mathrm{dR}}$-filtration thus determines the de Rham cohomology.

**Theorem 8.3.3** ($B_{\mathrm{cris}}$-conjecture, proved by Faltings 1988 / Fontaine–Messing 1987). *For $X$ smooth proper with good reduction, the isomorphism above descends to $B_{\mathrm{cris}}$: there is a canonical $G_{\mathbb{Q}_p}$-equivariant isomorphism*
$$H^i_{\mathrm{\acute{e}t}}(X_{\overline{\mathbb{Q}}_p}, \mathbb{Q}_p) \otimes_{\mathbb{Q}_p} B_{\mathrm{cris}} \cong H^i_{\mathrm{cris}}(X_0/W(k)) \otimes_{W(k)} B_{\mathrm{cris}},$$
*where $X_0$ is the special fibre.*

#### 8.4 Discussion

**Remark 8.4.1** (Why "periods"?). The name "period ring" evokes the classical theory of periods of differential forms: for a complex variety $X(\mathbb{C})$, the integral $\int_\gamma \omega$ of a holomorphic form $\omega \in H^i_{\mathrm{dR}}$ over a cycle $\gamma \in H_i^{\mathrm{sing}}$ gives a complex number, the "period." Fontaine's rings play the analogous role in the $p$-adic world, mediating between étale and de Rham cohomology.

**Remark 8.4.2** (Modern perspective). Bhatt–Morrow–Scholze (2018) introduced *prismatic cohomology* $\mathrm{H}^i_{\Delta}(X)$, which specialises to each of crystalline, de Rham, étale, and Hodge–Tate cohomology via appropriate base changes. This unifies Fontaine's constructions within a single framework.

---

## Part IV: Sheaf Neural Networks and Related AI

### Chapter 9: Cellular Sheaves vs. Étale Sheaves

This chapter addresses §4.1 of Part 2, concerning cellular sheaves and their relation to étale sheaves.

#### 9.1 The Original Statement

From §4.1, at the 🔬 level:

> **Important note:** The "sheaf" in Bodnar et al. (2022) is a *cellular sheaf*, belonging to algebraic topology — not the étale sheaf of algebraic geometry. They differ in abstraction level, but share the structure of "assigning a vector space to each point and connecting adjacent spaces by linear maps."

From §6, at the 🔬 level:

> Bodnar et al.'s cellular sheaf is a covariant functor $\mathcal{F} : \mathrm{Face}(G) \to \mathbf{Vect}_{\mathbb{R}}$ on the face-relation poset. In general category theory, a presheaf is a *contravariant* functor $\mathcal{C}^{\mathrm{op}} \to \mathbf{Set}$; the cellular sheaf reverses the direction of restriction maps.

#### 9.2 Nature of the Simplification

The passages are correct. The refinement consists of (a) placing the cellular/étale distinction within the larger taxonomy of sheaves; (b) clarifying the precise categorical definition of a cellular sheaf and why its restriction maps point "up" (from lower cells to higher cells) rather than "down" as in the classical topological case; and (c) explaining precisely what is lost in the passage from cellular sheaves to Sheaf Neural Networks.

#### 9.3 The Taxonomy of Sheaves

The modern notion of "sheaf" encompasses several distinct mathematical structures sharing common categorical features:

**Classical sheaf on a topological space.** Given a topological space $X$, a sheaf of sets on $X$ is a contravariant functor $\mathcal{F} : \mathrm{Open}(X)^{\mathrm{op}} \to \mathbf{Set}$ satisfying the sheaf axiom: for any open cover $\{U_i\}$ of an open $U \subseteq X$, the diagram
$$\mathcal{F}(U) \to \prod_i \mathcal{F}(U_i) \rightrightarrows \prod_{i,j} \mathcal{F}(U_i \cap U_j)$$
is an equaliser. The restriction map $\mathcal{F}(U) \to \mathcal{F}(V)$ (for $V \subseteq U$) reverses inclusion.

**Sheaf on a Grothendieck topology (site).** A generalisation in which one replaces $\mathrm{Open}(X)$ by an arbitrary category $\mathcal{C}$ equipped with a notion of covering. Étale sheaves are sheaves on the site $X_{\mathrm{\acute{e}t}}$.

**Cellular sheaf (Curry 2014).** A sheaf valued in vector spaces, on a regular CW complex (or, more generally, a cell complex), in which the base category is the face-relation poset $\mathrm{Face}(G)$ with $\sigma \leq \tau$ whenever $\sigma$ is a face of $\tau$. A cellular sheaf is a *covariant* functor $\mathcal{F} : \mathrm{Face}(G) \to \mathbf{Vect}$, with restriction maps $\mathcal{F}_{\sigma \trianglelefteq \tau} : \mathcal{F}(\sigma) \to \mathcal{F}(\tau)$ pointing from lower-dimensional cells to higher-dimensional cells.

**Sheaf on a graph (special case).** If $G = (V, E)$ is a graph viewed as a 1-dimensional CW complex, the face-relation poset has vertices $v$ and edges $e$, with $v \leq e$ iff $v$ is an endpoint of $e$. A cellular sheaf then assigns vector spaces $\mathcal{F}(v), \mathcal{F}(e)$ and linear maps $\mathcal{F}_{v \trianglelefteq e} : \mathcal{F}(v) \to \mathcal{F}(e)$.

#### 9.4 Why Restriction Maps Point "Up"

The reversal of direction (compared to classical sheaves on topological spaces) merits explanation, as it confuses readers transitioning from Hartshorne to Curry.

**For a classical topological sheaf**, restrictions $\mathcal{F}(U) \to \mathcal{F}(V)$ for $V \subseteq U$ go from "more information" (sections over a larger open set) to "less information" (sections over a smaller open set). This is contravariant with respect to inclusion.

**For a cellular sheaf**, the picture is dualised. A vertex $v \in V$ is a "smaller" (lower-dimensional) object than an edge $e$ containing it; one thinks of $e$ as being assembled from the data at its endpoints $v$. The restriction $\mathcal{F}_{v \trianglelefteq e}$ then specifies "how the vertex data is to be recorded at the edge level." The direction is covariant with respect to the face relation.

Formally, a cellular sheaf is equivalent to a classical sheaf on the *opposite* poset, or to a cosheaf on the original poset. The conventions in Curry (2014) and Hansen–Ghrist (2019) elect the covariant formulation for its notational convenience in spectral applications.

#### 9.5 What is "Sheaf" in Sheaf Neural Networks?

In a Sheaf Neural Network (Bodnar et al. 2022), the following simplifications are made relative to the general cellular-sheaf framework:

- Only $0$- and $1$-dimensional cells (vertices and edges) are considered.
- Stalks are identified with $\mathbb{R}^d$ for a fixed $d$ (the stalk dimension).
- Restriction maps $\mathcal{F}_{v \trianglelefteq e}$ are parameterised as learnable linear maps in $\mathbb{R}^{d \times d}$.
- The "sheaf Laplacian" $\Delta_{\mathcal{F}} = \delta_{\mathcal{F}}^\top \delta_{\mathcal{F}}$ is used as a diffusion operator for graph neural network message passing.

The *sheaf structure axiom* — the gluing condition that a classical sheaf must satisfy — is relaxed in SNNs: arbitrary configurations of restriction maps are permitted during training, and the network's training objective is to find restriction maps that minimise a task-specific loss. The gluing condition is, however, present in the limit: an optimal SNN for a regression task finds restriction maps such that the minimum-loss configuration corresponds to a (generalised) section of the sheaf.

#### 9.6 The Cellular–Étale Contrast, Made Precise

**The analogy.** Both cellular and étale sheaves are functors from a base category to a target category (vector spaces, for cellular; abelian groups or sets, for étale), and both satisfy locality/gluing axioms in their respective sites.

**The disanalogy.** The base category for a cellular sheaf is discrete (a poset of cells); for an étale sheaf, it is a Grothendieck topology (the étale site of a scheme). The target category for a cellular sheaf is typically $\mathbf{Vect}$; for an étale sheaf of $\ell$-adic type, it is a category of $\ell$-adic systems. The symmetry groups associated are $\mathrm{GL}(\mathcal{F}(\sigma))$ (a matrix group, continuous) vs. the Galois group $G_{\mathbb{Q}}$ (profinite, discrete-ish).

**Why cellular sheaves are AI-compatible and étale sheaves are not.** The restriction maps $\mathcal{F}_{v \trianglelefteq e}$ of a cellular sheaf live in a continuous parameter space (the general linear group), permitting gradient-based optimisation. The analogous data for an étale sheaf (the Galois-group action on the stalk) live in a profinite group with no continuous parameterisation; there is no gradient to optimise. This is the precise mathematical reason why Sheaf Neural Networks have been successfully instantiated with cellular sheaves and not with étale sheaves.

---

### Chapter 10: The Sheaf Laplacian and Sheaf Attention

This chapter addresses §§4.1 and 4.2 of Part 2.

#### 10.1 The Original Statement

From §4.1, at the 🎓 level:

> Bodnar et al. (2022) "Neural Sheaf Diffusion" (NeurIPS 2022) introduced *cellular sheaves* on graphs $G = (V, E)$:
> - Assign a vector space $\mathcal{F}(v) \cong \mathbb{R}^d$ (stalk) to each node $v$
> - Assign a linear map $\mathcal{F}_{v \trianglelefteq e} : \mathcal{F}(v) \to \mathcal{F}(e)$ (restriction map) to each edge $e = (u, v)$
> - Construct the sheaf Laplacian $\Delta_{\mathcal{F}}$
>
> The coboundary operator $\delta_{\mathcal{F}}$ computes "discrepancy" between adjacent nodes:
> $$(\delta_{\mathcal{F}} x)_e = \mathcal{F}_{u \trianglelefteq e} x_u - \mathcal{F}_{v \trianglelefteq e} x_v$$

#### 10.2 Nature of the Simplification

The passage is essentially correct. Three refinements are in order:

**First**, the coboundary formula $(\delta_{\mathcal{F}} x)_e = \mathcal{F}_{u \trianglelefteq e} x_u - \mathcal{F}_{v \trianglelefteq e} x_v$ implicitly fixes an orientation on the edge $e$: the sign convention depends on which endpoint is "source" and which is "target." A consistent orientation must be chosen to define $\delta_{\mathcal{F}}$, and the resulting $\Delta_{\mathcal{F}} = \delta_{\mathcal{F}}^\top \delta_{\mathcal{F}}$ is orientation-independent (up to isomorphism) because $\delta_{\mathcal{F}} \to -\delta_{\mathcal{F}}$ gives the same $\delta_{\mathcal{F}}^\top \delta_{\mathcal{F}}$.

**Second**, the sheaf Laplacian inherits the spectral properties of graph Laplacians — self-adjointness and positive semi-definiteness — but its kernel (the "harmonic sections") is in general a proper subspace of the traditional graph-Laplacian kernel. The kernel's dimension is precisely the number of "global sections" of the cellular sheaf, i.e., assignments of vectors $x_v \in \mathcal{F}(v)$ for all $v$ such that $\mathcal{F}_{u \trianglelefteq e} x_u = \mathcal{F}_{v \trianglelefteq e} x_v$ for every edge $e$ with endpoints $u, v$.

**Third**, the pedagogical emphasis in Part 2 on "restriction maps as translators between foreign languages" is vivid but can be made precise: the sheaf Laplacian measures the *obstruction* to gluing local sections into a global section. Its spectral decomposition captures the degree of this obstruction.

#### 10.3 Precise Formulation

**Setup.** Let $G = (V, E)$ be a finite graph with a fixed orientation on each edge (so each edge $e$ has a "head" $h(e)$ and "tail" $t(e)$).

**Definition 10.3.1** (Cellular sheaf of vector spaces). A cellular sheaf $\mathcal{F}$ on $G$ assigns:
- to each vertex $v \in V$, a finite-dimensional real vector space $\mathcal{F}(v)$;
- to each edge $e \in E$, a finite-dimensional real vector space $\mathcal{F}(e)$;
- to each incidence pair $(v, e)$ with $v$ an endpoint of $e$, a linear map $\mathcal{F}_{v \trianglelefteq e} : \mathcal{F}(v) \to \mathcal{F}(e)$.

**Definition 10.3.2** (Spaces of cochains). Define
$$C^0(\mathcal{F}) = \bigoplus_{v \in V} \mathcal{F}(v), \qquad C^1(\mathcal{F}) = \bigoplus_{e \in E} \mathcal{F}(e).$$

**Definition 10.3.3** (Coboundary operator). Define $\delta_{\mathcal{F}} : C^0(\mathcal{F}) \to C^1(\mathcal{F})$ by
$$(\delta_{\mathcal{F}} x)_e = \mathcal{F}_{h(e) \trianglelefteq e} \, x_{h(e)} - \mathcal{F}_{t(e) \trianglelefteq e} \, x_{t(e)}.$$

**Definition 10.3.4** (Sheaf Laplacian). Equip $C^0$ and $C^1$ with the direct-sum inner products, and define
$$\Delta_{\mathcal{F}} = \delta_{\mathcal{F}}^\top \, \delta_{\mathcal{F}} : C^0(\mathcal{F}) \to C^0(\mathcal{F}).$$

**Proposition 10.3.5** (Basic properties of the sheaf Laplacian). $\Delta_{\mathcal{F}}$ *is self-adjoint and positive semi-definite. Its kernel is the space of* global sections *of $\mathcal{F}$:*
$$\ker \Delta_{\mathcal{F}} = H^0(\mathcal{F}) := \{x \in C^0(\mathcal{F}) : \mathcal{F}_{h(e) \trianglelefteq e} \, x_{h(e)} = \mathcal{F}_{t(e) \trianglelefteq e} \, x_{t(e)} \text{ for all } e \in E\}.$$

*Proof.* Self-adjointness: $\Delta_{\mathcal{F}}^\top = \delta_{\mathcal{F}}^\top (\delta_{\mathcal{F}}^\top)^\top = \delta_{\mathcal{F}}^\top \delta_{\mathcal{F}} = \Delta_{\mathcal{F}}$. Positive semi-definiteness: $\langle \Delta_{\mathcal{F}} x, x \rangle = \|\delta_{\mathcal{F}} x\|^2 \geq 0$. Kernel: $\Delta_{\mathcal{F}} x = 0 \iff \delta_{\mathcal{F}} x = 0 \iff$ global-section condition. $\square$

**Proposition 10.3.6** (Recovery of the standard graph Laplacian). *If $\mathcal{F}$ is the "trivial" sheaf with $\mathcal{F}(v) = \mathcal{F}(e) = \mathbb{R}$ and all restriction maps equal to $\mathrm{id}_{\mathbb{R}}$, then $\Delta_{\mathcal{F}}$ coincides with the standard graph Laplacian $L(G) = D - A$, where $D$ is the degree matrix and $A$ the adjacency matrix.*

#### 10.4 Sheaf Attention: The Attentive Variant

From §4.2 of Part 2:

> **SheafAN attention:** Extends GAT's scalar weight $\alpha_{ij}$ to matrix-valued *restriction maps* $\mathcal{F}_{v \trianglelefteq e} \in \mathbb{R}^{d \times d}$.

**Remark 10.4.1** (Precise formulation). In a Sheaf Attention Network, the restriction maps are computed dynamically as a function of the node features:
$$\mathcal{F}_{v \trianglelefteq e}^{(t)} = \Phi_\theta(x_v^{(t)}, x_u^{(t)}) \in \mathbb{R}^{d \times d},$$
for some neural network $\Phi_\theta$. The sheaf Laplacian $\Delta_{\mathcal{F}^{(t)}}$ is thus itself a function of the current state, and the diffusion equation
$$\frac{dX}{dt} = -\Delta_{\mathcal{F}(X)} \, X$$
becomes non-linear in $X$. This is the attentive analogue of Neural Sheaf Diffusion, where $\Delta_{\mathcal{F}}$ was fixed by learned parameters independent of $X$.

**Remark 10.4.2** (GAT as a special case). GAT corresponds to the case $d = 1$ (scalar stalks) and $\mathcal{F}_{v \trianglelefteq e}^{(t)} = \alpha_{uv}^{(t)}$ a scalar attention weight. SheafAN thus strictly generalises GAT in the sense of allowing higher-dimensional stalks and matrix-valued "attention."

---

### Chapter 11: Singular Learning Theory and the RLCT

This chapter addresses §4.3 of Part 2, concerning Watanabe's Singular Learning Theory.

#### 11.1 The Original Statement

From §4.3, at the 🎓 and 📐 levels:

> Watanabe quantified the "sharpness" of these singularities using the *Real Log Canonical Threshold (RLCT)* $\lambda$:
> - Regular models (linear regression, etc.): $\lambda = d/2$
> - Singular models (neural networks): $\lambda < d/2$ — effective dimension is reduced by singularities
>
> Watanabe's free energy formula:
> $$F_n = n L_n(w_0) + \lambda \log n - (m - 1) \log \log n + O_p(1)$$

#### 11.2 Nature of the Simplification

The formulas are correct but a reader consulting Watanabe (2009) or (2018) will need several clarifications:

**First**, the RLCT is defined relative to a *prior distribution* $\varphi(w)$ and a Kullback–Leibler divergence $K(w)$ (the "empirical error at parameter $w$"). It is not an intrinsic property of the model alone. Different priors yield different RLCTs, although the dominant contributions in the asymptotics are typically invariant.

**Second**, the precise statement of the $\lambda = d/2$ identity for "regular models" requires specifying what "regular" means: in Watanabe's terminology, a statistical model $p(x | w)$ is *regular* at a true parameter $w_0$ if the Fisher information matrix $I(w_0)$ is strictly positive definite (equivalently, if the zero set of $K(w)$ is a single point with non-degenerate Hessian). Under this condition and a suitable prior, $\lambda = d/2$.

**Third**, the asymptotic expansion has a subtler structure than a one-line formula suggests. The multiplicity $m$ in $(m - 1) \log \log n$ is the *multiplicity of the RLCT pole* — a second invariant of the singularity, distinct from $\lambda$ itself.

#### 11.3 Precise Formulation

**Setup.** Let $\{p(x | w) : w \in W\}$ be a statistical model with parameter space $W \subseteq \mathbb{R}^d$, and let $q(x)$ be the true data-generating distribution. Define the Kullback–Leibler divergence
$$K(w) = \int q(x) \log \frac{q(x)}{p(x | w)} \, dx \geq 0,$$
and the zero set $W_0 = \{w \in W : K(w) = 0\}$. Assume $W_0 \neq \emptyset$ (the model is realisable). Let $\varphi(w)$ be a prior density on $W$.

**Definition 11.3.1** (Real log canonical threshold). The RLCT $\lambda$ and its multiplicity $m$ are defined by the asymptotic behaviour of the zeta function
$$\zeta(s) = \int_W K(w)^s \, \varphi(w) \, dw,$$
which converges for $\mathrm{Re}(s) > 0$ and has a meromorphic continuation to $s \in \mathbb{C}$. The rightmost pole of $\zeta(s)$ is at $s = -\lambda$ (a negative real number), with multiplicity $m$.

**Theorem 11.3.2** (Hironaka's resolution of singularities, 1964). *Given any real analytic function $K(w)$ with $K(w_0) = 0$, there exist an analytic manifold $U$ and a proper analytic map $g : U \to W$ such that, in local coordinates on $U$, $K(g(\tilde{w}))$ is a "normal crossing" of the form*
$$K(g(\tilde{w})) = \tilde{w}_1^{k_1} \tilde{w}_2^{k_2} \cdots \tilde{w}_d^{k_d} \cdot u(\tilde{w}),$$
*where $u$ is a nowhere-vanishing analytic function and $k_i \geq 0$ are non-negative integers.*

*Proof.* Hironaka (1964), for which Hironaka was awarded the Fields Medal. $\square$

**Theorem 11.3.3** (Watanabe's free-energy formula, 2009). *Under regularity assumptions on $p(x | w)$ and $q(x)$, the Bayesian free energy*
$$F_n = -\log \int_W \prod_{i=1}^n p(X_i | w) \, \varphi(w) \, dw$$
*admits the asymptotic expansion*
$$F_n = n \, L_n(w_0) + \lambda \log n - (m - 1) \log \log n + O_p(1),$$
*where $L_n(w_0)$ is the empirical KL divergence at $w_0$, $\lambda$ is the RLCT, and $m$ is its multiplicity.*

*Proof.* Watanabe (2009), Main Theorem 6.8. $\square$

**Theorem 11.3.4** (Regular-model specialisation). *If the model is regular at $w_0$ — i.e., the Fisher information matrix $I(w_0)$ is positive definite and $W_0 = \{w_0\}$ is a single non-degenerate point — then $\lambda = d/2$ and $m = 1$. The expansion reduces to*
$$F_n = n L_n(w_0) + \frac{d}{2} \log n + O_p(1),$$
*recovering BIC (Bayesian Information Criterion).*

#### 11.4 Discussion

**Remark 11.4.1** (Why $\lambda < d/2$ for neural networks). A neural network $p(x | w)$ typically has symmetries — permutations of hidden units, sign flips, and in ReLU networks, scaling symmetries — which force $W_0$ to be a positive-dimensional algebraic variety rather than a single point. Hironaka's resolution reveals the singularity structure, and the resulting $\lambda$ is strictly less than $d/2$. The precise value depends on the architecture and is non-trivial to compute analytically; MCMC-based numerical estimation is often used (see Wei–Murfet et al. 2022).

**Remark 11.4.2** (Why generalisation is improved). Smaller $\lambda$ implies a smaller penalty term $\lambda \log n$ in the free energy, meaning less "effective complexity" at fixed $n$. Intuitively, the singularity structure of $W_0$ pools posterior mass onto effective directions in parameter space, performing an automatic form of regularisation. This is Watanabe's formalisation of Occam's razor in singular models.

**Remark 11.4.3** (Relation to the Weil conjectures). The zeta function $\zeta(s)$ used in the RLCT definition is, remarkably, a direct analogue of the Hasse–Weil zeta function studied in Chapter 6 above. In both settings, singularity structure is encoded in the analytic properties (poles, residues) of a zeta function; in both, resolution of singularities plays a central role. This structural parallel, and not just a superficial one, is the deepest reason that "algebraic geometry is entering deep learning." See Watanabe (2018), Chapter 1, for further discussion of this analogy.

---

## Part V: Low-Priority Refinements

### Chapter 12: Historical Attribution and Language

#### 12.1 "200-year-old algebraic geometry"

The subtitle of the Buildings in the Desert series describes the mathematics involved as "200-year-old algebraic geometry." A more precise accounting:

- The earliest ancestors of modern algebraic geometry — the study of algebraic curves by Euler, Abel, Jacobi, Riemann — date to roughly 1750–1860, giving 170–275 years of history.
- Scheme theory, the main tool used in Part 2, dates from Grothendieck's work in 1957–1970, giving 55–70 years.
- Étale cohomology dates from SGA 4 (1972), giving 54 years.
- Cellular sheaves as used in Sheaf Neural Networks date from Curry (2014), giving 12 years.

The "200-year" figure is therefore best read as an evocation of the general ancestry of algebraic geometry, not a precise chronology of the tools employed. A future edition might replace it with language such as "a deep mathematical heritage, culminating in Grothendieck's revolution of the 1960s."

#### 12.2 "Galois group" vs. "profinite Galois group"

Part 2 occasionally uses "Galois group" without specifying "absolute" or "finite." Context usually resolves the ambiguity, but explicit qualification would aid the reader: $G_{\mathbb{Q}}$ is the absolute Galois group, a profinite group; $\mathrm{Gal}(K/\mathbb{Q})$ for $K/\mathbb{Q}$ finite is a finite group. The profinite structure is used critically in the sheaf–representation equivalence (Chapter 4 above).

#### 12.3 "Sheaf" disambiguation

As emphasised in the opening essay of Part 2's author (and in Chapter 9 of these notes), the word "sheaf" in AI literature almost always means "cellular sheaf" (in Curry's sense), not "étale sheaf." When speaking to mixed audiences, explicit qualification — "cellular sheaf," "sheaf on a graph," "étale sheaf" — can avert a great deal of confusion.

---

## Appendix A: Table of Refinements

| Chapter | Part 2 Section | Topic | Priority |
|---|---|---|---|
| 2 | §3.7 | Profinite topology of $G_{\mathbb{Q}}$ | High |
| 3 | §3.7 | Frobenius elements and Chebotarev density | High |
| 4 | §3.7 | Sheaf–representation equivalence | High |
| 5 | §3.7b | Hensel's lemma and the $\sqrt{2}$ example | High |
| 6 | §3.8 | Weil conjectures and Deligne's theorem | Medium |
| 7 | §3.8 | Modularity and Fermat's Last Theorem | Medium |
| 8 | §3.7b | $p$-adic Hodge theory | Medium |
| 9 | §§4.1, 6 | Cellular vs. étale sheaves | Medium |
| 10 | §§4.1, 4.2 | Sheaf Laplacian and Sheaf Attention | Medium |
| 11 | §4.3 | Singular Learning Theory | Medium |
| 12 | Various | Historical attribution | Low |

---

## Appendix B: Notation

All notation from the Part 1 notes is used; additional notation for Part 2:

**Galois-theoretic notation:**
- $G_{\mathbb{Q}} = \mathrm{Gal}(\overline{\mathbb{Q}}/\mathbb{Q})$: absolute Galois group of $\mathbb{Q}$.
- $G_{\mathbb{Q}, S}$: Galois group unramified outside $S$.
- $[\mathrm{Frob}_p]$: Frobenius conjugacy class at $p$.

**$p$-adic notation:**
- $\mathbb{Z}_p, \mathbb{Q}_p$: $p$-adic integers and rationals.
- $v_p$: $p$-adic valuation; $|-|_p$: $p$-adic absolute value.
- $\mathbb{C}_p$: $p$-adic completion of $\overline{\mathbb{Q}_p}$.
- $B_{\mathrm{dR}}, B_{\mathrm{cris}}, B_{\mathrm{st}}$: Fontaine's period rings.

**Cohomological notation:**
- $H^i_{\mathrm{\acute{e}t}}(X, \mathcal{F})$: étale cohomology.
- $H^i_{\mathrm{dR}}(X/K)$: de Rham cohomology.
- $H^i_{\mathrm{cris}}(X_0 / W(k))$: crystalline cohomology.
- $\pi_1^{\mathrm{\acute{e}t}}(X, \bar{x})$: étale fundamental group.
- $T_\ell(E) = \varprojlim_n E[\ell^n]$: $\ell$-adic Tate module.

**Sheaf-theoretic notation (cellular):**
- $\mathcal{F}(v), \mathcal{F}(e)$: stalk at vertex, edge.
- $\mathcal{F}_{v \trianglelefteq e}$: restriction map.
- $\delta_{\mathcal{F}}$: coboundary operator.
- $\Delta_{\mathcal{F}} = \delta_{\mathcal{F}}^\top \delta_{\mathcal{F}}$: sheaf Laplacian.
- $H^0(\mathcal{F}) = \ker \Delta_{\mathcal{F}}$: global sections.

**SLT notation:**
- $K(w)$: Kullback–Leibler divergence.
- $W_0 = \{w : K(w) = 0\}$: set of true parameters.
- $\lambda$: real log canonical threshold (RLCT).
- $m$: multiplicity of the RLCT pole.
- $F_n$: Bayesian free energy at sample size $n$.

---

## Appendix C: Exercises

### C.1 Exercises on Chapter 2 (Profinite Galois Group)

**Exercise 2.1.** Show that $G_{\mathbb{Q}}$ is uncountable of cardinality $2^{\aleph_0}$. (Hint: Construct uncountably many distinct automorphisms via transcendence arguments.)

**Exercise 2.2.** Prove that every open subgroup of $G_{\mathbb{Q}}$ has finite index.

**Exercise 2.3.** Show that a continuous homomorphism $\rho : G_{\mathbb{Q}} \to \mathrm{GL}_n(\mathbb{Q}_\ell)$ has image contained in some $\mathrm{GL}_n(\mathbb{Z}_\ell)$-conjugate.

### C.2 Exercises on Chapter 3 (Chebotarev)

**Exercise 3.1.** For $K = \mathbb{Q}(\zeta_{12})$, compute the density of primes in each Frobenius conjugacy class of $\mathrm{Gal}(K/\mathbb{Q}) \cong (\mathbb{Z}/12\mathbb{Z})^\times$.

**Exercise 3.2.** For $f(x) = x^3 - 2$, compute the Galois group and verify Chebotarev's predictions for small primes ($p \leq 100$).

**Exercise 3.3.** Prove that for any non-trivial Dirichlet character $\chi$ mod $m$, the density of primes with $\chi(p) = \zeta$ (for $\zeta$ a root of unity in the image of $\chi$) equals $1/\mathrm{order}(\chi)$.

### C.3 Exercises on Chapter 5 ($p$-adic Numbers)

**Exercise 5.1.** Determine whether $\sqrt{3} \in \mathbb{Q}_7$. If yes, compute the first three $7$-adic digits.

**Exercise 5.2.** Show that $\mathbb{Q}_p$ contains a primitive $(p-1)$-th root of unity for every odd prime $p$ (Teichmüller lifts).

**Exercise 5.3.** Prove that $\mathbb{Q}_p$ has exactly three quadratic extensions (for odd $p$): one unramified, two ramified.

### C.4 Exercises on Chapter 9–10 (Sheaf Neural Networks)

**Exercise 9.1.** Compute the sheaf Laplacian of a cycle graph $C_n$ with trivial sheaf structure, and verify it equals the standard graph Laplacian.

**Exercise 9.2.** Construct a cellular sheaf on a triangle whose space of global sections is zero-dimensional (meaning the restriction maps do not admit a consistent extension).

**Exercise 10.1.** Prove that when all restriction maps $\mathcal{F}_{v \trianglelefteq e}$ are orthogonal matrices, the sheaf Laplacian $\Delta_{\mathcal{F}}$ has eigenvalues bounded above by $2 \cdot d_{\max}$ (twice the maximum degree), as in the standard graph-Laplacian case.

### C.5 Exercises on Chapter 11 (SLT)

**Exercise 11.1.** For a two-layer ReLU network with one input, one hidden unit, and one output, compute the Fisher information matrix at a typical parameter. Identify the symmetry group of the parameter space.

**Exercise 11.2.** Verify that for linear regression with $d$ parameters, $\lambda = d/2$.

**Exercise 11.3.** Compute the RLCT for the "reduced rank regression" model $y = A B x + \varepsilon$ where $A \in \mathbb{R}^{p \times r}$, $B \in \mathbb{R}^{r \times q}$, $r < \min(p, q)$. (This is a non-trivial exercise; see Aoyagi–Watanabe 2005.)

---

## Appendix D: Further Reading

### D.1 Profinite Group Theory

- **Ribes, L., & Zalesskii, P.** (2010). *Profinite Groups*. Second edition, Springer. Standard modern reference.
- **Wilson, J. S.** (1998). *Profinite Groups*. Oxford University Press. Concise graduate-level introduction.
- **Serre, J.-P.** (1997). *Galois Cohomology*. Springer. Classic source for the interaction of profinite groups and cohomology.

### D.2 Algebraic Number Theory (Advanced)

- **Neukirch, J.** (1999). *Algebraic Number Theory*. Springer Grundlehren 322. The standard reference.
- **Lang, S.** (1994). *Algebraic Number Theory*. Second edition, Springer GTM 110.
- **Serre, J.-P.** (1973). *A Course in Arithmetic*. Springer GTM 7.

### D.3 $p$-adic Numbers and Analysis

- **Gouvêa, F. Q.** (1997). *$p$-adic Numbers: An Introduction*. Second edition, Springer. Accessible graduate-level introduction.
- **Koblitz, N.** (1984). *$p$-adic Numbers, $p$-adic Analysis, and Zeta-Functions*. Second edition, Springer GTM 58.
- **Robert, A. M.** (2000). *A Course in $p$-adic Analysis*. Springer GTM 198.

### D.4 Étale Cohomology and the Weil Conjectures

- **Milne, J. S.** (1980). *Étale Cohomology*. Princeton Math. Series 33.
- **Freitag, E., & Kiehl, R.** (1988). *Étale Cohomology and the Weil Conjecture*. Springer Ergebnisse 13.
- **Deligne, P.** (1974). La conjecture de Weil I. *Publ. Math. IHÉS*, 43, 273–307. The original paper.
- **Deligne, P.** (1980). La conjecture de Weil II. *Publ. Math. IHÉS*, 52, 137–252.

### D.5 $p$-adic Hodge Theory

- **Brinon, O., & Conrad, B.** (2009). *CMI Summer School notes on $p$-adic Hodge Theory*. Freely available online.
- **Fontaine, J.-M., & Ouyang, Y.** (2022). *Theory of $p$-adic Galois Representations*. Draft available online.
- **Bhatt, B., Morrow, M., & Scholze, P.** (2018). Integral $p$-adic Hodge theory. *Publ. Math. IHÉS*, 128, 219–397.

### D.6 Modularity, Fermat's Last Theorem, and the Langlands Programme

- **Wiles, A.** (1995). Modular elliptic curves and Fermat's Last Theorem. *Annals of Math.*, 141(3), 443–551.
- **Taylor, R., & Wiles, A.** (1995). Ring-theoretic properties of certain Hecke algebras. *Annals of Math.*, 141(3), 553–572.
- **Breuil, C., Conrad, B., Diamond, F., & Taylor, R.** (2001). On the modularity of elliptic curves over $\mathbb{Q}$: Wild 3-adic exercises. *Journal of the AMS*, 14(4), 843–939.
- **Diamond, F., & Shurman, J.** (2005). *A First Course in Modular Forms*. Springer GTM 228. The standard graduate introduction.
- **Darmon, H., Diamond, F., & Taylor, R.** (1997). Fermat's Last Theorem. In *Current Developments in Mathematics 1995*.
- **Bump, D., Cogdell, J. W., de Shalit, E., Gaitsgory, D., Kowalski, E., & Kudla, S.** (2003). *An Introduction to the Langlands Program*. Birkhäuser.

### D.7 Sheaf Neural Networks (Technical)

- **Curry, J. M.** (2014). *Sheaves, Cosheaves and Applications*. Ph.D. thesis, University of Pennsylvania. arXiv:1303.3255.
- **Hansen, J., & Ghrist, R.** (2019). Toward a spectral theory of cellular sheaves. *J. Appl. Comput. Topol.*, 3, 315–358.
- **Bodnar, C., Di Giovanni, F., Chamberlain, B. P., Liò, P., & Bronstein, M. M.** (2022). Neural Sheaf Diffusion. *NeurIPS 2022*.
- **Barbero, F., et al.** (2022). Sheaf Attention Networks. *NeurIPS 2022 Workshop NeurReps (Oral)*.
- **Barbero, F., et al.** (2022). Sheaf Neural Networks with Connection Laplacians. *ICML 2022 Workshop TAG-ML*.
- **Duta, I., et al.** (2023). Sheaf Hypergraph Networks. *NeurIPS 2023*.
- **Bamberger, J., et al.** (2025). Bundle Neural Networks for message diffusion on graphs. *ICLR 2025*.

### D.8 Singular Learning Theory

- **Watanabe, S.** (2009). *Algebraic Geometry and Statistical Learning Theory*. Cambridge Monographs on Applied and Computational Mathematics. Cambridge University Press.
- **Watanabe, S.** (2018). *Mathematical Theory of Bayesian Statistics*. CRC Press.
- **Wei, S., Murfet, D., Gong, M., Li, H., Gell-Redman, J., & Quella, T.** (2022). Deep Learning is Singular, and That's Good. *IEEE Transactions on Neural Networks and Learning Systems*.
- **Hoogland, J., van Wingerden, S., & Murfet, D.** (2024). Developmental landscape of in-context learning. arXiv:2402.02364.
- **Aoyagi, M., & Watanabe, S.** (2005). Stochastic complexities of reduced rank regression in Bayesian estimation. *Neural Networks*, 18(7), 924–933.

---

## Conclusion and Prospectus

The present Companion Notes to Part 2 extend the project begun in the Part 1 notes: to transform an accessible pedagogical exposition into a rigorously precise one, without thereby diminishing its accessibility.

The refinements assembled here are more technically demanding than those of Part 1, reflecting the greater depth of the mathematics treated in Part 2 itself. Readers who have worked through the profinite Galois theory of Chapters 2–4, the $p$-adic analysis of Chapter 5, the Weil–modularity–Hodge trio of Chapters 6–8, and the sheaf-neural-network and SLT refinements of Chapters 9–11, will be equipped to read the primary literature — Milne's *Étale Cohomology*, Wiles's *Annals* paper, Watanabe's *Algebraic Geometry and Statistical Learning Theory*, and Bodnar et al.'s *Neural Sheaf Diffusion* — without the disorientation that a purely pedagogical acquaintance can produce.

As with the Part 1 notes, the present document will be revised in future versions. Readers who identify further imprecisions, or who believe that the refinements offered here are themselves insufficiently precise, are warmly invited to open issues on the GitHub repository.

A third volume of notes, accompanying Part 3 of the main series, is in preparation.

---

## Final Remarks

These Companion Notes are published alongside the article *Buildings in the Desert — Part 2*, which was originally published on Zenn at [https://zenn.dev/etalecohomology/articles/286acd9ab58a01](https://zenn.dev/etalecohomology/articles/286acd9ab58a01) on 15 March 2026.

The notes are offered in the same spirit as their companion to Part 1: that intellectual honesty in mathematical exposition requires the preservation of both the pedagogical form and the technical supplement, and that the two together represent a more complete statement of the truth than either could in isolation.

Corrections and suggestions are warmly welcomed via the GitHub Issues interface.

---

*Total length: approximately 17,000 words.*

*Author: Étale Cohomology*

*Version 1.0, April 2026*

*License: CC BY 4.0*

*Canonical source of the main article: [https://zenn.dev/etalecohomology/articles/286acd9ab58a01](https://zenn.dev/etalecohomology/articles/286acd9ab58a01)*
