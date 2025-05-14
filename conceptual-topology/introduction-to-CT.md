Title: Semantic Geometry from Z-Frame Topologies: A Categorical Model of Lexical Structure

# Introduction:
Natural language exhibits variability, ambiguity, and strong context-dependence, challenging formal semantic modeling. However, through the lens of category theory and Z-frame used in this theory, certain latent regularities emerge. This paper explores the idea that word meaning is not merely a function of proximity in embedding space, but a topological structure defined by morphic continuity over conceptual anchors, called Z-frames.


# Semantic Projections and Topological Formalization

By projecting 7 words—["body", "mind", "sugar", "yummy", "cake", "innocent", "hungry"]—into a 2D space, the resulting geometry revealed a striking pattern:

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/semantic-geometry.png)

**Figure1: Z = sugar**</br>
This diagram reveals that clusters such as ["yummy", "cake"] and ["mind", "body"] emerge symmetrically around the semantic anchor sugar, forming a quasi-balanced configuration. Notably, "body" and "cake" align across opposing poles, indicating that the concept of sweetness (Z = sugar) functions as a mediating structure—bridging semantic crevasses while simultaneously inducing an communicative relation between otherwise distinct lexical domains. Lexicons used are from “Yummy” (INNA, 2023).


### Different Cases
**Figure2: Z = body**</br>
This reveals different clusters are symmetrically placed over body. Lexicons used are from “Yummy” (INNA, 2023).

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/innocent-hungry.png)

**Figure3: Z = mind** </br>
The lexical structure must be carefully configured for semantic coherence. While Z = body serves as a stable reference point that preserves morphic continuity, Z = mind fails to maintain lexical balance and induces structural collapse. As shown in this diagram, morphic chains lose alignment, and fiber coherence deteriorates.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/z=mind.png)


This observation demonstrates that Z-frame selection is not arbitrary. Effective Z-frames function as semantic attractors, enabling fiber cohesion and stable topologies. In contrast, inappropriate Z-frames—such as "mind" in this case—introduce ruptures, disconnected fibers, and distorted morphisms, leading to semantic incoherence.
Lexicons used are from “Yummy” (INNA, 2023).




**Figure4: Z = mammal**</br>
This reveals different clusters are symmetrically placed through mammal. puppy and girl. These lexical elements semantically converge through the conceptual anchor mammal, forming a coherent fiber structure.
![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)

**Quasi Communicative-Diagram**
```
           
    girl      puppy    
     |          |
     |          |
    she        dog      
      \        /      
        Mammal

```


**Figure5: Z = baby and mammal** </br>
This creates morphic circulation.
Meaning transformation forms a closed morphic circulation over intersecting Z-frames: baby and mammal

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/semantic-circulation-with-arrows-v2.png)


**Quasi Communicative-Diagram**
```
        Z = baby
    girl   ←   puppy    
     |          |
     |          |
    she        dog      
      \        /      
        Mammal

```



I hypothesize that these lexical arrangements do not reflect mere coincidence, but rather manifest a deeper semantic topology, governed by morphic continuity over a Z-frame.

The theory behind these results, I proposed the following structure:

```
CT := (C, B, π: E → B, Fb := π⁻¹(b), A ≅ b ⋃ Nat(Hom(−, A), Fb))

Where:
  - C is the category of concepts (objects = words)
  - B is the base space of Z-frames (semantic continuity anchors)
  - E is the total semantic space (word vector embedding space)
  - π projects each concept to its semantic base (Z-frame)
  - Fb is the fiber (semantic morphic chain) over a base b
  - A ≅ b ⋃ Nat(Hom(−, A), Fb) interprets each concept A via its morphisms relative to its   Z-frame b (Yoneda perspective defined in appendix): This is observable using specific pairs such as black and white. 
```

# Morphic Chain Complexes and Semantic Dynamism

We formalize the observed phenomena in Fig2 as Morphic Chain Complex and 
relation between morphic chains.

**Quasi Communicative-Diagram**
```
         Z = baby  
    girl   ←   puppy    
     |          |
     |          |
    she    ←   dog      
      \        /      
        Mammal

```
### Morphic Chain Complex
We define *girl → she → mammal* and *puppy → dog → mammal* as Morphic Chain Complex.

Let D(Cₙ₋₁ | Z) := Category of Morphic Chains over Ob(Cₙ₋₁) within Z frame

Objects are chain complexes A₀ → A₁ → A₂ → ...
representing conceptual transitions (e.g. "he" → "human" → "mammal" | life)
, which means Morphisms are chain maps that preserve morphic Identity(Z or rupture,which means non-invertibility) (i.e. maps between meaning-change sequences that maintain structural identity)


### Mirror Morphism Definition:

We define Morphic-Chain Mirror as a contextual correspondence between two Morphic Chains, where conceptual structures from distinct but meaning-aligned vocabularies are mirrored through quasi-natural transformations under a Z-frame. Each mirror maps concept transitions across vocabularies while preserving morphic identity up to rupture.
```
f′: A′ → B  | Z
    → A′ ≠ A, but cod(f) = cod(f′) = B | Y // Y = codomain

We define f′ as a mirror-correspondent morphism of f under a given Z-frame,
if and only if:

∃Z: rupture(f, f′ | Z) ≠ ∅ ∧ cod(f) = cod(f′) | Y
```

