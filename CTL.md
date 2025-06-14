# Conceptual Topology Language (CTL): A Categorical Framework for Semantic Computation
A minimal semantic calculus based on category-theoretic structure, modeling logical operations (AND, OR, XOR, NOT, implication) over contextual frames (Z-frames), and enabling semantic evaluation via conceptual morphisms. This α-version demonstrates the construction of exponential objects, semantic XOR, and Z-dependent entailment classification (χ).

# Logical Operations in Conceptual Topology
Following CTL Examples are simplified version. You need to clarify the Z frame as follows.
```
girl ⇔ woman | Human ∧ Femenity
```

| Logical Symbol | CTL Example         | Categorical Structure       |
|----------------|---------------------|-----------------------------|
| ⊤ (true)       | The concept of truth | Terminal object 1         |
| ⊥ (false)      | A null concept       | Initial object 0 or Zero morphism |
| ¬p (not p)     | σ(Z).Not(f)        | Zero morphism (rupture)     |
| ¬¬p            | Equalizer(σ∘σ, id) | Equalizer (closure of negation) |
| p ∧ q          | girl ∧ dog ≅ mammal | Pullback (common intersection) |
| p ∨ q          | dog ∨ cat ≅ pet    | Coproduct (union of categories) |
| p ⊻ q          | man ∨ woman ≅ genderness | p ⊻ q := (p ∨ q) ⊖ (p ∧ q) |
| p ⇒ q          | dog ⇒ mammal      | Exponential object (Hom(p, q)) |
| p ⇔ q          | girl ⇔ woman     | Isomorphism (bidirectional morphism)|
| p = q          | girl = girl        | Identiy Morphism (conceptual identity) |
| p ≅ q          | girl = woman        | Isomorphism  (conceptual identity) |
| ∃x. P(x)       | ∃ dog. dog ∈ pet   | Co-limit (existential quantification) |
| ∀x. P(x)       | ∀ dog. dog ∈ mammal| Limit (universal quantification) |

<div style="page-break-after: always;"></div>

**XOR** </br>
Example1:
```
using z-space Female
p ⊻ q := (p ∨ q) ⊖ (p ∧ q)
girl ⊻ woman
= (girl ∨ woman)  ⊖  (girl ∧ woman)
= age-attribute
```

Diagram:
```
           Female
          /     \
      girl       woman
        \         /
         \       /
       girl ∧ woman   ← Pullback
            |
            v
       girl ⊻ woman   ← XOR
            ^
            |
       girl ∨ woman   ← Coproduct
```

<div style="page-break-after: always;"></div>

Example 2:
```
using z-space Human

prince = (king ∧ man) ∧ young
princess = (queen ∧ woman) ∧ young
prince ⊻ princess  = genderness

More precisely
Let:
  A = prince
  B = princess
  Z = Human
  f = A ∨ B | Z    // Coproduct
  g = A ∧ B | Z    // Pullback

Then:
  h = f ⊻ g | Z    // Difference morphism: Genderness

Therefore:
  Genderness = prince　⊻ princess | Z
```

Diagram:
```
               Human                   Human
               /   \                   /   \
        prince       princess    prince    princess
            \         /              \         /
             \       /                \       /
          prince ∨ princess        prince ∧ princess      
                ｜                        ｜
                ｜────────────⊖──────────｜
                              | 
                              ∨
                       prince ⊻ princess
                              | 
                              ∨
                          Genderness

```

**Double Negation As XOR**
Xor can express double negation. This simplifies morphic flow. And this formulation *n ⊻ n ⊻ x*
reveals underlying semantic structure of language.
```
not unkind
= n ⊻ n ⊻ x
= x
where: 
n: not, un-
x: kind

n ⊻ n ⊻ x corresponds to 
    not un kind
     n   n  x

楽しくないわけじゃない
  x   n      n
  → x ⊻ n ⊻ n = x 

Commutativity and Associativity ensures the interchangeability of the calculation.
```

Here we hypothesize () signifies the semantic cohesion, 
thus *not unhappy* does not recover to *happy*.
```
not unhappy ≠ happy
 n ⊻ (n ⊻ x)

I didn't say iI amd not happy
   n                 n   x

The formalization will be as follows.
  n ⊻ (n ⊻ x) ≒ x   // approx recovery: pragmatic cancellation
  n ⊻ n ⊻ x = x     // strict algebraic reduction
```

<div style="page-break-after: always;"></div>

**AND in Diagram**
```
prince = (king ∧ man) ∧ young

Let:
 Z = Human
 A = king
 B = man
 C = young

Then:
 P₁ = A ∧ B | Z        (Pullback: adult male royalty)
 P₂ = P₁ ∧ C | Z       (Pullback: adds age attribute)

Therefore:
 prince := P₂ | Z


      Human
     /    \
    /       \ 
   /         \
king         man
   \          /       Human
    \        /         /
      ↘    ↙        ↙       
    king × man    young
         \         /
          \       /
            ↘   ↙
            prince
```

