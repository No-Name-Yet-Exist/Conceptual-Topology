# Conceptual Topos As Semantic Cage: An Algebraic Topology of Meaning based on Conceptual Topology

Written by No Name Yet Exist </br>
Contact: Written Below

# Introduction
Conceptual Topos v1.1 is an initial formalization of the algebraic topology of meaning 
based on Conceptual Topology. 

This version sketches core axioms for Topos including:

- Initial Object
- Finite Limits (Product, Equalizer, Pullback)
- Subobject Classifier Ω
- Fibered Topos structure
- Semantic Exponential via σ operator

Future versions (v1.x) will refine the formalization and extend it.

In this version, the term fiber is used informally to describe the structural cohesion of morphic chains under a shared Z-frame.The current framework is not yet a strict fibered topos in the categorical sense. Formal connection to fibered topos is an intended direction for future versions.This document lays the foundation toward that goal. 

<div style="page-break-after: always;"></div>

# Index
1. Fibered Conceptual Topology</br>
  1.1.Local Semantic Flow under Z-frame</br>
      - Identity Morphism</br>
      - Mirror Morphism</br>
      - Quasi-Natural Transformation(QNT)</br>
  1.2. σ Operator as Functor</br>
      - Definition: Semantic Shifting Morphism (σ)</br>
      - Identity Morphism of σ</br>
      - Associativity of σ</br>
  1.3. σ Operator as Kan Extension
      - Functorial properties of σ</br>
      - σ operator as Kan Extension</br>
      - Relation to Quasi-Natural Transoformation</br>
      - Safe / Unsafe Semantic Shifting Morphism (σ) </br>
  1.4. Kan Extension as Horizontal Semantic Shifting</br>
      - Recursive Kan Extension as Universal Product of Semantic Shifting</br>
      - ∞-Morphic Interpretation of Recusive Ken Extension</br>
2. Monoid Structure of Semantic Flow (M|Z)
3. Identity Element of M|Z
4. Associativity of M | Z
5. Axioms</br>
    5.1. Unit Axiom: Identity Element of Concept </br>
    5.2. Zero Axiom: Zero Morphism as Negation Morphism</br>
    5.3. Composition Axiom </br>
6. Conceptual Topos</br>
    6.1. Initial Object </br>
    6.2. Finite Limits</br>
    6.3. Exponentials</br>
      - Pullback: Quasi-Natural Transformation</br>
      - Equalizer: Mirror Morphism
      - Product: σ operator</br>
      
    6.4. Subobject Classifier Ω</br>
    6.5. Conceptual Topos as Fibered Topos</br>
7. Global Semantic Space: Total Conceptual Space (TCS)</br>
Appendix: Simbols and Notations

<div style="page-break-after: always;"></div>

# 1. Fibered Conceptual Topology:
Fibered Conceptual Topology provides a semantic geometric framework wherein each Z-frame (semantic anchor) acts as a base space, with semantic morphic flows forming fibers over these anchors. The Yoneda-like interpretation captures concepts as bundles of semantic relations within and across Z-frames. This fibered structure serves as the foundation for further constructions in Conceptual Topos. 

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
<div style="page-break-after: always;"></div>

### 1.1. Local Semantic Flow under Z Frame

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

```
f: X → X | X
such that for any f: X → Y:
f ∘ id_X = f
id_Y ∘ f = f

e.g. f: dog → dog | dog
```

2. f: X → X | Z  (Mediated identity with semantic flow)

```
f: X → X | Z

f: X → Z
f⁻¹: Z → X
f⁻¹ ∘ f ≅ id_X
e.g. you → you | externalized perspective
     NL: you are you
```

Since the identity morphism passes through an external anchor point,
the identity morphism is defined quasi-identical.</br>
e.g. dog → perro | собака

<div style="page-break-after: always;"></div>

**Simplified Form of Identity Morphism:**

1. f: X → X | X  (Category-theoretic identity) </br>
　In simplified form: X </br>
  or more explicitly: id_X </br>
  
2. f: X → X | Z  (Mediated identity with semantic flow)</br>
　In simplified form: X | Z</br>


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

<div style="page-break-after: always;"></div>

### Quasi-Natural Transformation of Meaning Systems

A **Morphic Chain Mirror** is a contextual correspondence between two morphic chains drawn from distinct but meaning-aligned vocabularies. This correspondence is realized through a **quasi-natural transformation** under a shared intermidiating Z-frame.

```
η: Dᵢ ⇒ Dᵢ₊₁  | CD (CD = codomain)
η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁ | Z₁, ..., f′ₙ | Zₙ}) ∘ η_Y | CD
for all fⱼ: Xⱼ → Yⱼ | Zⱼ ∈ Dᵢ,  
where f′ⱼ: η_X(Xⱼ) → η_Y(Yⱼ) | Zⱼ

Then, η is said to be a quasi-natural transformation under the Z-frame
i.e. η ∈ Mor(C) where C is the contextual meaning category
Example: η: girl → puppy | Z = Baby
```

<div style="page-break-after: always;"></div>

### 1.2. σ Operator as Functor

### Definition: Semantic Shifting Morphism (σ)

