# XOR in Word2Vec
We modeled semantic XOR algorithm in Word2Vec and found it works as we intended however it also showed its limitations.

### Semantic XOR algorithm in Word2Vec

**XOR definition in CTL**</br>
In a conceptual topological framework using a shared semantic frame (e.g. Female), XOR between two concepts p and q is defined as follows.
```
using z-space Female
p ⊻ q := (p ∨ q) ⊖ (p ∧ q)
girl ⊻ woman
= (girl ∨ woman)  ⊖  (girl ∧ woman)
= age-attribute|Attribute
```
We approximate this conceptual XOR using geometric operations in vector space.

OR (p ∨ q): approximated using KMeans clustering on the two word vectors.
KMeans computes a center that captures the semantic union of the terms, and can be interpreted categorically as a colimit (coproduct) of the two semantic points.
</br>
AND (p ∧ q): Approximated using Principal Component Analysis (PCA). PCA identifies the principal axis of shared variance between the word vectors, which corresponds to the semantic intersection, i.e., their structural commonality. From a categorical perspective, this can be understood as the pullback of two morphisms under a shared semantic frame (Z-frame).

XOR (p ⊻ q): defined as the vector difference between the semantic union and the intersection.
```
    XOR(p,q):=OR(p,q)−AND(p,q)
```
This extracts the non-overlapping semantic residue—that is, what each concept contributes that is not captured by their shared structure. And commutativity of XOR operation is ensured by KMeans and PCA.

# Computation Results

**multicellular ⊻ unicellular**</br>
We successfully extracted a meaningful semantic difference between the concepts multicellular and unicellular using the XOR operation. The result reflects biologically and historically coherent associations, including evolutionary milestones and structural taxonomies.
```
--- multicellular vs unicellular ---
    multicellular : Similarity = 0.6552
    Cambrian_Explosion : Similarity = 0.3634
    multicellularity : Similarity = 0.3576
    Cambrian_explosion : Similarity = 0.3555
    multicellular_animals : Similarity = 0.3474
```
This result indicates that XOR captured the semantic residue corresponding to evolutionary complexity, aligning with the conceptual leap marked by the Cambrian explosion.

**Venus ⊻ Earth**</br>
In contrast, the XOR result between Venus and Earth failed to yield any meaningful semantic distinctions. 
```
--- Venus vs Earth ---
        Iordanis : Similarity = 0.0000
    bloody_dogfighting_ring : Similarity = 0.0000
    Malku_Khota_Silver : Similarity = 0.0000
    justice_Duncan_Ouseley : Similarity = 0.0000
    PlayMesh_recently : Similarity = 0.0000
```
We interpret this failure as a limitation of the vector space representation.
In many linguistic contexts, Venus is often described in close association with Earth (e.g., “Earth’s twin,” “similar size and composition”), leading to dense vector overlap in Word2Vec embeddings. As a result, XOR produced a direction that lacks lexical representation in the model’s vocabulary, or whose semantic differentiation is absorbed into shared context.


**Conceptual Hierarchy**</br>
The XOR operation also reveals conceptual hierarchies embedded in the lexical space. When applied to pairs where one term is a more general or more advanced form of the other, XOR tends to return the dominant concept or its representative lexical cluster. This suggests that XOR does not merely reflect difference—it captures directional semantic elevation or abstraction.

**monolingual ⊻ bilingual**
In this pair, bilingual represents a more inclusive or cognitively complex category than monolingual. The XOR operation retrieves variants and repetitions of bilingual, reflecting the asymmetry of generality.
```
--- monolingual vs bilingual ---
       bilingual : Similarity = 0.4204
      bi_lingual : Similarity = 0.2727
       Bilingual : Similarity = 0.2706
            WNZR : Similarity = 0.2633
    SACATON_Ariz. : Similarity = 0.2608
```
The lexical outputs confirm that bilingual absorbs monolingual in usage and representation.

**polyglot ⊻ bilingual**
Here, polyglot can be considered a higher-order linguistic ability, encompassing bilingual.
XOR returns polyglot as its own difference, with surrounding words semantically less coherent—indicating semantic dominance with sparse lexical differentiation:
```
--- polyglot vs bilingual ---
        polyglot : Similarity = 0.3376
      reprobates : Similarity = 0.2846
         badland : Similarity = 0.2845
      imposingly : Similarity = 0.2838
       merciless : Similarity = 0.2835
```
This suggests that polyglot occupies a semantically higher but sparsely connected position in the embedding space.

**highschool ⊻ university**
In this example, university is both institutionally higher and semantically broader than highschool.
XOR retrieves university and terms like provost—a high-ranking academic role—indicating that the semantic difference aligns with an educational progression.
```
--- highschool vs university ---
      university : Similarity = 0.4924
         provost : Similarity = 0.3953
      University : Similarity = 0.3801
    Provost_Kathy_Krendl : Similarity = 0.3708
    Martin_Jischke : Similarity = 0.3702
```

In all three cases, XOR extracts a form of semantic elevation or abstraction, pointing toward the concept that subsumes or generalizes the other. This suggests that XOR is not merely a symmetric difference operator, but also captures hierarchical asymmetry (i.e., where A ⊆ B), particularly when applied to ordered conceptual domains.