<div style="page-break-after: always;"></div>

**king - man + woman = queen**</br>
```
queen = (king ⊻ man) ∧ woman | Human
```

Diagram:
```
        Human                    Human
        /   \                    /   \
    king      man             king    man
      \        /                \      /
       \      /                  \    /
     king ∨ man                king ∧ man      
         ｜                        ｜
         ｜────────────⊖──────────｜
                       | 
                       ∨
                  king ⊻ man
                       |            Human
                       ∨              ｜
                     Royalty        woman
                       ｜             ｜
                       ｜─────────────｜
                              ｜
                             queen   
```

<div style="page-break-after: always;"></div>

# Application

```python
func exponential(a: Concept, b: Concept, z: Frame) -> ConceptualMorphism:
  """
  Construct exponential object B^A under Z-frame.
  Represents: 'if a then b' interpreted within context z.
  """
  return σ(z).>(a, b)  // represents B^A

func eval(f: Conceptual Morphism, a: Concept, z: Frame) → Concept:
  return f × a | z

//if press then open → it opens
val1 = eval("press", "open", "door") → door → opened door | Door

//if press then open + you press → it opens
f = exponential("press", "open", "door")
val2 = eval(f, "you press") → open | Door // open → open | Dorr

// if means truth = χ(val1, val2)  
// χ: entailment classifier → Ω
if val1 ⇒ val2:
    print("This is about door being opened")

```

<div style="page-break-after: always;"></div>

**simbols**

```
Z : Intermediating variable (conceptual anchor; Z-frame)
| : Frame separator (indicates morphism is mediated by Z-frame)
→: Morphic Flow
↛: Ruptured morphism
F : Cross-category morphism (used in cross-category flow under shared Z-frame)
//: Used to narrate meaning flow of morphic chains.
¬: Absence

M|Z : Monoid of Conceptual Flow under Z-frame
R|Z := { rupture(f) | rupture(f, σ(f) | Z) ≠ ∅ }
e|Z : Identity element of M|Z
D(Aₙ₋₁ | Z) : Morphic chain under Z frame

σ : Conceptual Shifting Morphism
>> : Generalization relation (A >> X ≡ A ⊑ X)
<< : Specialization relation (X >> A ≡ X ⊑ A)
rupture(f, σ(f) | Z) ≠ ∅ : Indicates conceptual rupture
η : Quasi-Natural Transformation: Contextual alignment between morphic chains.

⊕:  Conceptual morphism set addition in σ or morphic merger such as:
    (k₂ ∘ k₁) ⊕ (q₂ ∘ q₁) = human → royalty | Z'
⊖:  Conceptual morphism set subtraction 
    Removes specified morphisms from a morphic chain or set.
```

**Notations**
```
Concept / Word (lexeme):
    - Lower case (e.g., puppy, dog, girl, she)

Z Frame (conceptual anchor):
    - Upper case (e.g., Mammal, Human, Agency, Domesticated, Royalty)

Type variables (A, B, X, Y, Z in formal definitions):
    - Follow standard formal notation (uppercase) 

Example:
puppy → dog | Mammal
A → B | Z

Morphism: f, g, h
Functor: F
```

<div style="page-break-after: always;"></div>

**Simplified Form of Identity Morphism:**

1. f: X → X | X  (Category-theoretic identity) </br>
　In simplified form: X </br>
  or more explicitly: id_X </br>
  
2. f: X → X | Z  (Mediated identity with conceptual flow)</br>
　In simplified form: X | Z</br>

**σ Operator**

```
σ(X). Not(x){ A ↛ B | Z}     →     Rupture under Z frame
σ(X). so_much(x){A → B | Z}  →     Preservation & amplification under Z frame
σ(X). >>(x,y)                →     Conceptual Shifting x to y (Generalization) as function form
σ(X). <<(x,y)                →     Downward Shifting x to y (Specialization) as function form
σ(X). >(x,y)                 →     Conceptual Shifting 
```

</br>

**Conceptual Morphism Set Operators**

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

This is version α 1.1

### Conceptual Topos Named as 概念位相論 / Conceptual Topology
This theory, named 概念位相論 or Conceptual Topoloy, was proposed by **No Name Yet Exist**.

Meaning no longer escapes.<br/>
It circulates within the morphic fibration.<br/>
We, once again, govern the topology of meaning.<br/>

GitHub: https://github.com/No-Name-Yet-Exist/Conceptual-Topology<br/>
Note: https://note.com/xoreaxeax/n/n3711c1318d0b<br/>
Zenodo: https://zenodo.org/records/15455079

----
 © 2025 No Name Yet Exist.
 This work is licensed under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0
 International License (CC BY-NC-ND 4.0).
 You may cite or reference this work with proper attribution.
 Commercial use, modification, or redistribution is prohibited without explicit permission.