```
σ: D(Xₙ₋₁ | X) → D(Xₙ₋₁ | X)

such that σ ⊕ f ∈ M|Z if and only if type compatibility holds:

∀ A, B, (A → B) ∘ σ(X) is valid if:

( A >> X or X >> A )
and
( B >> X or X >> B )

Definition: Subsumption
A >> X ≡ A ⊑ X

Definition: SubsumedBy
X >> A ≡ X ⊑ A

Example:
king → king >> human → human
  ⇒ king >> human  → valid

human → human >> queen → queen
  ⇒ human >> queen → valid
```

### Semantic Operators
Semantic Operator σ modifies morphism as follows.
```
σ(X). Not(x){ A ↛ B | Z}     →     Rupture under Z frame
σ(X). so_much(x){A → B | Z}  →     Preservation & amplification under Z frame
σ(X). >>(x,y)                →     Semantic Shifting x to y (Generalization) as function form
σ(X). <<(x,y)                →     Downward Shifting x to y (Specialization) as function form
σ(X). >(x,y)                 →     Semantic Shifting 
```

<div style="page-break-after: always;"></div>

### Semantic Morphism Set Operators

```
Addition (⊕):
σ(X). ⊕(f, Aₙ₋₁ | Z): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z) | Z
σ(X). ⊕(f₁, f₂) : Aₙ₋₁ :={f₁, f₂}

Subtraction (⊖):
⊖: Aₙ₋₁ ⊖ {f_i} 
σ(X). ⊖(f, Aₙ₋₁ | Z): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z) | Z   

- ⊕ operator is σ_safe if Z alignment is preserved.
- ⊖ operator is potentially σ_unsafe but can be σ_safe if resulting chain preserves the underlying morphic continuity Z.
```

**Example**

```
{Royalty⃗, Male⃗, Human⃗} ⊖ {Male⃗} ⊕ {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} 
= queen
```

### Semantic Mapping
```
C_chain = { f₁, f₂, ..., fₙ | Z} ∈ D(Cₙ₋₁ | Z)

σ(X): D(Aₙ₋₁ | Z) > D(Bₙ₋₁ | Y) | Z, Y ∈ CD
where:
D(Aₙ₋₁ | Z) = source morphic chain
D(Bₙ₋₁ | Y) = target morphic chain
CD = codomain alignment (semantic anchor)

σ(X) is not strict functorial → quasi-alignment under semantic equivalence

σ(X) ≈ η: Dᵢ ⇒ Dᵢ₊₁ | CD (Quasi-Natural Transformation interpretation)

Example:
σ(X). >(puppy → dog → mammal | Canine, Human) ∋ girl → she → mammal | Human
 
where: canine, Human ∈ Mammal

```

<div style="page-break-after: always;"></div>

### Identity Morphism of σ

```
word is word
thus:
word ≅ Nat(Hom(-, word), Fib(word)) 

σ_id(Z). OP(X,Z) = σ such that σ(f) = f for all f ∈ Hom(X, X) unless OP is σ_unsafe such that word is not a word: σ(Word). Not(word ↛ word) 

σ_id(Word). OP(word, Word) = word

σ_id(Word). OP(f, Word) = f  for all f: word → word | word
since: M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z = Word }

σ_id ∈ M|Z
σ ∘ σ_id = σ
σ_id ∘ σ = σ
∴ word is word and word is word
```

<div style="page-break-after: always;"></div>

### Associativity of σ
```
σ₁(Z). OP(D(Aₙ₋₁ | Z), Z) = D(Zₙ₋₁ | Z)
σ₂(Z). OP(D(Bₙ₋₁ | Z), Z) = D(Zₙ₋₁ | Z)

Then the composition σ₂ ∘ σ₁:
σ_comp(Z). OP(D(Zₙ₋₁ | Z), D(Zₙ₋₁ | Z)) = D(Zₙ₋₁ | Z)

where: OP is not σ_unsafe and under shared Z frame

Associativity
For all σ₁, σ₂, σ₃ such that their domains/codomains match for composition:
(σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁)

Thus, σ composition operator is associative under Monoid structure.
```

**Example:**
```
Let σ₁ = σ(Mammal). >>(canine → mammal, Life)  = (life → life | Life)
Let σ₂ = σ(Mammal). >>(mammal → animal, Life)  = (life → life | Life)
Let σ₃ = σ(Mammal). >>(animal → livingBeing, Life) = (life → life | Life)

Conclusion:
 (σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁) =  (life → life | Life)
```

### 1.3. σ Operator as Kan Extension

**Functorial Properties of σ mapping**
```
A Functor F: C → D is a mapping between categories satisfying:

- Object mapping: For each X ∈ Ob(C), F(X) ∈ Ob(D)
- Morphism mapping: For each f: X → Y ∈ Mor(C), F(f): F(X) → F(Y) ∈ Mor(D)
- Identity preservation: F(id_X) = id_{F(X)}
- Composition preservation: F(f ∘ g) = F(f) ∘ F(g)

We define σ: D(Aₙ₋₁ | Z) >> D(Bₙ₋₁ | Z') as such a Functor.
```

