# 概念位相論 / Conceptual Topology As Conceptual Topos
### Category Theory × Semantics x Philosophy
Conceptual Topology mainly analyzes how words, concepts, and meanings are structured and transformed, using tools from category theory and vector semantics such as word2vec. 

Conceptual Topology aims to provide a formal structure for meaning itself, bridging philosophy, linguistics, and mathematics.

The translation is currently in progress; not all content is available in English yet.
Please refer to the **Index** section for key definitions and core concepts.

### preprint
https://zenodo.org/records/15455079

### Index
https://github.com/No-Name-Yet-Exist/Articles/blob/main/Index.md

### Formal Definitions
https://github.com/No-Name-Yet-Exist/Articles/blob/main/axioms.md

This GitHub is linked with:</br>
https://note.com/xoreaxeax/n/n3711c1318d0b


# Commutative diagrams: The Relationship of words in category theory

### king - man + woman = queen
This relationship can be expressed as the following commutative diagram.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/others/king2quee.png)

```
        r
    Q ←————— W
    |        ↑
  f |        |h
    ↓        |
    K —————→ M
        g

K = king
Q = queen
M = man
W = woman

g: Differential Morphism（King → Man）
h: Differential Morphism(Man → Woman)
r: Differential Morphism（Woman → Queen）
f: Composed Semantic Morphism r ∘ h ∘ g 
```

### quasi-natural transformation diagram

**Quasi-Natural Transformation of Meaning Systems**
```
  η: Dᵢ ⇒ Dᵢ₊₁  | CD (CD = codomain)
  η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁ | Z₁, ..., f′ₙ | Zₙ}) ∘ η_Y | CD
  for all fⱼ: Xⱼ → Yⱼ | Zⱼ ∈ Dᵢ,  
  where f′ⱼ: η_X(Xⱼ) → η_Y(Yⱼ) | Zⱼ

  Then, η is said to be a quasi-natural transformation under the Z-frame
  i.e. η ∈ Mor(C) where C is the contextual meaning category
  Example: η: girl → puppy | Z = baby
```

```
          
   girl     puppy  newer + small + specific: axis
     |   　    |
     |     　  |
   she   　   dog        abstraction of all
      \     　/       
      　mammal

```

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)


### Semantic Circularity

**baby → girl → she → female → human → ape → mammal → dog → puppy →　baby**

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/semantic-circulation-with-arrows-v2.png)


```
      Z = baby
   girl   ←   puppy  young + small + specific: axis
     |         |
     |      　 |
   she    　   dog        abstraction of all
      \      /       
       mammal

```


```
D_gender: girl - she - female 
D_humanity: female - human - ape - mammal
D_canine: puppy - dog - mammal
D_baby: puppy - baby - girl

η: puppy → human_girl | baby // canine to human under baby
f: female → human // femenity to human 
η: human → dog | mammal // human to canine under mammal
```

```
1st Morphism: Human He is a human
2nd Morphism: He is a human, but Human is him
3rd Morphism: man

1st Morphism: He → Human (He is a human)
  → Existential attribution: assigning a category ("Human") to an individual ("He").

2nd Morphism: Human → He (He is a human, but Human is him)
 → Reverse attribution: turning the attributed category back into an individual reference.
 → Highlights the directionality and reversibility of meaning.
 
3rd Morphism: man
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
       man

f: Propositional classification morphism (He is a Human)
g: Referential inversion morphism (Human is him)
α, α′: 2-morphisms ensuring bidirectional equivalence between He and Human
(Reversible structure)
Θ: 3rd morphism representing higher-order abstraction
(emergence of "man" as a shared conceptual generalization)
```

# king - man + woman = queen
Concepts/meaning can be calculated as monoid, or semantic set as shown below.

```
Let C be a concept
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda's lemma and structralism

king = {Royalty⃗, Male⃗, Human⃗}
queen = {Royalty⃗, Female⃗, Human⃗} 
man = {Male⃗}
woman =  {Female⃗} 

{Royalty⃗, Male⃗, Human⃗} ⊕ {Male⃗} ⊕ {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} 
= queen
```

# Meaning Preservation Communicative Diagram
This diagram illustrates how additive semantics reconstructs conceptual continuity.
This reconstruction equation A−(A−B)≈A do not apply universally. Specific word pairs such as black and wihte shows this result.

```
A − (A − B) ≈ A

            f: A → B （black → white）
    B
    ▲
   /    \
  /        \  Δ = A − B
 /           \       
δ            ↑
 \           /
  \         /
   A <── r: −Δ


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
A word that includes itself or other words is subsumed by a higher-order concept.
That concept, in turn, is structurally embedded within the word.
Therefore, a word is a self-referential structure.

```
// A concept is a structure of oppositional differences
Let C be a concept //e.g. black
//OC be the opposite concept or not relative concept (e.g., white, not pink)
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda's perspective × Structuralism

// A word is a concept, and belongs to the category of words
word ≅ C and Ob(Word) ∋ word

// A concept is a bundle of semantic morphisms (in the word2vec sense)
// Interpretable as a more concrete model via Grothendieck fibration
∀ fᵢ ∈ Mor(C), ∃∞_f s.t. fᵢ ⊆ ∞_f

// The structure of semantic morphisms is abstracted into a word
∀ ∞_f, ∃ Word s.t. ∞_f ⊆ Word

// The ∞-structure of morphisms is deployed into the linguistic category as a natural transformation
and then: Word≅Nat(h∞f​,Language)

// Self-identity of the word: word is word
id_word ≈word
```

<br/>
<br/>  
---
<br/>
<br/>
This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
<br/>
---
<br/>
<br/>
<br/>

~~Meaning doesn’t escape.~~
~~It moves in sight.~~  
~~f: escape → move | reduced unpredictability~~

*Meaning no longer moves.*
*It just topologizes within the abstract cage.*