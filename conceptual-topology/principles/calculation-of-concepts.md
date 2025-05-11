# モノイド

# 結合法則成立：
```
 (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C) が成立
Queen = {Royalty⃗, Female⃗, Human⃗} かつ King = {Royalty⃗, Male⃗, Human⃗}のとき以下が成り立つ

Queen ⊕ ({Male⃗} ⊕ −{Female⃗}) = King
(Queen ⊕ {Male⃗}) ⊕ −{Female⃗} = King
```

# 単位元（Identity Element）：
Neutral⃗ = 「意味を変えない無属性集合」

```
X ⊕ Neutral⃗ = X anything is anything
¬X ⊕ Neutral⃗ = ¬X nothing is nothing
X ⊖ Neutral⃗ = X  "dog"
Neutral⃗ ⊕ Neutral⃗ = Neutral⃗ ""
```

概念位相論的に、Neutral⃗ は恒等射に近い。

```
恒等射 idₓ : X → X

X ⊕ Neutral⃗ ≡ idₓ(X)
¬X ⊕ Neutral⃗ ≡ id_{¬X}(¬X)

つまり、Neutral⃗ は概念空間における意味的恒等射として機能する
```


# 意味集合の演算
　- 意味集合 A ∪ B = 意味融合（概念の合成）
　- 意味集合 A − B = 概念の純化 or 差異化
　
　例: king - man + woman = queen

意味集合の階層化・包含関係
　- Animal ⊃ {Dog, Cat}
　- Emotion ⊃ {Joy, Sadness}
　※仮説段階

意味集合間の射を定義することで、概念進化をモデル化
　- 例：「Stone → Tool」みたいな、意味変容の歴史パスを射で示す。
　こちらは動詞の過去形/未来形で近似的な実験データがあります。
CTL


This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
