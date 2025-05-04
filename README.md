# What is Conceptual Topology
Conceptual Topology mainly analyzes how words, concepts, and meanings are structured and transformed, using tools from category theory and vector semantics such as word2vec. 

Conceptual Topology aims to provide a formal structure for meaning itself, bridging philosophy, linguistics, and mathematics.

The translation is currently in progress; not all content is available in English yet.
Please refer to the **Index** section for key definitions and core concepts.

This GitHub repository serves as an archive for the following account:
https://note.com/xoreaxeax


# Commutative diagrams: The Relationship of words in category theory

### king - man + woman = queen
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
  f: Composed Semantic Morphism g ∘ h ∘ r 
  h: Differential Morphism(Man → Woman)
```

```
1st Morphism: Human He is a human
2nd Morphism: He is a human, but Human is him
3rd Morphism: mammal

1st Morphism: He → Human (He is a human)
  → Existential attribution: assigning a category ("Human") to an individual ("He").

2nd Morphism: Human → He (He is a human, but Human is him)
 → Reverse attribution: turning the attributed category back into an individual reference.
 → Highlights the directionality and reversibility of meaning.
 
3rd Morphism: mammal
 → Higher-order abstraction over both "He" and "Human".
   This abstracts from individual and category to a shared ontological layer (e.g., biological classification).

He ----f----> Human
 |              |
α|              |α'
 ↓              ↓
Human <----g--- He

        ↓
       (Θ)
        ↓
      mammal

f: Propositional classification morphism (He is a Human)
g: Referential inversion morphism (Human is him)
α, α′: 2-morphisms ensuring bidirectional equivalence between He and Human
(Reversible structure)
Θ: 3rd morphism representing higher-order abstraction
(emergence of "mammal" as a shared conceptual generalization)
```

# king - man + woman = queen

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


# Semantic Additivity Principle

Any given concept A and B meet the following according to the Semantic Additivity Principle
This is observed in word2vec using black - (black - white) ≈ black (cos_sim = 0.8)

```
A = {-B},　B={-A}
A − (A − B)
= {-B} -( {-B} - {-A} )
= {-B} + ( -{-B} + {-A} ) //The additivity principle was applied
= {-A}
= B

∴　A − (A − B) ≈ B
```

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

A: Initial concept
B: Target (destination) concept
A − (A − B): Restored meaning (via additive recomposition)
(experimentally, cos_sim ≈ 0.8; approximates original A)

f: Meaning morphism (standard semantic transformation)
δ: Differential morphism — extracts Δ, the semantic difference between A and B
r: Regen morphism — applies −Δ to recover A from B
Δ: Differential — the structural difference space between A and B
```         

# The Definition Of Word
Any word that contains other words is subsumed by a higher-order concept,
and the higher-order concept is, in turn, contained within the word.
A word is itself a word.

```
Let C be a concept //e.g. black
Let OC be the opposite concept //e.g. white
C = {−OC₁, −OC₂, ..., −OCₙ}
word ≅ C and Ob(Word) ∋ word
∀ fᵢ ∈ Mor(C), ∃∞_f s.t. fᵢ ⊆ ∞_f
∀ ∞_f, ∃ Word s.t. ∞_f ⊆ Word
and then: Word≅Nat(h∞f​,Language)
id_word ≈word
```

## 概念位相論.md and 概念位相論と圏論の体系的・記号的接続.md
Those are the summary of the conceptual topology.
You can also see the formulas, word2vec experiements and other applications
These are written in Japanease, so we are afraid that please use the translator.

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.