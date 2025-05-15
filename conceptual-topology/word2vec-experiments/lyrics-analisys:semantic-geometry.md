本稿は研究的考察であり、著作権者様からのご指摘があれば速やかに対応いたします。

INNAによるYummyは非常に強い比喩的表現を含む。今回は歌詞に含まれる単語を利用して、歌詞の持つ意味空間構造を可視化していく。また可視化した意味構造を圏論的に分析することで、比喩がどのようにして成り立っているのか、その意味写像の原理について明らかにしていく。


###　歌詞の基本構造
Grothendieck空間として全体空間E=Yummyとした場合、この曲の基底空間はBodyと読める。これは歌詞を読むとわかるが、明らかに体を中心に回っている曲である。それを総称してYummy、または構造的にYummyであることを肯定するためにBodyをいろいろな角度から表現してYummyと曲を名付けていると読んでいる。


### 2圏構造
本曲ではBodyとIsomorphicな単語としてCake、またMindを使用している。
初回の分析ではまずBodyとCake, Sweet, Yummyを使用して歌詞の意味構造を明らかにしていく。

これら単語を選んだ背景としてBodyは背景的主題テーマ、Cakeは身体性を象徴する明示的なテーマ、SweetはSugar、tasteなどと味成分の繰り返しがあるため強い意味成分を持つとし選択。Yummyは曲名であり、歌詞の内容を象徴する形容詞であるため選択。

分析結果は以下の通りで、2圏構造が現れた。

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/cake-yummy-body-sweet.png)


```
Yummy <---- Sweet
  |         ↑
  |         | 
  ↓         |
Cake  ----> Body
```

可換構造としてはBody → Sweet → Yummy → Cakeである
BodyからSweetへの写像を肯定する理由は歌詞にある"I got a lot of sugar" INNA, “Yummy” (2023)から読める。Sweetの写像がYummyである理由は美味しいから甘いは意味論的に不自然。よってSweet→Yummyとする。上記可換構造からCake ≅ Bodyが成り立っているとわかる。

### Z対称構造
上記分析で使用した4単語に合わせて、innocentとhungryを追加した分析である。innocentはmindを修飾しているが、
後の分析でもわかるように、意味論的にもBodyとMindは準同型的で可換。HungryはInnocentに対する対概念として採用(無垢が侵される) ただし当人はNot Innocentであるが、ここで気をつけなければならないのはこれは意味論ではなく、意味の圏論構造を扱うのでなぜInnocentが出てきているのかを圏論的に踏まえる必要がある。言い換えれば、当人(Object)がどうであるかは別として、社会的に期待される無垢さと、一つ前の節に出てきたそれを脅かすHungryの意味対立構造(逆写像関係)によりInnocentが起用されていると判断することができるのでInnocentはそのままのベクトルで扱う。


![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/innocent-hungry.png)


結果としてbodyを対称として２つのクラスタが現れた。CakeはInnocentと同階層であり、SweetとYummyの同階層にHungry、意味論的には同クラスタにあらわれても良さそうだが別クラスタ。美味しく、甘いものに対して飢えた人物の対比が引かれ、その中心に歌われる人物の身体がある。意味論的に言えば、甘美なその体は欲をそそるというふうに解釈ができる。概念位相論として定式化すれば、Sweet → Hungry | Bodyとなる。保存構造としては魅力であり、Hungryはその魅力の反転として発現する渇きと解釈する。





### mindとbody
mind上記でmindは同型と言ったが、実際PCA上でmindを追加してもZ対称性は崩れなかった。ここからBodyはMindは準同型として機能していると言える。
※Hungryが修飾するeyesを入れないのは、このeyesはbodyの持ち主ではないためZ軸としては不採用とした

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/z=body-mind.png)

またbodyとmindは準同型であるが、意味空間構造としてはbodyがあって初めてこの関係は成り立つ　PCA上でもmindではZ対称性が保てず語彙ネットワークが崩壊する。


![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/z=mind.png)


言い換えればbodyは異なる語彙空間の媒介参照座標として効果的に機能していて、本来異なる語彙クラスターをbodyをベースに語彙空間が再配置されている。実際歌詞を読むとbodyが基底空間にあることは明白で、またword2vec上の結果にも現れたようにこれはこの歌詞のみに当てはまる局所解ではなく、英語の意味空間において普遍的にありえる意味配置である。これを踏まえれば寧ろかなりきれいに歌詞の意味空間構造が作られていることがわかる。またこの曲がなぜ有名になったのかも、この語彙ネットワークの対称性の美しさからも読める。
※データセットはこの曲が出る前なので影響はゼロ




# 結論
この曲の持つ歌詞は非常に美しい意味空間構造を形成しており、それをPCAを用いて明らかとすることができた。なぜこの曲が非常に人気を誇るのか、その一端を意味空間構造から垣間見ることができたと考えている。またCake = Bodyなども、圏論的構造によって支えられた論理的な構造であり、今まで見えなかった非論理性に潜む高度な論理構造を明るみに出すことができたと考えている。加えて冒頭、基底空間はBodyだと言いましたが、実際にPCA上でクラスタ間(fibers)をつなげている様子が見えました。これは概念位相論におけるZの可視化であり、有意義な結果が得られたと考えています。

![alt text](https://raw.githubusercontent.com/No-Name-Yet-Exist/Articles/main/conceptual-topology/resources/metaphor-sweet-cake/semantic-geometry.png)

sweetをsugarに変えると、非常美しい意味幾何学模様というべき絵が表れた。意味構造として美しく配置された語意空間はこのような性質を示すのだろうか。実際、概念位相的構造も守られている。

同階層・同クラスター (Z = sugar)
```
cake → body | sugar 甘美な体 (直接的比喩)
yummy → mind | sugar 甘く美味しいものを思う
hungry → innocent | sugar 甘美な無垢さに対する飢え/禁忌の抑制
mind → body | sugar 欲望の可能性 → 快楽の知/体験
yummy → cake | sugar 美味しいものは甘いケーキ
↑意味論的にはあり得る構図だが( A dog is Shiba: dog → Shiba//具体化)
最後だけはcake → yummy | sugar の方が因果論的には自然かもしれない
```

```python
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from gensim.models import KeyedVectors
import numpy as np


model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

words = ["body","mind","sweet","yummy","cake","innocent","hungry"]

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

plt.title("PCA of Semantic Circulation (Word2Vec)")
plt.grid(True)
plt.axis("equal")
plt.savefig("image.png") 
plt.show()

```

### 使用したWord2Vec
https://github.com/No-Name-Yet-Exist/Articles/blob/main/word2vec.md


### 参考文献
INNA, “Yummy” (2023)