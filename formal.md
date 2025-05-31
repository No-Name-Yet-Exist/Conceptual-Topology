# Index
1. Global Definition of Conceptual Topology
2. Local Semantic Flow under Z-frame
    - Identity Morphism
    - Mirror Morphism
    - Quasi-Natural Transformation
3. Semantic Shifting Morphism (σ) 
    - Semantic Operator
5. Monoid Structure of Semantic Flow (M_Z)
6. Cross-Category Flow Condition

</br>

# Global Definition of Conceptual Topology: Morphic Chain Structure

```
CT := (C, B, π: E → B, Fb := π⁻¹(b), A ≅ b ⋃ Nat(Hom(−, A), Fb))

Where:
  - C is the category of concepts (objects = words or concepts)
  - B is the base space of Z-frames (semantic continuity anchors)
  - E is the total semantic space (word vector embedding space)
  - π projects each concept to its semantic base (Z-frame)
  - Fb is the fiber (semantic morphic chain) over a base b
  - A ≅ b ⋃ Nat(Hom(−, A), Fb) interprets each concept A via its morphisms relative to its   Z-frame b (Yoneda perspective defined in appendix)
```

```
        Z = baby  
    puppy  ←   girl    //specified: size + young
     |          |
     |          |
    dog        she     //abstraction
      \        /      
        Mammal

```

</br>

# Local Semantic Flow under Z Frame

### Identity Morphism

In Category Theory, Identity Morphism is always defined.
```
id_X: X → X
such that for any f: X → Y:
f ∘ id_X = f
id_Y ∘ f = f
```

However, in Conceptual Topology, morphisms are mediated by Z frame, thus
the identity morphis is not always given unless Z is defined.

**Two Types of Identity Morphism in Conceptual Topology**
1. f: X → X | X  (Category-theoretic identity)
2. f: X → X | Z  (Mediated identity with semantic flow)


```
f: X → X | X
such that for any f: X → Y:
f ∘ id_X = f
id_Y ∘ f = f

e.g. f: dog → dog | dog
```

In Conceptual Topology there is another type of identity morphism.
This type involves semantic flow.

```
f: X → X | Z

f: X → Z
f⁻¹: Z → X
f⁻¹ ∘ f ≅ id_X
e.g. you → you | externalized perspective
     NL: you are you
```

Since the identity morphism is passes through an external anchor point,
the identity morphism is defined quasi-identical.</br>
e.g. dog → perro | собака

</br>

### Mirror Morphism Definition:
Each mirror maps conceptual transitions across vocabularies while preserving morphic identity up to rupture—that is, it allows for semantic divergence that still respects underlying structural continuity, even if exact invertibility is not preserved.

```
f : X  → Y  | Z ∈ Dᵢ
f′: X′ → Y' | Z ∈ Dᵢ₊₁
  ⇒X′ ≠ X, but cod(f) = cod(f′) | CD (CD = codomain)

We define f′ as a mirror-correspondent morphism of f under a given Z-frame,
if and only if:

∃Z: rupture(f, f′ | Z) ≠ ∅ 
∧ cod(f) = cod(f′) | CD

```

```
        Z = baby  
    puppy  ←   girl    //specified: size + young
     |          |
     |          |
    dog        she     //abstraction
      \        /      
        Mammal

```

**Note:** **Z: rupture(f, f′ | Z) ≠ ∅** means that there exists a Z-frame under which *f* and *f′* exhibit structural divergence—i.e., they are not fully invertible but still converge at the codomain level.

For example, let *Z = abstraction*. This allows a semantic transition from *girl → she* and *puppy → dog*, treating them as mirror morphisms under a shared conceptual frame.  
However, if we take *Z = agency*, a rupture emerges: *puppy → dog* lacks agency, while *girl → she* retains it. Hence, **rupture(f, f′ | agency) ≠ ∅**, yet *f* and *f′* still align toward the same codomain (e.g., *mammal*).

</br>

### Quasi-Natural Transformation of Meaning Systems

A **Morphic Chain Mirror** is a contextual correspondence between two morphic chains drawn from distinct but meaning-aligned vocabularies. This correspondence is realized through a **quasi-natural transformation** under a shared intermidiating Z-frame.

```
η: Dᵢ ⇒ Dᵢ₊₁  | CD (CD = codomain)
η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁ | Z₁, ..., f′ₙ | Zₙ}) ∘ η_Y | CD
for all fⱼ: Xⱼ → Yⱼ | Zⱼ ∈ Dᵢ,  
where f′ⱼ: η_X(Xⱼ) → η_Y(Yⱼ) | Zⱼ

Then, η is said to be a quasi-natural transformation under the Z-frame
i.e. η ∈ Mor(C) where C is the contextual meaning category
Example: η: girl → puppy | Z = baby
```

</br>

