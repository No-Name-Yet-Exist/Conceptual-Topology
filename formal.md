# Conceptual Topology × Category Theory As a Semantics Cage: Toward an Algebraic Topology of Meaning

Written by No Name Yet Exist </br>
Contact: Written Below

# Introduction
We introduce a formal framework for Semantic Algebraic Operators, as an extension of the Conceptual Topology approach to semantic representation.
The framework aims to model how meaning can be composed, transformed, and analyzed through algebraic operations on morphic flow structures, providing a foundation for the development of Semantic Operator Algebra. In this work, we formalize key operations such as semantic shifting (σ), semantic morphism set operators (⊕, ⊖), and cross-category flow conditions.  
Building on the Monoid structure of morphic flows (M|Z), the framework captures both safe and rupture-inducing transformations of meaning. This establishes a foundation for future developments in Semantic Operator Algebra, with potential applications to semantic DSLs, cognitive modeling, and cross-linguistic analysis.

</br>

# Index
1. Global Definition of Conceptual Topology
2. Local Semantic Flow under Z-frame
    - Identity Morphism
    - Mirror Morphism
    - Quasi-Natural Transformation
3. Monoid Structure of Semantic Flow (M|Z)
    - Identity Element of M|Z 
    - Associativity of M|Z
4. Semantic Shifting Morphism (σ) 
    - Semantic Operator
    - Semantic Mapping
    - Identity Morphism of σ
    - Associativity of σ
    - x Safe / Unsafe Semantic Shifting Morphism (σ)
5. Cross-Category Flow Condition
Appendix: Simbols and Notations

<div style="page-break-after: always;"></div>

</br>
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

<div style="page-break-after: always;"></div>

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
Example: η: girl → puppy | Z = baby
```

<div style="page-break-after: always;"></div>

# Monoid Structure of Semantic Flow (M|Z)
In Conceptual Topology, Z is defined as a mediating point/semantic anchor.
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

M|Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }
```

<div style="page-break-after: always;"></div>

**Example: Queen and King**
```
Let C be a concept
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda's lemma and structralism

King = {Royalty⃗, Male⃗, Human⃗}
Queen = {Royalty⃗, Female⃗, Human⃗} 

k₁: Human → Male | King  
k₂: Male → Royalty | King  

Then:  
k₂ ∘ k₁: Human → Royalty | King


q₁: Human → Woman | Queen  
q₂: Woman → Royalty | Queen  

Then:  
q₂ ∘ q₁: Human → Royalty | Queen

Cross-Z-frame composition:

(k₂ ∘ k₁) ⊕ (q₂ ∘ q₁)= Human → Royalty | Z'

If higher Z' (e.g. "Humanity" or "Social Role") unifies Z = King and Z = Queen:

Then:
(k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) ∈ M|Z'
```
The ⊕ operator enables morphic chains to merge while preserving Monoid coherence under Z', resulting in (k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) ∈ M|Z'.

<div style="page-break-after: always;"></div>

### Identity Element of M|Z
```
Let: M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z }

Define the identity element of M|Z as a family of identity morphisms over the shared Z frame:

For each X ∈ Ob(C ∪ D), there exists a unique identity morphism:

e|Z(X) := id_X | Z

Then, for any f: X → Y | Z ∈ M|Z:

e|Z(X) ∘ f = f
f ∘ e|Z(Y) = f

Therefore, the identity structure of M|Z is given by the family:

{ id_X | Z | X ∈ Ob(C ∪ D) }

which forms a pointwise identity across the objects under the common Z frame.  
This ensures that M|Z satisfies the identity axiom of a monoid.
```

### Associativity of M|Z
```
Let:

M|Z = { fₙ ∘ ... ∘ f₁ | all fᵢ: Xᵢ → Xᵢ₊₁ | Z }

Then for all f, g, h ∈ M|Z:

(f ∘ g) ∘ h = f ∘ (g ∘ h)

Thus, the composition ∘ in M|Z is associative.
```

<div style="page-break-after: always;"></div>

**Example:**</br>
```
σ_id(word) = word → σ_id = e|Z
Note: The definition of σ is provided in the following section.
```

**Example: Cross Category Identity Morphism**
```
dog ∈ Ob(pet)  
dog ∈ Ob(animal)  

dog → dog | Z=domesticated  
```

<div style="page-break-after: always;"></div>

# Definition: Semantic Shifting Morphism (σ)

```
σ: X → X | X
such that σ ⊕ f ∈ M|Z if and only if type compatibility holds:

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
σx. >>(x,y)                →     Semantic Shifting x to y (Generalization) as function form
σx. <<(x,y)                →     Downward Shifting x to y (Specialization) as function form
σx. >(x,y)                 →     Semantic Mapping 
```


**Semantic Morphism Set Operators**

