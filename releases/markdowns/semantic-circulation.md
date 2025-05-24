# Meaning Circulates —  Generative Semantics via Conceptual Topology

# Introduction
Language exhibits a circulating structure in its semantics.
This study explores how sentences are organized and interpreted by combining Principal Component Analysis (PCA) with Conceptual Topology—a category-theoretic framework for modeling semantic flow and structural meaning.

Reference:
**Meaning in Motion: A Category-Theoretic Framework for Conceptual Topology**
https://zenodo.org/records/15455079


# Semantic Cirulation
By applying Conceptual Topology, we can visualize how words are combined and structure meaning.

### Identity Morphism
The sentence Yes is a minimal linguistic unit—a single-word sentence.
It exhibits a semantic identity, represented by the following morphism:
```
Yes is Yes.
f: Yes → Yes
∴id_f
```
![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/yes-is-yes.png?raw=true)
In PCA space, this is observed as a point—an unmoving semantic center.


### Homeomorphic Relation

The sentence This is a dog expresses a basic referential mapping.
Here, This acts as a morphism from a real-world object, projected onto a conceptual object, dog—establishing a semantic mapping from the observed to the conceptual.

```
f: This → dog  // This is a dog
f-1: dog → this  //The dog is this

g: this → this 
∴id_g
```

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/this-is-dog.png?raw=true)
In PCA space, this is typically observed as a linear alignment—
a directed semantic path between referent and concept,
with identity preserved via mutual reversibility.


### Communicative Triangle
**This dog is beatiful** - This sentence exhibits a triangular communicative structure, where three elements interact to produce a unified semantic impression.

```
This dog is beatiful

This  - dog 
   \    /
  beatiful
```
![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/this-dog-beautiful.png?raw=true)

Here, This and dog form a composite subject, both pointing toward and being qualified by beautiful.
The triangle reflects a semantic circuit—a three-point relational topology—where reference (This), substance (dog), and evaluation (beautiful) converge into a stable communicative unit.


This sentence can be reduced to a homeomorphic relation by omitting dog.
This reduction is semantically valid, grounded in the bidirectional relation between the referent (this) and the predicate (beautiful), forming a minimal semantic core.
```
this is beatiful

f: this → beatiful
f-1: beatiful → this
g: this → this
∴id_g
```


###  Additive Structure
This sentence is composed of a core three-word relational structure, with so much functioning as an additive semantic extension.

**He loves me so much.**
```
 He - loves - me
  \         /
    so much
```

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/he-loves-me-so-much.png?raw=true)

From this PCA visualization, we observe that *love* mediates between *he* and *me*, forming a semantic anchor.
The intensifier so much extends this core structure without disrupting its internal identity.

We can formalize this as:
```
(λx. so much(x)) (he → me | love)
```
This expression represents a triadic relation between *he* and *me*, mediated by *love*, and further intensified by the function *so_much* —
an external semantic modifier that amplifies the emotional vector of the relation,
without altering its underlying commutative structure.


# Remapping Generative Grammar
We reinterpret Chomsky’s Generative Grammar framework through the lens of Conceptual Topology, to reveal how syntactic form is sustained through underlying semantic continuity.


Let us consider the sentence:

*She has a dog with a long tail.*

We begin by transcribing this into a standard syntactic tree:

```
S
├── NP (subject)
│   └── PRP: She
├── VP (predicate)
│   ├── V: has
│   └── NP (object)
│       ├── Det: a
│       ├── N: dog
│       └── PP (prepositional phrase)
│           ├── P: with
│           └── NP
│               ├── Det: a
│               ├── Adj: long
│               └── N: tail
```

### From Tree to Topology

In traditional generative grammar, *She* and *has* are placed at parallel syntactic branches.
However, from a topological perspective, they form a continuous relation—or more precisely, a semantic morphism—preserving the role of the agent across the conceptual space.

In this mapping:
    She → has expresses the activation of agency
    The morphism preserves subject continuity, even as the syntactic structure branches

Thus, we begin to reinterpret syntactic hierarchy as semantic flow,
where morphisms carry roles, and identity is preserved not through position but through structural invariance.

This mapping relation may not be immediately evident in English,
but becomes more apparent in Spanish:

**Tiene un perro con cola larga.**  
*→ (She) has a dog with a long tail.*

Here, the agent (she) is omitted and absorbed into the verb *tiene*.
In this case, the agent is either:

    homeomorphically embedded within the verb (semantic continuity is preserved through structural integration), or

    treated as isomorphic to the verb phrase, assuming the agent role is still distinguishable through context.

The latter interpretation is more likely, since Spanish maintains clear subject-verb agreement, indicating that the agent is not erased, but structurally mirrored.

### Functorial Interpretation of Prepositions

In the syntactic structure of the sentence:

*She has a dog with a long tail.*

The second hierarchical level is a dog,
the third is the preposition with,
and the fourth is a long tail.

From a topological and categorical perspective, *with* acts not merely as a preposition,
but as a Functor that maps from the conceptual object *dog* to its associated attribute tail.

