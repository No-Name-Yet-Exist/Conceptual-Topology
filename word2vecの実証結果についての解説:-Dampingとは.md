Word2vecのプログラムの背景: Dampingとは

今回解説するプログラムは以下です

```python
from gensim.models import KeyedVectors
import numpy as np
import matplotlib.pyplot as plt

# word2vecロード
model = KeyedVectors.load_word2vec_format('word2vecのファイルパス', binary=True)

def vec(w): return model[w]

# 対象ペアとrupture語
pairs = [
    ('black', 'white', 'light'),
    ('cat', 'dog', 'animal'),
    ('apple', 'banana', 'fruit'),
    ('sun', 'moon', 'sky'),
   ('life', 'death', 'human'),
   ('true', 'false', 'answer'),
]

def compute_damping(w1, w2, rupture):
    axis = vec(w2) - vec(w1)
    axis /= np.linalg.norm(axis)
    rupture_dir = vec(rupture).copy()
    rupture_dir /= np.linalg.norm(rupture_dir)
    
    def proj(w, remove_rupture):
        v = vec(w)
        if remove_rupture:
            v = v - np.dot(v, rupture_dir) * rupture_dir
        y = np.linalg.norm(v - np.dot(v, axis) * axis)
        return y

    before = (proj(w1, False) + proj(w2, False)) / 2
    after  = (proj(w1, True)  + proj(w2, True))  / 2
    damping = before - after
    return damping

# 結果出力
for w1, w2, rupture in pairs:
    damping = compute_damping(w1, w2, rupture)
    print(f'{w1}-{w2} (rupture: {rupture}) → damping: {damping:.4f}')
```

dampingを理解するには前提知識として次が必要です
概念は属性射ベクトルの集合としてみています。
C = { a1_vec, a2_vec, ..., an_vec }

各概念の定義を属性ベクトル集合で表現すると次のように書けます
dog = {Animal⃗, Canine⃗, Domesticated⃗, Pet⃗}
cat = {Animal⃗, Feline⃗, Domesticated⃗, Pet⃗}

dampingの算出操作としては、まずanimal(rupture)を引く、そのあとにx軸成分を引く(差分軸除去)ということをしています
　→ dog-animal-(dog-cat)

コードではこの部分です
def proj(w, remove_rupture): v = vec(w) if remove_rupture: v = v - np.dot(v, rupture_dir) * rupture_dir y = np.linalg.norm(v - np.dot(v, axis) * axis) return y

単語ベクトルからanimal成分を除去
v = v - np.dot(v, rupture_dir) * rupture_dir

単語ベクトルからx軸(差分ベクトル)成分を除去
y = np.linalg.norm(v - np.dot(v, axis) * axis)

一言で言えば、dogという概念がanimalという意味成分と犬らしさを示す意味成分以外にどれだけ支えられているかを測っています。と言っても難しいかと思われますので、意味集合とモノイドで示します。

dogやcatを意味集合として書くと例えば以下のように書けました。
dog = {Animal⃗, Canine⃗, Domesticated⃗, Pet⃗}
cat = {Animal⃗, Feline⃗, Domesticated⃗, Pet⃗}

ベクトルの操作をモノイドで計算します
dog-animal={Animal⃗, Canine⃗, Domesticated⃗, Pet⃗} ⊖ animal =  {Canine⃗, Domesticated⃗, Pet⃗}
dog-cat = {Animal⃗, Canine⃗, Domesticated⃗, Pet⃗} ⊖ {Animal⃗, Feline⃗, Domesticated⃗, Pet⃗} = Canine⃗ - Feline⃗

dog-animal-(dog-cat) = {Canine⃗, Domesticated⃗, Pet⃗} ⊖ ( Canine⃗ - Feline⃗ )
 = {Feline⃗ , Domesticated⃗, Pet⃗}

dog_after = dog-animal-(dog-cat) =  {Feline⃗ , Domesticated⃗, Pet⃗}
つまりAnimal成分が抜けている状態になる。

dog_before = dog - (dog-cat)=- cat ≒ dog = {Canine⃗, Domesticated⃗, Pet⃗}
※≒で繋げられるかは実際に概念空間を見ないと分かりませんが、dog catが対立概念であることを踏まえdog = -catとしてここでは読んでいます。

この時Dampingの計算は次の通りになります。
Damping =  dog_before - dog_after = {Animal⃗, Canine⃗, Domesticated⃗, Pet⃗} ⊖ {Feline⃗ , Domesticated⃗, Pet⃗} =  {Animal⃗, Canine⃗, -Feline⃗ } ≒ {Animal⃗, Canine⃗ }

Dampingとは{Animal⃗, Canine⃗ } 、言い換えればAnimal(rupture)を取り除いた後の変化量である{Animal⃗, Canine⃗ } を測っている※1。これが大きい場合dogという概念はanimal依存であると分かるというものでした。

※1 {Animal⃗, Canine⃗ } Canineが残っていますがDamping自体が主にAnimal成分の消失に伴う変化量となっています。Canineについては残余の属性でありDampingの主要因ではありません。

Damping =rupture（例：Animal⃗）成分を除去した時、ベクトルの変化量
Damping = |Proj_before| - |Proj_after|
ここで変化しているのは、rupture軸に依存していた成分が消えたことで生じるズレであり、Dampingはrupture成分（＝Animal⃗）がどれだけ概念を支えていたかを測っています。

この記事はFair Use対象外です。
This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.