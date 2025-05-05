# 意味素

最も小さな概念であり、対立概念の逆射(-OC)一つのみを要素として持つ意味集合。この時意味素は以下の通りに定義できる。

C_0 = {-OC}

以下実証

black whiteの意味集合を以下の通り定義するBlack={-white}White={-Black}

この時以下のモノイド計算をするとblack=whiteが成り立つBlack-(Black-white) = {-white} ⊖ ({-white}, {-black })= {Black}I might've found you :)

Cosine Similarity > 0.8

使用したコード

```python
from gensim.models import KeyedVectors
import numpy as np

# word2vecモデルのロード
model = KeyedVectors.load_word2vec_format('word2vecのパス', binary=True)

def cos_sim(vec1, vec2):
    return np.dot(vec1, vec2) / (np.linalg.norm(vec1) * np.linalg.norm(vec2))

# 単語設定
word_black = 'black'
word_white = 'white'

# ベクトル取得
vec_black = model[word_black]
vec_white = model[word_white]

# 差分計算 (Black - White)
diff_vec = vec_black - vec_white

# Black - (Black - White)
result_vec = vec_black - diff_vec

# コサイン類似度計算
similarity = cos_sim(vec_black, result_vec)

print(f'CosSim(black, black - (black - white)) = {similarity:.4f}')
```


この一見意味のない計算は実はWhite ≈ Blackという結果になる
Black - (Black - White) ≈ Black
White ≈ Black

# 意味素

最も小さな概念であり、対立概念の逆射(-OC)一つのみを要素として持つ意味集合。この時意味素は以下の通りに定義できる。

C₀ = {-OC}
モノイド計算

black whiteの意味素集合を以下の通り定義する
black={-white}
white={-black}

この時以下のモノイド計算をするとWhite ≈ Blackが成り立つ
black - (black - white) = {-white} ⊖ ({-white} - {-black })
≈ {black}

# 理論的背景

しかしなぜモノイド計算するとWhite≈ Blackになるのか、
その理論的背景を説明する

Black - Whiteは単なる減算ではなく、意味射ベクトル生成、または概念変換の意味的経路を生成する操作となる
黒 → 白

Diff(Black, White) ⇒ f_vec : Black → White // 黒→白の意味射ベクトル生成

Black - Diff(Black, White)
= Black - (Black → White)
= Black + (White → Black) //白→黒 つまり黒としての意味射ベクトルに転換
= Black + Black
= 2Black // 計算上は消失したBlackが出てくる Black - (Black - White) = White

この結果から White ≈ Black になる

故に
Black = {-White}
C₀ = {-OC}

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.