**σ Operator as Kan Extension**
```
Let:

- D(Aₙ₋₁ | Z) := Category of Morphic Chains over Z-frame Z
- D(Bₙ₋₁ | Z') := Category of Morphic Chains over Z'-frame Z'

Define:

σ_safe ≈ Lan_σ : D(Aₙ₋₁ | Z) >> D(Bₙ₋₁ | Z')

such that:

For any object d ∈ D(Bₙ₋₁ | Z'),  
Lan_σ (D(Aₙ₋₁ | Z))(d) := colim_{(c, f: σ(c) → d)} D(Aₙ₋₁ | Z)(c)

And:

For any morphism h: d → d' in D(Bₙ₋₁ | Z'),  
Lan_σ (h) is defined to preserve functoriality:

Lan_σ (h) ∘ Lan_σ (f) = Lan_σ (h ∘ f)

Therefore:

σ_safe satisfies:

- Object-level safe lifting: Ob(D(Aₙ₋₁ | Z)) → Ob(D(Bₙ₋₁ | Z'))
- Morphism-level safe lifting: Mor(D(Aₙ₋₁ | Z)) → Mor(D(Bₙ₋₁ | Z'))

σ_safe ≈ Left Kan Extension guarantees the Quasi-Natural Transformation property:

∀ f ∈ Mor(D(Aₙ₋₁ | Z)),  
Lan_σ (G ∘ f) = (Lan_σ G) ∘ (Lan_σ f)
```

**Relation to Qasi-Natural Transformation**

