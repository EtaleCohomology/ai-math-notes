# Buildings in the Desert — Part 3

## The "Sheaf" in NeurIPS Papers: A Correction — What AI Actually Borrowed Was the Cellular Sheaf, Not the Étale Sheaf

A dialogue-format correction to Parts 1 and 2, clarifying a common misconception in AI literature about the word "sheaf."

Part 1 と Part 2 への対話形式の訂正。AI 文献で流通している「sheaf」という語の誤解を明確にします。

---

## Publication History / 公開経緯

The Japanese version of this article was originally published on Qiita:

**https://qiita.com/etale_cohomology/items/38ebac219c97c40fc4e3**

The English translation presented here is released for the first time in this repository.

本記事の日本語版は Qiita で初出公開されました（上記 URL）。本リポジトリに収められた英訳版は、ここが初公開です。

---

## Highlight / ハイライト

Parts 1 and 2 describe the landscape of étale sheaves in algebraic geometry, suggesting the metaphor that "AI is borrowing étale sheaves." Part 3 corrects this: what Sheaf Neural Networks actually use is the *cellular sheaf* from applied algebraic topology — a mathematically distinct object that, crucially, admits differentiable operations and can therefore be trained end-to-end in PyTorch.

Part 1 と Part 2 では、代数幾何のエタール層の風景を描き、「AI がエタール層を借用している」というメタファーを提示しました。Part 3 はこれを訂正します。Sheaf Neural Networks が実際に使っているのは、応用代数トポロジーの**セルラー層**であり、これはエタール層とは数学的に別の対象です。セルラー層は微分可能な演算を許容するため、PyTorch で end-to-end に学習できます。

---

## Format / 形式

Unlike Parts 1 and 2, Part 3 is written as a dialogue between a *Young Data Scientist* and an *AI Research Scientist*. This form was chosen deliberately: the piece exists to correct a misconception, and a dialogue naturally traces the reader's path from confusion to clarity.

Part 1・Part 2 とは異なり、Part 3 は *Young Data Scientist* と *AI Research Scientist* の対話形式で書かれています。この形式は意図的な選択です。本稿は誤解を訂正することを目的としており、対話形式は読者の「混乱から明晰へ」の道筋を自然にたどります。

---

## Contents / 内容

- `article/` — The article body (English)

---

## License / ライセンス

CC BY 4.0 (Creative Commons Attribution 4.0 International)

---

## Author / 著者

Étale Cohomology