### Quasi-Natural Transformation of Meaning Systems
```
η: Dᵢ ⇒ Dᵢ₊₁  | Y // Y = codomain
η_X ∘ Dᵢ({f₁ | Z₁, ..., fₙ | Zₙ}) ≈ Dᵢ₊₁({f′₁, ..., f′ₙ}) ∘ η_Y | Y
for all fᵢ: Xᵢ → Yᵢ | Zᵢ in Dᵢ,  
where f′ᵢ: η_X(Xᵢ) → η_Y(Yᵢ) | Zᵢ is the image morphism under meaning translation

Then: η is a quasi-natural transformation under Z-frame
i.e. η ∈ Mor(C) where C is the contextual meaning category
Example: η: girl → puppy | Z = baby
```

# Communicative Diagram of Semantics

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/cake-yummy-body-sweet.png)

```
Under Z-frame: sugar
        
        g
 Yummy <---- Mind
   |         ↑
 h |         | f
   ↓         |
 Cake  ----> Body

f: Body → Mind | sugar // Bodily sweetness gives rise to a mental perception of sweetness
g: Mind → Yummy | sugar //Mental sweetness leads to the subjective pleasure: "this is yummy."
h: Yummy → Cake | sugar //The abstract sense of yumminess gets grounded in a concrete symbol: cake.

if:
i = h∘g∘f | sugar
Thus:
Cake ≅ Body | sugar // metaphor
```

### king - man + woman = queen
This relationship can be expressed as the following semantic morphism diagram

```
       f
    Q ——→ W
    |     \
  r |       \ g
    ↓         \
    K' ——→ M'
        g
K = king
Q = queen
M' = man
W' = woman

g: Differential Morphism（King → Man）
h: Differential Morphism(Man → Woman)
r: Differential Morphism（Woman → Queen）
f: Composed Semantic Morphism r ∘ h ∘ g 
```

# Conclusion
This geometric coherence suggests a hidden layer of structure in natural language semantics—what I call "semantic geometry through conceptual topology." The theory is still evolving, including definitions for morphisms, identity, absence/void, morphic chain, ontology and so on. This model opens a path toward formalizing metaphor, analogy, and even poetic structure within a rigorous categorical and topological framework. It invites further exploration across natural language processing, translation theory, and cognitive semantics.

Whole theories, codes and further examples are available at: 
https://github.com/No-Name-Yet-Exist/Articles/blob/main/README.md


### Appendix:

The Definition Of Word
A word that includes itself or other words is subsumed by a higher-order concept. That concept, in turn, is structurally embedded within the word.
Therefore, a word is a self-referential structure.

```
// A concept is a structure of oppositional differences
Let C be a concept //e.g. black
Let OC be the opposite concept //e.g. white
C = {−OC₁, −OC₂, ..., −OCₙ} // Yoneda × Structralism

// A word is a concept, and belongs to the category of words
word ≅ C and Ob(Word) ∋ word

// A concept is a bundle of semantic morphisms (in the word2vec sense)
// Interpretable as a more concrete model via Grothendieck fibration
∀ fᵢ ∈ Mor(C), ∃∞_f s.t. fᵢ ⊆ ∞_f

// The structure of semantic morphisms is abstracted into a word
∀ ∞_f, ∃ Word s.t. ∞_f ⊆ Word

and then: Word≅Nat(h∞f​,Language)
// The ∞-structure of morphisms is deployed into the linguistic category as a natural transformation

// Self-identity of the word: word is word
id_word ≈word
```
### Appendix 2
Meaning is calculable as follows.
Or it can be written as set calculation as follows:

Let king = {Royalty⃗, Male⃗, Human⃗}
Let queen = {Royalty⃗, Female⃗, Human⃗}
Let man = {Male⃗} 
Let woman = {Female⃗} 

king - man + woman = queen
{Royalty⃗, Male⃗, Human⃗} ⊖ {Male⃗} ⊕ {Female⃗} = {Royalty⃗, Female⃗, Human⃗}


### Used Code
``` python
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from gensim.models import KeyedVectors
import numpy as np

model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

# 単語グループ
words = ["puppy", "dog", "girl", "female", "mammal"]

# ベクトル取得
vectors = [model[word] for word in words]
labels = words

# 次元削減（PCA）
pca = PCA(n_components=2)
reduced = pca.fit_transform(vectors)

# プロット
plt.figure(figsize=(10, 6))
for i, label in enumerate(labels):
    x, y = reduced[i]
    plt.scatter(x, y)
    plt.text(x + 0.01, y + 0.01, label, fontsize=9)

#矢印付加 
from matplotlib.patches import FancyArrowPatch
for i in range(len(reduced) - 1):
    start = reduced[i]
    end = reduced[i + 1]
    arrow = FancyArrowPatch(start, end, arrowstyle='->', mutation_scale=10, color='gray')
    plt.gca().add_patch(arrow)

start = reduced[len(reduced)-1]
end = reduced[0]
arrow = FancyArrowPatch(start, end, arrowstyle='->', mutation_scale=10, color='gray')
plt.gca().add_patch(arrow)

plt.title("PCA of Semantic Structure (Word2Vec)")
plt.grid(True)
plt.axis("equal")
plt.savefig("image.png") 
plt.show()
```

### Word2Vec Data Set
https://code.google.com/archive/p/word2vec/

### Reference
“Yummy”  (INNA, 2023)

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.