**(android ⊻ robot) ∧ (humanoid ⊻ human) ≈ android**</br>
We extended the semantic computation by composing XOR and AND operations.
```
**(android ⊻ robot) ∧ (humanoid ⊻ human)**
```
This structure computes the intersection of two semantic differences
```
    android ⊻ robot captures the human-like qualities added to a robot
    humanoid ⊻ human captures the robot-like qualities subtracted from a human
```
The resulting intersection represents the shared conceptual space between humanness and robotness.
Remarkably, this composite vector points back to the word "android" itself.

```
     android : Similarity = 0.4980
       WinMo : Similarity = 0.4061
  myTouch_4G : Similarity = 0.4041
Samsung_Omnia : Similarity = 0.3972
  Android_OS : Similarity = 0.3869
```

Also we observed that the order and selection of words in XOR expressions significantly affects the result. When we reversed the pairing used in the previous computation.
```
(humanoid ⊻ robot) ∧ (android ⊻ human)

       human : Similarity = 0.4354
minister_Anisur_Rahaman : Similarity = 0.2970
       Human : Similarity = 0.2944
  Sally_Bott : Similarity = 0.2869
Rashad_Kaldany : Similarity = 0.2849

```

The output collapsed toward "human". This collapse can be attributed to semantic imbalance in the vector pairs. Both humanoid and human are strongly aligned with humanness and both android and robot lean toward mechanical or robotic connotations. As a result, the XOR differences fail to counterbalance.
```
    humanoid ⊻ robot ≈ strong humanness (since humanoid is conceptually close to human)
    android ⊻ human ≈  robotness + humanness (since human has more humanness than android)
```
This indicates that the intended robotness component is underrepresented, and thus the AND result becomes semantically biased toward the dominant conceptual pole.


### The limitation of Word2Vec for semantic computation
Even when the conceptual XOR framework is formally correct and structurally well-defined, it may fail to produce meaningful results when implemented on Word2Vec embeddings. We observe the following key limitations.

**1.Pragmatic asymmetry**
Simple vector subtraction (e.g., vec1 − vec2), which underlies the XOR operation, is often distorted by asymmetric usage patterns in natural language. For instance, while "king" and "queen" may appear structurally symmetric, "queen" is frequently associated with culturally gendered contexts—such as fashion, royalty, or celebrity. As a result, the XOR vector may reflect pragmatic residue rather than the intended semantic difference.


**2.Statistical Bias in Distributional Models**
Word2Vec relies heavily on co-occurrence statistics. Words or concepts that appear less frequently or in limited contexts are not well-represented, regardless of their semantic importance. Thus, rare but semantically distinct concepts may be marginalized, causing XOR results to either collapse toward dominant vectors or fail to generalize at all.

Example:
```
King ∨ Queen → does not yield Human for example
```
This makes XOR results overly sensitive to usage-dependent connotation rather than structural abstraction. And bias by statistically heavy modeling causes not frequently coocuring words are not evaluated well.


**3.Failure in Verbalization**
Even when the XOR vector points to a meaningful conceptual direction, Word2Vec can only return words that already exist in its vocabulary: similar_by_vector(). If no such word lexically expresses the semantic residue captured by XOR, the model will either, return unrelated or noisy items, or fail to project the result back into the lexicon at all. This highlights a core limitation of distributional semantics.



```python
import numpy as np
from gensim.models import KeyedVectors
from sklearn.decomposition import PCA
from sklearn.cluster import KMeans
from numpy import dot
from numpy.linalg import norm

def cosine_similarity(vec1, vec2):
    return dot(vec1, vec2) / (norm(vec1) * norm(vec2))


def calc_xor(vec1,vec2):
    vecs = np.vstack([vec1, vec2])

    # AND = PCA
    pca = PCA(n_components=1)
    pca.fit(vecs)
    projected = pca.transform(vecs)
    val_and = pca.inverse_transform(projected.mean(axis=0))

    # OR = KMeans
    kmeans = KMeans(n_clusters=1, random_state=42, n_init='auto')
    kmeans.fit(vecs)
    val_or = kmeans.cluster_centers_[0]

    # XOR
    return val_or - val_and

def calc_and(vec1,vec2):
    vecs = np.vstack([vec1, vec2])

    pca = PCA(n_components=1)
    pca.fit(vecs)
    projected = pca.transform(vecs)
    return pca.inverse_transform(projected.mean(axis=0))

def calc_or(vec1,vec2):
    vecs = np.vstack([vec1, vec2])

    # OR = KMeans
    kmeans = KMeans(n_clusters=1, random_state=42, n_init='auto')
    kmeans.fit(vecs)
    return kmeans.cluster_centers_[0]

#model path
model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

w1="Venus"
w2="Earth"
xor=calc_xor(model[w1],model[w2])

print(f"--- {w1} vs {w2} ---")
for word, score in model.similar_by_vector(xor, topn=5):
    print(f"    {word:>12s} : Similarity = {score:.4f}")


xor1=calc_xor(model["robot"], model["android"])
xor2=calc_xor(model["humanoid"], model["human"])
result_vec=calc_and(xor1,xor2)

print("xor and and")
for word, score in model.similar_by_vector(result_vec, topn=5):
    print(f"{word:>12s} : Similarity = {score:.4f}")
```

----
This document and all conceptual content therein are © [No Name Yet Exist], 2025. 
All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.