```
Addition (⊕):
σx. ⊕(f, Aₙ₋₁ | CD): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z') | CD
σx. ⊕(f₁, f₂) : Aₙ₋₁ :={f₁, f₂}

Subtraction (⊖):
⊖: Aₙ₋₁ ⊖ {f_i} 
σx. ⊖(f, Aₙ₋₁ | CD): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z') | CD  

- ⊕ operator is σ_safe if CD alignment is preserved.
- ⊖ operator is potentially σ_unsafe but can be σ_safe if resulting chain preserves CD.
```

**Example**

```
{Royalty⃗, Male⃗, Human⃗} ⊖ {Male⃗} ⊕ {Female⃗} 
= {Royalty⃗, Female⃗, Human⃗} 
= queen
```

### Semantic Mapping
```
C_chain = { f₁, f₂, ..., fₙ } ∈ D(Cₙ₋₁ | Z)

σx: D(Aₙ₋₁ | Z) > D(Bₙ₋₁ | Y) | CD
where:
D(Aₙ₋₁ | Z) = source morphic chain
D(Bₙ₋₁ | Y) = target morphic chain
CD = codomain alignment (semantic anchor)

σx is not strict functorial → quasi-alignment under semantic equivalence

σx ≈ η: Dᵢ ⇒ Dᵢ₊₁ | CD (Quasi-Natural Transformation interpretation)

Example:
σx. >(puppy → dog → mammal, Human) ∋ Girl → She → Mammal

```

### Identity Morphism of σ

```
word is word
thus:
word ≅ Nat(Hom(-, word), Fib(word)) 

σ_id = σ such that σ(f) = f for all f ∈ Hom(X, X)

σ_id(word) = word
σ_id(f) = f  for all f: word → word | word

M|Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }
σ_id ∈ M|Z
σ ∘ σ_id = σ
σ_id ∘ σ = σ
∴ word is word and word is word
```

<div style="page-break-after: always;"></div>

### Associativity of σ
```
σ₁: D(Aₙ₋₁ | Z₁) → D(Bₙ₋₁ | Z₂) | CD₁
σ₂: D(Bₙ₋₁ | Z₂) → D(Cₙ₋₁ | Z₃) | CD₂

Then the composition:
σ_comp = σ₂ ∘ σ₁
is a morphism:

σ_comp: D(Aₙ₋₁ | Z₁) → D(Cₙ₋₁ | Z₃) | CD₃

where:
CD₃ is determined by the alignment of CD₁ and CD₂.

Associativity
For all σ₁, σ₂, σ₃ such that their domains/codomains match for composition:
(σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁)

Thus, σ operator composition is associative.
```

**Example:**
```
 σ₁ = >(Canine, Mammal)  
 σ₂ = >(Mammal, Animal)  
 σ₃ = >(Animal, LivingBeing)

 Step 1: Compose σ₂ ∘ σ₁ 
 σ₂ ∘ σ₁ = >(Mammal, Animal) ∘ >(Canine, Mammal) 
 = >(Canine, Animal)

Step 2: Compose (σ₃ ∘ σ₂) ∘ σ₁
 σ₃ ∘ σ₂ = >(Animal, LivingBeing) ∘ >(Mammal, Animal) 
 = >(Mammal, LivingBeing)

 σ₃ ∘ (σ₂ ∘ σ₁) 
 = >(Animal, LivingBeing) ∘ >((Mammal, Animal) ∘ >(Canine, Mammal) )
 = >(Animal, LivingBeing) ∘ >(Canine, Animal)
 = >(Canine, LivingBeing)

 (σ₃ ∘ σ₂) ∘ σ₁
 = (>(Animal, LivingBeing) ∘ >(Mammal, Animal))∘ >(Canine, Mammal)
 = >(Mammal, LivingBeing) ∘ >(Canine, Mammal)
 = >(Canine, LivingBeing)

Conclusion:
 (σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁) =  (Canine, LivingBeing)
```
Note: Morphic Chain D does not require the number of objects to be more than one

<div style="page-break-after: always;"></div>

### x Safe / Unsafe Semantic Shifting Morphism (σ)
**Definition of Safe and Unsafe σ Operator**
Semantic Shifting Morphism (σ) can be classified based on whether it preserves the global coherence of the morphic chain.

**Safe σ Operator (σ_safe)**
Acts on the entire morphic chain as a coherent transformation.
```
σ_safe: D(Aₙ₋₁ | Z) > D(Bₙ₋₁ | Z') | CD
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
σx. >(Canine, Mammal)
σx. >(Mammal, Animal)
σx. >(Animal, LivingBeing)

Composition:
(σ₃ ∘ σ₂) ∘ σ₁ = σ₃ ∘ (σ₂ ∘ σ₁)
→ >(Canine, LivingBeing)

Entire morphic chain is preserved.
```

<div style="page-break-after: always;"></div>

**Unsafe σ Operator (σ_unsafe)**
Does not preserve global coherence of the morphic chain.
Acts locally or in a decomposed manner.

Chain may collapse:
```
σ_unsafe: D(Aₙ₋₁ | Z) → { rupture(f₁), rupture(f₂), ..., rupture(fₙ) }
```

