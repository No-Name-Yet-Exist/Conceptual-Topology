# Morphic Chain Visualization

We here demonstrate that quasi-natural transformation of meaning systems—in the form of quasi-commutative diagrams—can be empirically observed in Word2Vec space. 


### Morphic Chain
https://github.com/No-Name-Yet-Exist/Articles/blob/main/conceptual-topology/principles/morphic-chain.md


### First Model: Failure of Commutativity due to Semantic Equivalence

In this model, we attempted to demonstrate a quasi-commutative diagram using the chain:
she → human → mammal, dog → canine → mammal.

However, the word canine functions more as a synonym or paraphrase of dog, and in Word2Vec space it appears even more specific or unusual due to its relatively low frequency. Thus, the morphic transformation between dog and canine lacks sufficient structural contrast, preventing commutative structure.

```
          R
    she   ←  dog     
     |         |
     |    Z    |
   human  ←  canine  
      \      /       
       mammal

```

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/she-human-mammal-canine-dog.png)




### Second Model: Successful Quasi-Commutativity through Axis Fixation

To stabilize the diagram, we introduced three semantic axes:

    ・Temporal axis (puppy vs dog),

    ・Size/specificity axis,

    ・Abstraction level (girl vs she).

This model successfully formed a quasi-commutative diagram in Word2Vec space, with meaningful word location.

```
          R
   girl   ←  puppy  newer + small + specific
     |         |
     |    Z    |
   she    ←   dog      abstraction of all
      \      /       
       mammal

```

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)



### Third Model: Sustained Quasi-Commutativity with Reduced Axes and Intensified Semantic Role

In this model, we replaced she with female. The visualized image shows that the female did not show up as clearnly as she did, yet it still maintained the observable semantic formation.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-female-girl.png)


And the distortion created by female can be understood as female includes gender role which dog does not and female was pulled away from dog towards gender axis. To support this we added "she"(generalized or diluted femenity, which some even say she, refering to a car, runs really good). And also we added "human"(gender less), and "ape" as the categorical term for human to fill the gap between mammal and girl. As the result, we could observe the bulge created by female tries to converge into mammal through:

girl → she → female → human → ape → mammal


![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/she-female-human.png)


### Fourth Model: Semantic Circularity
We noted that puppy and girl are located on the same level, so we added "baby" as Z.
This completed the semantic circle as we intended.
baby → girl → she → female → human → ape → mammal → dog → puppy →　baby

Note: We could not use "young" since it is mostly used with human, so word2vec heavily evaluates the relation with words such as girl and undervalues the relation with puppy. For this reason, we used baby instead.


**In this PCA, we could observe four morphic chains and the semantic formatoin circulates.**

D_gender: girl - she - female 
D_humanity: female - human - ape - mammal
D_canine: puppy - dog - mammal
D_baby: puppy - baby - girl

η: puppy → human_girl | baby // canine to human under baby
f: female → human // femenity to human 
η: human → dog | mammal // human to canine under mammal

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/baby-morphic-circle.png)


![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/semantic-circulation-with-arrows-v2.png)



# Conclusion

While our current understanding of the mechanisms behind word alignment remains provisional and requires further analysis, we have demonstrated that **quasi-natural transformations are observable** within Word2Vec embeddings. And also we could observe the circulation of morphic chains.

**Next step:**
We will explore rupture modeling, and introduce Z to represent and potentially restore collapsed morphic chains.


### Code we used

``` python
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from gensim.models import KeyedVectors
import numpy as np

model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

# 単語グループ
words = ["puppy", "dog", "girl", "female", "mammal"]

#words = ["puppy", "dog", "girl", "she", "mammal"]
#words = ["dog", "canine", "she", "human", "mammal"]
#words = ["baby","girl","she","female","human","ape","mammal","dog","puppy"] 


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

### the used model
Please refer to word2vec.md


This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.