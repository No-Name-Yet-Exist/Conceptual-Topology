# What is Conceptual Topology: 
### Category Theory × Semantics x Philosophy
Conceptual Topology mainly analyzes how words, concepts, and meanings are structured and transformed, using tools from category theory and vector semantics such as word2vec. 

Conceptual Topology aims to provide a formal structure for meaning itself, bridging philosophy, linguistics, and mathematics.

The translation is currently in progress; not all content is available in English yet.
Please refer to the **Index** section for key definitions and core concepts.

This GitHub repository serves as an archive for the following account:
https://note.com/xoreaxeax


# Commutative diagrams: The Relationship of words in category theory

### king - man + woman = queen
This relationship can be expressed as the following semantic morphism diagram

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

### quasi-natural transformation diagram

**Quasi-Natural Transformation of Meaning Systems**
```
    η: Dᵢ ⇒ Dᵢ₊₁  | Y // Y = codomain
    η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁, ..., f′ₙ}) ∘ η_Y | Y
    for all fᵢ: Xᵢ → Yᵢ | Zᵢ in Dᵢ,  
    where f′ᵢ: η_X(Xᵢ) → η_Y(Yᵢ) | Zᵢ is the image morphism under meaning translation

    Then: η is a quasi-natural transformation under Z-frame
    i.e. η ∈ Mor(C) where C is the contextual meaning category
```

```
          
   girl   ←   puppy  newer + small + specific: axis
     |         |
     |        |
   she    ←   dog        abstraction of all
      \      /       
       mammal

```

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)


### Semantic Circularity

**baby → girl → she → female → human → ape → mammal → dog → puppy →　baby**

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/baby-morphic-circle.png)

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/semantic-circulation-with-arrows.png)


D_gender: girl - she - female 
D_humanity: female - human - ape - mammal
D_canine: puppy - dog - mammal
D_baby: puppy - baby - girl

η: puppy → human_girl | baby // canine to human under baby
f: female → human // femenity to human 
η: human → dog | mammal // human to canine under mammal


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
Let OC be the opposite concept //e.g. white
C = {−OC₁, −OC₂, ..., −OCₙ} 

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
Author Verification(sha-256 2025-05-06):<br/>
verification:  a1c605499b0b1833db330db066131448793009aeafe3f17ba3f87a3a3a7910da  <br/> 
origin: dd3b3129b3b9ca51227083b2515969cc00967fe7e614c19b9a02486eade42e1b
<br/>
---
<br/>
<br/>
<br/>

Meaning doesn’t escape.  
Meaning moves.  
*f: escape → move | reduced unpredictability*