# Monoid Structure of Semantic Flow (M_Z)
In Conceptual Topology, Z is defined as a mediating point/sematinc anchor.
```
Let C and D be categories with semantic projection to Z.

π_C: C → Z  
π_D: D → Z

Or jointly:  
π: C ∪ D → Z

For each X, there exists:

f_X: X → Z  
f_X⁻¹: Z → X

such that:

f_X⁻¹ ∘ f_X ≅ id_X

For morphism f: X → Y | Z,  
this corresponds to:

f_Z: π(X) → π(Y) in Z

For any X, Y ∈ Ob(C ∪ D):

[ X ]_Z ≅ [ Y ]_Z

Then the set of semantic flow morphisms under Z forms a monoid:

M_Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }
```

```
Let C be a concept
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda's lemma and structralism

king = {Royalty⃗, Male⃗, Human⃗}
queen = {Royalty⃗, Female⃗, Human⃗} 
man = {Male⃗, Human}
woman =  {Female⃗, Human} 

{Royalty⃗, Male⃗, Human⃗} ⊖ {Male⃗} ⊕ {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} 
= queen


k₁: Human → Male | king  
k₂: Male → Royalty | king  

Then:  
k₂ ∘ k₁: Human → Royalty | king


q₁: Human → Woman | queen  
q₂: Woman → Royalty | queen  

Then:  
q₂ ∘ q₁: Human → Royalty | queen

m: Human → Male
f: Human → Female

Cross-Z-frame composition:

(k₂ ∘ k₁) ⊕ (q₂ ∘ q₁)= Human → Royalty | Z'

If higher Z' (e.g. "Humanity" or "Social Role") unifies Z = king and Z = queen:

Then:
(k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) ∈ M_Z'

```
</br>

# Definition: Semantic Shifting Morphism (σ)

```
σ: X → X | X
such that σ ⊕ f ∈ M_Z if and only if type compatibility holds:

∀ A, B, (A → B) ∘ σ is valid if:

( A >> X or X >> A )
and
( B >> X or X >> B )

Definition: Subsumption
A >> X ≡ A ⊑ X

Definition: SubsumedBy
X >> A ≡ X ⊑ A

Example:
King >> Human
Human >> Queen
```

**Semantic Operators**
Semantic Operator σ modifies morphism as follows.
```
σx. Not(x){ A ↛ B | Z}     →     Rupture under Z frame
σx. so_much(x){A → B | Z}  →     Preservation & amplification under Z frame
σx. >>(x,y)                →     Semantic Shifting (Generalization) as function form
σx. <<(x,y)                →     Downward Shifting (specialization) as function form
```

### Example: Morphic Shifting and Cross-Z-frame Semantic Flow

We consider the well-known semantic analogy:
**king - man + woman = queen**

We formalize this using Conceptual Topology's morphic flow.

```
Concept Definitions

Let C be a concept:

// (Yoneda's lemma and structuralism — concept defined by oppositional components)
C = {−OC₁, −OC₂, ..., −OCₙ}  

We define king as:

k₁: Human → Male | king  
k₂: Male → Royalty | king  

Then:  
k₂ ∘ k₁: Human → Royalty | king

We define queen as:
q₁: Human → Woman | queen  
q₂: Woman → Royalty | queen  

Then:  
q₂ ∘ q₁: Human → Royalty | queen

We define semantic editing morphisms σ within the Human frame:

σ: Human → Human | Human (A ∘ B | Human)  
= (Human → Human | Human) ⊕ (A ∘ B | Human)  
= Human → Human | Human
since:
M_Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }

Thus formally:
σ(m⁻¹ ∘ f)
= (Male → Human)∘(Human → Female) | Human ⊕ (Human → Human | Human)
= Human → Human | Human

where:
m⁻¹: Male → Human  
f: Human → Female

And:
Male >> Human  
Female >> Human

(Male → Human) ∘ (Human → Female) ⊑ (Human → Human)

Then:
(k₂ ∘ k₁) ∘ σ(m⁻¹ ∘ f): Human → Royalty | Human


Assuming a higher semantic frame Z' (e.g., Humanity, Social Role) that unifies king and queen frames:

(k₂ ∘ k₁) ∘ σ ∈ M_Z'

Thus:

king - man + woman = queen
is formalized as:  

(k₂ ∘ k₁) ∘ σ ∈ M_Z'
```
</br>

# Cross-Category Flow Condition
Conceptual Topology allows communicative diagram across categories as long as same Z is shared: shared semantic equivalence.

```
Let C and D be categories with Z-frame semantic anchoring.
If all morphisms involved are of the form:
f: X → Y | Z

and semantic equivalence holds:
∀ X, Y ∈ Ob(C ∪ D), [X]_Z ≅ [Y]_Z

then semantic flow forms a monoid over Z-frame:
M_Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }

```

**Example: Cross-Category Flow under Z-frame**</br>
This example illustrates how morphic flow can traverse categories (livestock, pet)  
as long as semantic equivalence under Z = domesticated is preserved.

```
(dog ≅ cat ≅ pig) | Z = domesticated
Ob(livestock) = {pig} 
Ob(pet) = {dog, cat}

f₁: pig → cat | Z
f₂: cat → dog | Z
f₃: dog → pig | Z
Then:
f₃ ∘ f₂ ∘ f₁: pig → pig | Z ∈ M_Z
```

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.