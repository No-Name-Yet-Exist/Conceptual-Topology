# What is Conceptual Topology
The conceptual topology analizes how words, concepts and meanings etc are consisted
and change using category theory and vector such as word2vec

This github is storage of the following account.
https://note.com/xoreaxeax



### king - man + woman = queen

```
Let C be a concept
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda's lemma and structralism

king = {Royalty⃗, Male⃗, Human⃗}
queen = {Royalty⃗, Female⃗, Human⃗} 
man = {Male⃗}
woman =  {Female⃗} 

{Royalty⃗, Male⃗, Human⃗} - {Male⃗} + {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} 
= queen
```

# Commutative diagrams: The Relationship of words in category theory

```
        f
     K → Q
     |     \
   r |       \ g
     ↓         \
     M' ——→ W'
         h
  K = king
  Q = queen
  M' = man
  W' = woman

  r: Differential Morphism（King → Man）
  g: Differential Morphism（Queen → Woman）
  f: Differential Morphism(King → Queen)
  h: Differential Morphism(Man → Woman)
```

```
He ----f----> Human
 |              |
α|              |α'
 ↓              ↓
Human <----g--- He

```

# Semantic Additivity Principle

Any given concept A and B meet the following according to the Semantic Additivity Principle
This is observed in word2vec using black - (black - white) ≈ black (cos_sim = 0.8)

A = {-B},　B={-A}
A − (A − B)
= {-B} -( {-B} - {-A} )
= {-B} + ( -{-B} + {-A} ) //The additivity principle was applied
= {-A}
= B

∴　A − (A − B) ≈ B

# Meaning Preservation Triangle

```
         f: A → B （black → white）
      B
      ▲
     / \
    /   \  Δ = A − B
   /     \       ↑
A ──────→ δ      │
          r: −Δ → A (B → A: )
```         

A: Initial concept
B: Target (destination) concept
A − (A − B): Restored meaning (via additive recomposition)
(experimentally, cos_sim ≈ 0.8; approximates original A)

f: Meaning morphism (standard semantic transformation)
δ: Differential morphism — extracts Δ, the semantic difference between A and B
r: Regen morphism — applies −Δ to recover A from B
Δ: Differential — the structural difference space between A and B


## 概念位相論.md and 概念位相論と圏論の体系的・記号的接続.md
Those are the summary of the conceptual topology.
You can see the formulas, word2vec experiements and other applications
These are written in Japanease, so we are afraid that please use the translator.
