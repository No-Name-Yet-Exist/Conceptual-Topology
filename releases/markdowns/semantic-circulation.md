# Meaning Circulates —  Generative Semantics via Conceptual Topology

### Introduction
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
他動詞はA verb BというFunctor性、写像性を内包する概念。


これら知識を合わせるとチョムスキーによる生成文法を以下のように書き換えることができる

She has a dog with a long tale.
上記文章を樹形図に書き直すと以下のとおりです。

```
S
├── NP (主語)
│   └── PRP: She
├── VP (述語)
│   ├── V: has
│   └── NP (目的語)
│       ├── Det: a
│       ├── N: dog
│       └── PP (前置詞句)
│           ├── P: with
│           └── NP
│               ├── Det: a
│               ├── Adj: long
│               └── N: tail
```

She と has は同階層です。位相論的に考えればshe と has は 連続的関係、もしくは写像関係にあります。 保存される構造は動作主体です。

動作主体 → 動作主体が動作する

上記写像関係は一見わかりにくいですが、スペイン語で顕著です。
Tiene un perreo con cola larga.
(She) has a dog with a tale long.

動作主体が省略され動詞に同化しています。つまりHomeomorphismとして動作主体が動詞に埋め込まれているか、isomorphicとして扱われています。（恐らく動作主体の区別がついているのでisomorphic）

２階層目はa dog
３階層目は with
４階層目はa long tale

犬は尻尾では無いのでwithがFunctor として写像されています。（犬の一部としての尻尾）
F_with: Dog → a long tale

概念位相論的に書き直すと以下のとおりです。


In PCA, the structure of *she has a dog with a long tale* is not visible, so we divided 
this sentence into 2 categories: she has dog and with long tale. As the result, this visualized "she has dog has" a communicative structure as we expected and with mediated the morphic relation between long and tale from dog

```         
                         tale
                           |
             Functor       | 
 She  -  Dog  ----→ with   | 
   \    /                \ |
     Has                  long

Note: Two PCA are artificially combined for visualization
```

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/she-has-dog.png?raw=true)

![alt text](https://github.com/No-Name-Yet-Exist/Conceptual-Topology/blob/main/releases/resources/meaning-circulates/with-long-tale.png?raw=true)

```
C₁: f: She → has 
             / F // she relates to a dog
C₂: a dog ←/
     ↓ F_with //what kind of dog
C₃: g: tail → long

```

We formalize this as:
A → B → C + α


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
