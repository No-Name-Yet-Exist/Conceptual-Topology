# Meaning Circulates —  Generative Semantics via Conceptual Topology

### Introduction
Sentences have circulating structure in its meaning. We explore how sentences are structured using Principle Component Analisys (PCA)and Conceptual Topology, which is category-theoretic framework for semantics.


# Semantic Cirulation
By applying Conceptual Topology, we can visualize how words are combined and structured.

**Identity Morphism**
*Yes* is one word sentence. This satisfies with the following structure.
This is observed in PCA as a dot
```
Yes is Yes.
f: Yes → Yes
∴id_f
```

**Homeormophic Relation**
*This is a dog* *This* points a dog, which works as a morphism of pointed object to conceptual object called dog. This is observed liear structure in PCA.
```
f: This → dog  // This is a dog
f-1: dog → this  //The dog is this

g: this → this 
∴id_g
```

**Communicative Triangle: This dog is beatiful**
This sentence has a triangular communicative structure.

```
This dog is beatiful

This  - dog 
   \    /
  beatiful
```

This sentence can be simplified to homeomorphic relation by dropping *dog*.
This manipulation is supported by the firm grounding of two-way relation of sematic core.
```
this is beatiful

f: this → beatiful
f-1: beatiful → this
g: this → this
∴id_g
```

Sentence is composed with three word relation, thus with a long tale is treated as an additive structure.

She loves me so much.
```
 She - loves - me
         |    /
        so much
```

This structure is also observable in PCA.



From this PCA image, we can observe love mediates he and me, thus we formalize this relation as follows.
he → me | love

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