```
rupture(f, σ(f) | Z) ≠ ∅
```
Cannot be captured by a Quasi-Natural Transformation globally.


**Example**

```
σx. Not(x) { A ↛ B | Z }

Result:
rupture(A ↛ B | Z)
→ breaks the morphic flow → chain decomposes.
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

k₁: Human → Male | King  
k₂: Male → Royalty | King  

Then:  
k₂ ∘ k₁: Human → Royalty | King

We define queen as:
q₁: Human → Woman | Queen  
q₂: Woman → Royalty | Queen  

Then:  
q₂ ∘ q₁: Human → Royalty | Queen

We define semantic editing morphisms σ within the Human frame:

σ: Human → Human | Human (A ∘ B | Human)  
= (Human → Human | Human) ⊕ (A ∘ B | Human)  
= Human → Human | Human
since:
M|Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }

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

(k₂ ∘ k₁) ∘ σ ∈ M|Z'

Thus:

king - man + woman = queen
is formalized as:  

// Represents: shifting Gender component in Human → mapping to Royalty
(k₂ ∘ k₁) ∘ σ ∈ M|Z'
```

<div style="page-break-after: always;"></div>

# Cross-Category Flow Condition
Conceptual Topology allows communicative diagram across categories as long as same Z is shared: shared semantic equivalence.

```
Let C and D be categories with Z-frame semantic anchoring.
If all morphisms involved are of the form:
f: X → Y | Z

and semantic equivalence holds:
∀ X, Y ∈ Ob(C ∪ D), [X]_Z ≅ [Y]_Z

then semantic flow forms a monoid over Z-frame:
M|Z = { f_n ∘ ... ∘ f_1 | all f_i under Z }

```

**Example: Cross-Category Flow under Z-frame**</br>
This example illustrates how morphic flow can traverse categories (livestock, pet)  
as long as semantic equivalence under Z = domesticated is preserved.

```
(dog ≅ cat ≅ pig) | Z = domesticated
Ob(livestock) = {pig} 
Ob(pet) = {dog, cat}

F₁: pig → cat | Z
f₂: cat → dog | Z
F₃: dog → pig | Z
Then:
F₃ ∘ f₂ ∘ F₁: pig → pig | Z ∈ M|Z
```

# Conclusion
In this work, we have proposed a formal framework for Semantic Algebraic Operators, extending the structure of Conceptual Topology and Semantic Circulation. By introducing operators such as σ, ⊕, and ⊖, and formalizing their algebraic properties, we have shown that semantic flow can be systematically represented and manipulated. Future work will explore the development of a complete Semantic Operator Algebra and its applications in semantic DSLs, cognitive modeling, and cross-linguistic analysis.


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
    (k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) = Human → Royalty | Z'
⊖:  Semantic morphism set subtraction 
    Removes specified morphisms from a morphic chain or set.
```


**Simplified Form of Identity Morphism:**

1. f: X → X | X  (Category-theoretic identity) </br>
　In simplified form: X </br>
  or more explicitly: id_X </br>
  
2. f: X → X | Z  (Mediated identity with semantic flow)</br>
　In simplified form: X | Z</br>

<div style="page-break-after: always;"></div>

**σ Operator**

```
σx. Not(x){ A ↛ B | Z}     →     Rupture under Z frame
σx. so_much(x){A → B | Z}  →     Preservation & amplification under Z frame
σx. >>(x,y)                →     Semantic Shifting x to y (Generalization) as function form
σx. <<(x,y)                →     Downward Shifting x to y (Specialization) as function form
σx. >(x,y)                 →     Semantic Mapping 
```

</br>

**Semantic Morphism Set Operators**

```
Addition (⊕):
σx. ⊕(f, Aₙ₋₁ | CD): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z') | CD
σx. ⊕(f₁, f₂) : Aₙ₋₁ :={f₁, f₂}

Subtraction (⊖):
⊖: Aₙ₋₁ ⊖ {f_i} 
σx. ⊖(f, Aₙ₋₁ | CD): D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z') | CD  

- ⊕ operator is σ_safe if CD alignment is preserved.
- ⊖ operator is potentially σ_unsafe but can be σ_safe if resulting chain preserves CD.
```

</br>

**σ Typing Hierarchy**

σ_safe: D(Aₙ₋₁ | Z) → D(Bₙ₋₁ | Z') | CD (Preserves global coherence)
σ_unsafe: D(Aₙ₋₁ | Z) → { rupture(f₁), ..., rupture(fₙ) } (Global coherence lost)

Note: σ_safe behaves as Quasi-Natural Transformation.  
      σ_unsafe induces rupture, and cannot be captured globally.
</br>

### 概念位相論 / Conceptual Topology 
This theory, named 概念位相論 or Conceptual Topoloy, was proposed by **No Name Yet Exist**.

GitHub: https://github.com/No-Name-Yet-Exist/Conceptual-Topology<br/>
Note: https://note.com/xoreaxeax/n/n3711c1318d0b
Zenodo: https://zenodo.org/records/15510119

---

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.