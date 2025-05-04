# 概念位相論とは / What is Conceptual Topology
概念位相論は意味や概念がどのように構成され変化するかを
圏論的構造やベクトルを用いて分析するものです

The conceptual topology analizes how words, concepts and meanings etc are consisted
and change through category theory and vector such as word2vec

king - man + woman = queen

{Royalty⃗, Male⃗, Human⃗} - {Male⃗} + {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} = queen


# Commutative diagrams: The Relationship of words in category theory

```
        f
     K → Q
     |     \
   r |       \ g
     ↓         \
     M' ——→ W'
         h
```
    K = king
    Q = queen
    M' = man
    W' = woman

    r: 差分射（King → Man）
    g: 差分射（Queen → Woman）
    f: 差分射 (King → Queen)
    h: 差分射 (Man → Woman)

```
He ----f----> Human
 |              |
α|              |α'
 ↓              ↓
Human <----g--- He

```

## 概念位相論.md
こちらが理論系のまとめになります

検証系が見たい場合は適用例だったり、word2vecを参照ください
proto-概念位相論は概念力学という名前で運用されていました。

本GitHubは以下のNoteの記事管理保管庫になります
https://note.com/xoreaxeax/n/n3711c1318d0b
