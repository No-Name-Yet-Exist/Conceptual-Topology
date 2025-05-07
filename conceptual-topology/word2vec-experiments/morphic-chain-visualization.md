# morphic chain visualizaiton
Firstly, we could observe  Quasi-Natural Transformation of Meaning Systems, in other words, quasi-communicative diagram in word2vec.


### First Model
We used this model to explain Quasi-Natural Transformation of Meaning Systems in morphic chain, but it did not work as this model described in word2vec. Simply because the word canine is almost a paraphrase of dog, and even treated as more specific/individul word due to its low frequency in word2vec space.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/she-human-mammal-canine-dog.png)


```
          R
    she   ←  dog     
     |         |
     |    Z    |
   human  ←  canine  
      \      /       
       mammal

```

### Second Model
In this second model, we introduced 3 axis fixation by integrating time axis, size axis and abstraction level as follows to stabilize the illustration of the meaning structure. And this model successfully demosntrated the quasi-communicative diagram.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-she-girl.png)


```
          R
   girl  ←    puppy  newer + small + specific
     |         |
     |    Z    |
   she  ←     dog      abstraction of all
      \      /       
       mammal

```

### Third Model
We reduced one axis, which is time axis, replacing she to female and yet still
We could obtain similar quasi-communicative-diagram. Apparently, if we intend to observe the illustration of the digram, we need to at least maintain the 2 axis, ideally more than 3 axis to stablize the representation.

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/quasi-communicative-diagram/puppy-dog-mammal-female-girl.png)


```
          R
   girl  ←    puppy  newer + small + specific
     |         |
     |    Z    |
   female  ←     dog      abstraction of all
      \      /       
       mammal

```

# Conclusion
The quasi-natural transformation is demostrable in also word2vec space. The next thing we would like to experiment is that the rupture model and restoration of the rutpure by introducing Z.




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

plt.title("PCA of Semantic Structure (Word2Vec)")
plt.grid(True)
plt.axis("equal")
plt.savefig("image.png") 
plt.show()


```

### the used model
Please refer to word2vec.md