We can formalize this as:
```
F_with: Dog → a long tale
```

In PCA space, the full sentence She has a dog with a long tail does not appear as a single coherent structure.
To clarify its internal semantic relations, we divide the sentence into two conceptual components:

    (1) she has a dog

    (2) with a long tail

As a result, the first segment—she has a dog—exhibits a communicative triangular structure,
while the second segment—with a long tail—reveals how with functions as a Functor
mediating the morphic relation between long and tail, and indirectly linking them back to dog.

```         
                         tale
                           |
             Functor       | 
 She  -  Dog  ----→ with   | 
   \    /                \ |
     Has                  long

Note: The two PCA spaces were artificially merged for this visualization.
```

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/she-has-dog.png?raw=true)

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/with-long-tale.png?raw=true)


### Remapping the Syntactic Tree into Conceptual Topology Semantic Flow

We reinterpret the syntactic tree structure of the sentence
*She has a dog with a long tail*
as a Conceptual Topology semantic flow map, where morphisms reflect meaning-preserving relations.

```
C₁:    She → has 
         \   /        // she relates to a dog
          dog 
        
    f: She → Dog
              ↓ F_with  // what kind of dog?
C₂:   g: long → tail
```
Note: There is an interpretable structure where g ∈ Fib(F_with) —
that is, the modifier long → tail exists within the fiber over the functor F_with.

### Functorial Role of Transitive verb
A transitive verb functions not only as a morphism but often as a functor—mapping between conceptual domains.

Consider the verb *give*, which operates as a transformation from an implied subject to a receiver of possession.

In Japanese, this becomes even clearer:

ねえ、それ、ちょうだい。
(Hey, give [that] to me.)

Although the subject is omitted, the request enacts a functorial structure
in which possession is transferred or requested across conceptual roles.

```
   [それ]     ちょうだい     
     |          |
私に ← Functor ← 主語
```

Rewritten in English alignment:
```
   [That]         Give     
     |             |
  Me ← Functor ← Subject
```
The preserved structure is the ownership relationship directed toward the speaker.

We may formalize this functorial action as:
```
f: Owner → Owned ∈ Category A, B  
F: A → B
```
Where F maps ownership structure from the domain (A) to the codomain (B),
reflecting how possession shifts or is preserved in the linguistic operation.


### Reconciling Functorial and Morphic Interpretations in Conceptual Topology

In Conceptual Topology, treating give as a functor and love as a morphism may appear inconsistent at first glance. However, this distinction reflects not a contradiction, but a difference in structural hierarchy.

**Semantic Function of love: Morphism**

In sentences such as He loves me or She has a dog,
the verb denotes a direct, unidirectional conceptual relation:

```
f: he → me | love
g: she → dog | have
```
These represent basic morphisms—arrows preserving semantic identity within a single conceptual frame, typically between two arguments in a static structure.


**Semantic Function of give: Functor**

In contrast to simple binary relations, the verb give implies a semantic transformation—
a dynamic restructuring of conceptual roles across participants.

Specifically, it reorganizes a triadic structure:

    subject → object → indirect object
    i.e., giver → thing → receiver

This transformation can be captured functorially:

```
f: owner → owned ∈ A, B
F: A → B | owned object

Where:
    A = conceptual domain of giver
    B = domain of receiver
    F maps ownership structures from one domain to another
```

Unlike morphisms, which represent direct semantic connections,
this functorial action transfers not only referents but semantic roles.
It preserves internal structure while shifting possessive alignment across conceptual domains.

**Example: I show you this book**

We can model the sentence:
```
I show you this book
I → book → you
```

**Morphic Layer**
```
f: person → book | sight
This represents a direct semantic action.
the person is semantically linked to the book through the act of perception.
```

**Functorial Layer**
```
F: A → B | sight
Where:
    A = conceptual domain of the subject (I)
    B = perceptual domain of the receiver (you)
    F = a functor that maps objects from the subject’s domain
        into the perceptual space of the recipient via sight
```

It was not correct that I told you before.
What I told you  before

The thing - I told you - before 
(過去射としてbeforeとは写像関係 過去射は観測済み)

```
   R
It - correct
 |     | R
What I told you you before
```

I told you のyouをどう見るか

```
        R
I - told - you
```
Notや間接目的語はRuptureとして解釈できるのでは？
要はNotは循環、写像不可能性を意味する: It - correct - what told youは非写像関係

Not right ≠ correct //写像構造の破綻を示す
だから、Not right = wrong //写像不可能性をbridgeする概念を立てると可換になる

```
It - wrong
 |     | 
What I told you you before
```

間接目的語は非可逆性を意味する: youからIに戻れない Iからyouには動作の連続性として変形可能


```python
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from gensim.models import KeyedVectors
import numpy as np

model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

words = ["this","dog"]


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

plt.title("PCA of Semantic Geometry (Word2Vec)")
plt.grid(True)
plt.axis("equal")
plt.savefig("image.png") 
plt.show()
```


This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