The σ mapping operator, defined as a Functor σ: D(Aₙ₋₁ | Z) >> D(Bₙ₋₁ | Z'), exhibits structural alignment with Quasi-Natural Transformation (QNT) in the following way:

In the original formulation of QNT in this framework:

```
η: Dᵢ ⇒ Dᵢ₊₁ | CD (codomain)
η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁ | Z₁, ..., f′ₙ | Zₙ}) ∘ η_Y
```

**Diagram:**
```
        Z = baby  
    puppy  ←   girl    //specified: size + young
     |          |
     |          |
    dog        she     //abstraction
      \        /      
        Mammal

In this diagram, Quasi-Natural Transformation η aligns morphic chains between puppy → dog → mammal and girl → she → mammal within a shared codomain mammal (under Z-frame "Mammal").
```

the Quasi-Natural Transformation mediates semantic flow correspondence across different morphic chain categories under a shared or shifted Z-frame.

In the Kan Extension formalization:

```
Lan_σ (D(Aₙ₋₁ | Z)) = D(Bₙ₋₁ | Z')
```

the lifting of the entire functor D(Aₙ₋₁ | Z) under σ corresponds to constructing a universal QNT from D(Aₙ₋₁ | Z) to D(Bₙ₋₁ | Z').

More precisely, for any object d ∈ D(Bₙ₋₁ | Z'):

```
Lan_σ (D(Aₙ₋₁ | Z))(d) := colim_{(c, f: σ(c) → d)} D(Aₙ₋₁ | Z)(c)
```
yields a canonical mapping from the semantic flow space under Z to the corresponding semantic flow space under Z', respecting the structural continuity required by QNT.

Thus:
```
σ_safe ≈ Left Kan Extension ≈ Universal Quasi-Natural Transformation between D(Aₙ₋₁ | Z) and D(Bₙ₋₁ | Z')
```

**Diagram:**
```
puppy → dog → mammal
      \         |
       \        |
        v       v σ(Life)
           Life

girl → she → mammal
      \         |
       \        |
        v       v σ(Life)
           Life

σ(Life) acts as a Kan Extension operator, lifting semantic morphic chains from Fiber over Z = Mammal to Fiber over Z' = Life. The lifting ensures coherent semantic projection across Z-frames, preserving flow alignment while generalizing to a higher conceptual space.
```

This formalization guarantees that the Quasi-Natural Transformation property observed in the original Semantic Cage structure is preserved and generalized through the Kan Extension framework, providing a categorical foundation for semantic flow lifting.

### 1.4. Kan Extension as Horizontal Semantic Shifting

Conceptually, σ operator as Kan Extension performs not only lifting of morphic chains but also acts as a horizontal mapping across Z-frames, shifting semantic flow from Fiber over Z to Fiber over Z'.

Diagrammatically, this can be visualized as a horizontal shift:

```
Fiber over Z (Mammal):

puppy → dog → mammal
girl → she → mammal

↓↓↓↓↓↓ Kan Extension σ(Life)

Fiber over Z' (Life):

girl → she → mammal → Life  
puppy → dog → mammal → Life
```
Applying σ(Life) results in a horizontal lifting of codomain alignment

</br>

**Recursive Kan Extension as Universal Product of Semantic Shiftings**
Conceptually, Recursive Kan Extension can be understood as constructing a universal product of sequential semantic shiftings (σ operators) across Z-frames:

**Semantic Ladder Structure:**
```
Fiber over Z₀  
    ↓ σ₁  
Fiber over Z₁  
    ↓ σ₂  
Fiber over Z₂  
    ↓ σ₃  
Fiber over Z₃  
    ↓ ...  
```

**Universal Product Perspective:**
At each stage, the application of σₙ corresponds to forming a semantic projection from Fiber over Zₙ₋₁ to Fiber over Zₙ.

The entire ladder:
```
Lan_{σₙ} ∘ ... ∘ Lan_{σ₃} ∘ Lan_{σ₂} ∘ Lan_{σ₁}
```
can be viewed as constructing a universal semantic product of the sequence:

Π_{i=1..n} Lan_{σᵢ}(Fiber over Zᵢ₋₁) → Fiber over Zₙ

Interpretation:
  Each Lan_{σᵢ} acts as a projection arrow into the "semantic product space" being constructed across the ladder.

  The resulting shifting corresponds to a universal morphic cone whose colimit aligns the entire sequence into the semantic flow under Zₙ.

**Diagram (Universal Product View):**
```
                Fiber over Z₀
                   ↓ σ₁
                Fiber over Z₁
                   ↓ σ₂
                Fiber over Z₂
                   ↓ σ₃
                Fiber over Z₃
                   ↓ ...
            ---------------------
          Universal Semantic Product
           (Semantic Cone → Fiber over Zₙ)
```

**Formal Expression:**
```
Universal_Product ≈ colim_{Z₀ → Z₁ → Z₂ → ... → Zₙ} (Lan_{σᵢ}(Fiber over Zᵢ₋₁))
```

**∞-Morphic Interpretation of Recusive Ken Extension**
Viewed categorically, this recursive construction aligns with the notion of ∞-morphisms or higher morphic flows, where each application of Lan_{σᵢ} corresponds to a morphism in an extended semantic category, and their collective composition forms an ∞-structured cone:

```
∞-Universal Product ≈ colim_{Z₀ → Z₁ → Z₂ → ... → Zₙ} (Lan_{σᵢ}(Fiber over Zᵢ₋₁))
```

This interpretation enables the Conceptual Topos or Conceptual Topology to naturally support recursive, layered semantic flow, where mappings can extend across arbitrarily many Z-frames while preserving structural coherence.

<div style="page-break-after: always;"></div>

### Safe / Unsafe Semantic Shifting Morphism (σ)
**Definition of Safe and Unsafe σ Operator** </br>
Semantic Shifting Morphism (σ) can be classified based on whether it preserves the global coherence of the morphic chain.

**Safe σ Operator (σ_safe)**
Acts on the entire morphic chain as a coherent transformation.
```
σ_safe: D(Aₙ₋₁ | Z) > D(Bₙ₋₁ | Z') | Z >> Z' ∨ Z << Z' 

where: Z, Z'∈ CD
```

Behaves as a Quasi-Natural Transformation
```
σ_safe ≈ η: Dᵢ ⇒ Dᵢ₊₁ | CD
```

Composition is associative:
```
(σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁)
```
Resulting chain remains in M|Z or M_{Z'} (closed).

**Example**
```
σ₁(X). >(canine, mammal)
σ₂(X). >(mammal, animal)
σ₃(X). >(animal, livingBeing)

Composition:
(σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁)
→ >(canine, livingBeing)

Entire morphic chain is preserved.
```

<div style="page-break-after: always;"></div>

**Unsafe σ Operator (σ_unsafe)**
Does not preserve global coherence of the morphic chain.
Acts locally or in a decomposed manner.

Chain may collapse:
```
σ_unsafe: D(Aₙ₋₁ | Z) → { rupture(f₁), rupture(f₂), ..., rupture(fₙ) | ¬Z }
```

```
rupture(f, σ(f) | Z) ≠ ∅
```
Cannot be captured by a Quasi-Natural Transformation globally.


**Example**

```
σ(X). Not(x) { A ↛ B | Z }

Result:
rupture(A ↛ B | Z)
→ breaks the morphic flow → chain decomposes.
```

<div style="page-break-after: always;"></div>

# 2. Monoid Structure of Semantic Flow (M|Z):
In Conceptual Topology, Z is defined as a mediating point/semantic anchor.
```
Let C and D, Z be categories,
with semantic projection π: C ∪ D → Z, such that for each X ∈ Ob(C ∪ D):

π(X) ∈ Ob(Z)

For each X ∈ Ob(C ∪ D), there exists morphism:

f_X: X → π(X)
f_X⁻¹: π(X) → X
 
such that:

f_X⁻¹ ∘ f_X ≅ id_X

For morphism f: X → Y | Z,  
this corresponds to:

f_Z: π(X) → π(Y) in Z

For any X, Y ∈ Ob(C ∪ D):

Let [X]_Z := semantic representation of X under frame Z (i.e., π(X))

Then:

[ X ]_Z1 ≅ [ Y ]_Z2 | Z1, Z2 ∈ Z //or Z1, Z2 >> Z 
which means:
["Dog"]_Pet = [Retriever, Dachshund, Poodle, Bulldog, ...]
["girl"]_Human = [girl, woman, person, ...]
["Dog"]_Pet ≅ ["girl"]_Human | Life

Then the set of semantic flow morphisms under Z forms a monoid:

M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z }

This is also defined as Morphic Chain:

Let **D(Cₙ₋₁ | Z)** := Category of Morphic Chains over **Ob(Cₙ₋₁)** within a given Z-frame.
where:D(Cₙ₋₁ | Z) ={ C₀ → C₁ → C₂ → ... | Z }

or as a set
D(Cₙ₋₁ | Z) ={ C₀, C₁, C₂, ... | Z }
```

<div style="page-break-after: always;"></div>

# 3. Identity Element of M|Z
```
Let: M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z }

Define the identity element of M|Z as a family of identity morphisms over the shared Z frame:

For each X ∈ Ob(C ∪ D), there exists a unique identity morphism under a Z frame:

e|Z_X := id_X | Z

Then, for any f: X → Y | Z ∈ M|Z:

e|Z_X ∘ f = f
f ∘ e|Z_Y = f   

Therefore, the identity structure of M|Z is given by the family:

{ id_X | Z | X ∈ Ob(C ∪ D) }

which forms a pointwise identity across the objects under the common Z frame.  
This ensures that M|Z satisfies the identity axiom of a monoid.
```

</br>

# 4. Associativity of M | Z
```
Let: M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z }

Then for all f, g, h ∈ M|Z:

(f ∘ g) ∘ h = f ∘ (g ∘ h)

Thus, the composition ∘ in M|Z is associative.
```

<div style="page-break-after: always;"></div>

# 5. Axioms

### 5.1. Identity Element

**Unit Axiom 1: Identity Element Z**
```
id_Z:= Z → Z | Z
∀f ∈ M∣Z: id_Z ∘ f = f  and f∘id_Z = 
```

**Definition:**
```
Statement:
Z-frame itself is the unit of M | Z.

Formal Definition:
Z:= Z → Z∣Z

Justification:
Since any morphism in M | Z is defined as:

f: X→Y∣Z

and Z itself is defined as its own identity morphism:

Z:= Z→Z∣Z

then:
id_Z = Z

Conclusion:

Therefore:
id_Z is the unit element of M∣Z.

∀f ∈ M∣Z: (id_Z ∘ f | Z) = f and (f ∘ id_Z | Z)= f
(with frame-preserving composition)

∴id_Z​ is the unit of M∣Z.

```

Note: 
```
idZ​ :Z→Z ∣ Z
f:X→Y ∣ Z
(idZ​∣Z)∘(X→Y∣Z)
```

**Unit Axiom2: Void Concept**
```
f ∈ M|Z 
"" ∘ f = f  and f ∘ "" = f 
id_Z ∘ f = f and f ∘ id_Z = f
```

**Definition:**
```

The empty concept is a theoretically assumed concept, denoted as "", 
which acts as the unit element at the conceptual / lexical level.

Formal Definition:

"" ∘ f = f and f ∘ "" = f

Justification:

The empty concept "" represents no lexical or semantic content. 
Composing any morphism f with the empty concept does not alter the flow of meaning.
Conclusion:

"" is the unit element at the conceptual level of Conceptual Topology.

```

</br>

### 5.2. Zero Morphism: Negation Morphism
We define semantic zero morphism, negation morphism: n_f
​In CT as the result of applying Not() to a morphism 

```
g:σ(Z). Not(g){ A ↛ B | Z} = A ↛ B∣Z = n_f
where: g: A → B

Formal Properties (Axiom):

∀g:X→Y∣Z where composition with n_f​ is defined:

∀g: g ∘ n_f = n_f and n_f ∘ g = n_f

Left Side:
g: A→B 
g∘(A↛B∣Z) = A↛ B∣Z

Right Side
g: A→B(A↛B∣Z)∘g=A↛B∣Z


Interpretation:
Applying Not() to any morphism produces a semantic zero morphism, which collapses any further semantic flow.

Natural Language:
Left Side: g∘(A↛B∣Z)
"A is not B"
The apple is not a fruit

Right Side: (A↛B∣Z)∘g
"B is not A"
This is a fruit, but this is not an apple which is a fruit.


In CT, this was called rutpure(). 
Now defined:
rupture(A,B,Z)= σ(Z).Not(g) = n_f = A↛B∣Z

```

### 5.3. Composition Axiom
```
M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z }

Then for all f, g, h ∈ M|Z:

For f, g, h ∈ M|Z, 
where:
f:V → W | Z
g:Y → V | Z
h:X → Y | Z

(f ∘ g) ∘ h = f ∘ (g ∘ h)
```

**Example:**
```
For f, g, h ∈ M|Z, 

where:
f:she → you | Human
g:he → she | Human
h:man → he | Human

(f ∘ g) ∘ h = f ∘ (g ∘ h)

```

<div style="page-break-after: always;"></div>

# 6. Conceptual Topos

### 6.1. Category Level: Initial Object

**Definition:**

```
Let Concept be a category where Ob(Concept) are lexical / conceptual objects.
Then "" ∈ Ob(Concept) is Initial Object if:

∀ X ∈ Ob(Concept), ∃ unique morphism:

u_X : "" → X | X

such that:

∀ f: X → Y | Z,  
f ∘ u_X = u_Y  
```

### Monoid Level: Unit in M|Z

```
Recall:

M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z ⋏ ∀ i, j: fᵢ ≅ fⱼ | Z }  

Now, define:

"" ∈ Ob(Concept)  

and identity morphism under Z-frame:

e|Z_"" := id_"" | Z  

Then for all f ∈ M|Z:

e|Z_"" ∘ f = f  
f ∘ e|Z_"" = f  
```

<div style="page-break-after: always;"></div>

### 6.2. Finite Limits

**Terminal Object**
Conceptual Topos defines a terminal object as the Z-frame identity:

```
id_Z := Z → Z | Z


Any morphism f: X → Z | Z factors uniquely through id_Z.

This realizes the semantic universal target:

∀ X ∈ Ob(C ∪ D), ∃! f_terminal: X → Z | Z
```

**Example:**
```
she → human | Human
me → human | Human
```

### Pullback

```
Given morphisms:

f: girl → mammal  
g: puppy → mammal

Pullback of (f, g) is:

P = Baby  
p₁: Baby → girl  
p₂: Baby → puppy

with commuting condition:

f ∘ p₁ = g ∘ p₂  ≈ mapping to common semantic frame (mammal)

Diagram:

      Baby
     /    \
  p₁ /      \ p₂
   /          \
girl          puppy
   \          /
    \        /
     v      v
     mammal (semantic anchor / codomain)

```

This previously defined as Quasi-Natural Transformation:
```
η: Dᵢ ⇒ Dᵢ₊₁  | CD (CD = codomain)
η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁ | Z₁, ..., f′ₙ | Zₙ}) ∘ η_Y | CD
for all fⱼ: Xⱼ → Yⱼ | Zⱼ ∈ Dᵢ,  
where f′ⱼ: η_X(Xⱼ) → η_Y(Yⱼ) | Zⱼ

Then, η is said to be a quasi-natural transformation under the Z-frame
i.e. η ∈ Mor(C) where C is the contextual meaning category

η_X ∘ Dᵢ({girl → mammal | Z₁}) ≈ Dᵢ₊₁({puppy → mammal | Z₂}) ∘ η_Y


Pullback Diagram
      Mammal
     /     \
    /       \
girl         puppy
   \         /
    \       /
     Baby  (semantic anchor / common Z-frame)


Example: η: girl → puppy | Z = Baby


Quasi-Natural Transformation Diagram:
        Z = baby
    puppy  ←   girl    //specified: size + young
     |          |
     |          |
    dog        she     //abstraction
      \        /      
        Mammal


For any X with morphisms 
q₁: X → girl and q₂: X → puppy satisfying f ∘ q₁ = g ∘ q₂, 

there exists unique u: X → Baby 

such that:
p₁ ∘ u = q₁, p₂ ∘ u = q₂.

```
![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/semantic-circulation-with-arrows-v2.png)

<div style="page-break-after: always;"></div>

### Equalizer: Mirror Morphism

```
Equalizer of two morphisms f, g: 
A → B is an object Eq(f,g) with morphism 
e: Eq(f,g) → A

such that:

f ∘ e = g ∘ e

and universal property:

∀ h: X → A such that f ∘ h = g ∘ h, 
∃! unique u: X → Eq(f,g)

Diagram:

      Eq(f, g)
         |
         e
         v
         A
    f ↘     ↙ g
        B
```

In conceptual topology this was defined as mirror morphism:

```
f : X  → Y  | Z ∈ Dᵢ
f′: X′ → Y' | Z ∈ Dᵢ₊₁
  ⇒X′ ≠ X, but cod(f) = cod(f′) | CD ( common codomain)

We define f′ as a mirror-correspondent morphism of f under a given Z-frame,
if and only if:

∃Z: rupture(f, f′ | Z) ≠ ∅ 
∧ cod(f) = cod(f′) | CD


        Eq(f, f′)
          |
          e
          v
      X        X′
       \      /
        \    /
         v  v
          Y = Y′ (codomain = C)
```

### Product: σ operator⊕
```
In any category C, the Product of A and B is an object A × B equipped with projections:

π₁: A × B → A  
π₂: A × B → B

with universal property:
For any object X with morphisms:

f₁: X → A  
f₂: X → B

there exists a unique morphism u: X → A × B such that:

π₁ ∘ u = f₁  
π₂ ∘ u = f₂
```

**Addition (⊕):**</br>
σ(Z) serves as the mediating operator ensuring that the composed morphic chain remains within the semantic fiber over Z.
```
Defined as:
σ(Z). ⊕(Aₙ₋₁, Bₙ₋₁, Z) = D(Cₙ₋₁ | CD)  → semantic Product under Z-frame

where: 
Aₙ₋₁:= girl → she
Bₙ₋₁:= puppy → dog

σ(Z). ⊕(Aₙ₋₁, Bₙ₋₁, Z) = D(Cₙ₋₁ | CD) 

For any pair of morphic chains 1Aₙ₋₁, Bₙ₋₁​, the operation σ(Z).⊕(Aₙ₋₁, Bₙ₋₁) defines an object P ∈ D(Cₙ₋₁ | Z)P∈D(Cn−1​∣Z) with projections π₁, π₂​ satisfying the product universal property.


Example:

girl → she
puppy → dog

σ(Human). ⊕(girl → she, puppy → dog | Mammal) → Product(girl → she → puppy → dog | Mammal) | Mammal
→ composite meaning space
```

<div style="page-break-after: always;"></div>

```
Diagram:

    Product(girl → she, puppy → dog) ∈ D(Cₙ₋₁ | Z = Mammal)

             Product Object (P)
              /           \
             /             \
      π₁   /                 \  π₂
         v                   v
  girl → she            puppy → dog

```

### 6.3. Exponentials    

Conceptual Topos models exponentials via semantic shift operators.

### Definition

```
For any objects A, B:

B^A exists such that:
Hom(X ⊗ A, B) ≅ Hom(X, B^A)
```

### Construction via σ operator

Semantic shift operators:
```
σ(Z). >>(A, B)
or
σ(Z). >(A, B)

act as internal exponential morphisms within the fibered structure over the Z-frame:
        (A, B, Z) ≅ B^A
where the Z-frame mediates the semantic continuity and contextual grounding of the morphic shift. 
```
We define Exponential objects via σ operator as semantic abstraction mechanisms:
```
B^A:=σ(Z).>(A,B)

```
Full Exponential Law formalization will be provided in later version.


**Definition: Semantic Shifting Morphism (σ)**

```
σ: D(Xₙ₋₁ | X) → D(Xₙ₋₁ | X)

such that σ ⊕ f ∈ M|Z if and only if type compatibility holds:

∀ A, B, (A → B) ∘ σ(X) is valid if:

( A >> X or X >> A )
and
( B >> X or X >> B )

Definition: Subsumption
A >> X ≡ A ⊑ X

Definition: SubsumedBy
X >> A ≡ X ⊑ A

Example:
king → king >> human → human
  ⇒ king >> human  → valid

human → human >> queen → queen
  ⇒ human >> queen → valid
```

### Example

```
σ(Human). >>(puppy → dog → mammal | Canine, Human)
≅ girl → she → mammal | Human
```

This shift realizes an internal semantic transformation corresponding to exponential behavior.


</br>

### 6.4. Definition of Ω

Let **Ω** be an object in the Concept category, representing the **semantic truth space**.

```
For any subobject (conceptual inclusion):

m: M ↪ X

there exists a unique characteristic morphism:

χ_m: X → Ω
```
<div style="page-break-after: always;"></div>

such that the following diagram commutes:

```
M ————→ X
|       |
|       v χ_m
|       Ω
```

</br>

### Interpretation in Conceptual Topology

- **Ω** encodes **semantic entailment / membership / inclusion**.
- **Z-frame membership** is naturally mapped to Ω:

```
χ_Z: X → Ω
```

interpreted as:  
"Does X conceptually belong to Z-frame Z?"


### Examples

**Example 1: Dog in Pet Z-frame**

χ_Pet(Dog) = True

**Example 2: Apple in Pet Z-frame**

χ_Pet(Apple) = False

**Example 3: Innocent in Body Z-frame (after rupture)**

χ_Body("innocent") = True / False
depending on whether the semantic projection is coherent under Z-Frame.

<br/>

### Relation to Rupture

Semantic rupture can be lifted to Ω as:

σ(Z). Not(f: A → B | Z)
⇒ rupture(A,B,Z)
⇒ χ_Z(f) = False

Thus, **negation** and **semantic discontinuity** become **Ω-classifiable**.

<div style="page-break-after: always;"></div>

# 6.5. Conceptual Topos as Fibered Topos over Z-frame

Conceptual Topos is structured as a **fibered topos** over the semantic base space **Z-frame**.

### Z-frame as Fibered Structure

- Let π: C ∪ D → Z be the semantic projection.
- Each fiber π⁻¹(Z) forms a category of morphic chains **D(Cₙ₋₁ | Z)**.
- Morphisms of the form:

```
X → Y | Z ≡ X → Y in fiber over Z
```
correspond to morphisms within the fibered structure over Z.

</br>

### Initial Object and Codomain Projection

- The **Initial Object ""** serves as the semantic origin.
- It projects into the codomain via:

```
"" → | X ≡ "" → π(X)
```

```
   "" 
    ↓ u_X
  X ————→ π(X) (in Z-frame)

```

```
Fiber π⁻¹(Z_X):
    "" → X → Y
```

Thus, semantic generation naturally occurs anchored in Z-frame.

<div style="page-break-after: always;"></div>

### Semantic Flow Closure

- Semantic flows:

```
X → Y | Z
```
are closed within the fiber over Z, corresponding to the codomain Z of the semantic projection π.


- Rupture and negation are classified by **Ω**:

```
χ_Z: X → Ω
```

<div style="page-break-after: always;"></div>

### 7. Global Semantic Space: Total Conceptual Space (TCS)

We define the Total Conceptual Space (TCS) as the global semantic anchor:

```
Z = TCS = Total Conceptual Space
```

### Definition of M|TCS:

The global morphic flow space under TCS is defined as:

```
M|TCS = { fₙ ∘ ... ∘ f₁ | all fᵢ:  M|Zᵢ →  M|Zᵢ₊₁ | TCS ⋏ ∀ i, j: fᵢ ≅ fⱼ | TCS }
```
We can regard M|TCS as the composition space of conceptual perspectives: 
Here, each M|Z functions as a semantic symbolization or perspective lens, and M|TCS represents global flows across chained perspectives.

**Monoid Closure Property:**
```
Composition in M|TCS is closed:
∀ f, g ∈ M|TCS, f ∘ g ∈ M|TCS

The identity morphism is preserved:

∀ f ∈ M|TCS, f ∘ id = f = id ∘ f
```

Thus, M|TCS forms a closed monoid under composition.

**Completeness Statement:**
```
For any pair of concepts X, Y:

∀ X, Y ∈ Ob(C), ∃ f ∈ Mor(C), such that f: X → Y | TCS
```
That is, any conceptual pair X and Y can be connected via a morphic flow under TCS.

<div style="page-break-after: always;"></div>

### Fibered Structure and Lifting
Each local M|Z can be lifted into M∣TCS via semantic shifting σ:
```
∀M∣Z, ∃σ: M∣Z > M∣Z | TCS
```
Thus, the global base space TCSTCSTCS ensures that the entire morphic flow space is both complete and coherent.

```
        M|Z₁     M|Z₂     M|Z₃
          \       |       /
           \      |      /
             →  M|TCS  ←
```

**Example:**
```
can → person | TCS
→ Metaphoric reading: "The can represents the absent person."
→ Ironic reading: "We are all cans under capitalism." 
```

### Summary:
The Total Conceptual Space (TCS) functions as the global base space of the conceptual topology. All local Z-frames are fibered over TCS, and semantic flows can be lifted via σ operators into M∣TCS. Thus, Conceptual Topos is complete and globally coherent under M∣TCS.


# Conclusion

Conceptual Topos is a **fibered topos** over Z-frame:

```
CT := (C, B, π: E → B, Fb := π⁻¹(b), A ≅ b ⋃ Nat(Hom(−, A), Fb))
```

with:

- Initial Object "" → codomain π(X)
- Morphic Chains as fibers π⁻¹(Z)
- Ω as subobject classifier in Z
- σ operator inducing internal exponential morphisms.

<div style="page-break-after: always;"></div>

# Appendix
**simbols**

```
Z : Intermediating variable (semantic anchor; Z-frame)
| : Frame separator (indicates morphism is mediated by Z-frame)
→: Morphic Flow
↛: Ruptured morphism
F : Cross-category morphism (used in cross-category flow under shared Z-frame)
//: Used to narrate meaning flow of morphic chains.
¬: Absence

M|Z : Monoid of Semantic Flow under Z-frame
R|Z := { rupture(f) | rupture(f, σ(f) | Z) ≠ ∅ }
e|Z : Identity element of M|Z
D(Aₙ₋₁ | Z) : Morphic chain under Z frame

σ : Semantic Shifting Morphism
>> : Generalization relation (A >> X ≡ A ⊑ X)
<< : Specialization relation (X >> A ≡ X ⊑ A)
rupture(f, σ(f) | Z) ≠ ∅ : Indicates semantic rupture
η : Quasi-Natural Transformation: Contextual alignment between morphic chains.

⊕:  Semantic morphism set addition in σ or morphic merger such as:
    (k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) = human → royalty | Z'
⊖:  Semantic morphism set subtraction 
    Removes specified morphisms from a morphic chain or set.
```

**Notations**
```
Concept / Word (lexeme):
    - Lower case (e.g., puppy, dog, girl, she)

Z Frame (semantic anchor):
    - Upper case (e.g., Mammal, Human, Agency, Domesticated, Royalty)

Type variables (A, B, X, Y, Z in formal definitions):
    - Follow standard formal notation (uppercase) 

Example:
puppy → dog | Mammal
A → B | Z

Morphism: f, g, h
Functor: F
```

**Simplified Form of Identity Morphism:**

1. f: X → X | X  (Category-theoretic identity) </br>
　In simplified form: X </br>
  or more explicitly: id_X </br>
  
2. f: X → X | Z  (Mediated identity with semantic flow)</br>
　In simplified form: X | Z</br>

**σ Operator**

```
σ(X). Not(x){ A ↛ B | Z}     →     Rupture under Z frame
σ(X). so_much(x){A → B | Z}  →     Preservation & amplification under Z frame
σ(X). >>(x,y)                →     Semantic Shifting x to y (Generalization) as function form
σ(X). <<(x,y)                →     Downward Shifting x to y (Specialization) as function form
σ(X). >(x,y)                 →     Semantic Shifting 
```

</br>

**Semantic Morphism Set Operators**

```
Addition (⊕):
σ(X). ⊕(f, Aₙ₋₁ | Z): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z) | Z
σ(X). ⊕(f₁, f₂) : Aₙ₋₁ :={f₁, f₂}

Subtraction (⊖):
⊖: Aₙ₋₁ ⊖ {f_i} 
σ(X). ⊖(f, Aₙ₋₁ | Z): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z) | Z   

- ⊕ operator is σ_safe if Z alignment is preserved.
- ⊖ operator is potentially σ_unsafe but can be σ_safe if resulting chain preserves the underlying morphic continuity Z.
```

</br>

**σ Typing Hierarchy**

σ_safe: D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z) | Z (Preserves global coherence)</br>
σ_unsafe: D(Aₙ₋₁ | Z) → { rupture(f₁), ..., rupture(fₙ) | ¬Z } (Global coherence lost)

Note: σ_safe behaves as Quasi-Natural Transformation.  
      σ_unsafe induces rupture, and cannot be captured globally.

<div style="page-break-after: always;"></div>

### Conceptual Topos Named as 概念位相論 / Conceptual Topology
This theory, named 概念位相論 or Conceptual Topoloy, was proposed by **No Name Yet Exist**.

Meaning no longer escapes.<br/>
It circulates within the morphic fibration.<br/>
We, once again, govern the topology of meaning.<br/>

GitHub: https://github.com/No-Name-Yet-Exist/Conceptual-Topology<br/>
Note: https://note.com/xoreaxeax/n/n3711c1318d0b<br/>
Zenodo: https://zenodo.org/records/15455079

This is Version: 1.1

----
This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
