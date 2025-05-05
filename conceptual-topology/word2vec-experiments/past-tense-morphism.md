動詞の意味集合を以下のように仮定し、過去形について調査を行いました。
verb = {verb, Δt}

結果としては動詞の時制変化(過去形について)は過去射が存在しており、
過去射を通じて連続的に変換が可能です。
f_t: verb ↦ verb-past ≈ verb + Δt
reach —[Δt:past morphism]→ reached

過去射の導出方法
mean([verb - verb_past])
上記のような非常に単純な計算ですが十分な精度で機能しています。


不規則活用・conjugateのような低頻度使用の動詞についても同様の傾向が確認されました


have → [('have', 0.7881007790565491), ('had', 0.7847875952720642), ('been', 0.638687014579773)]
like → [('like', 0.8058760166168213), ('liked', 0.5078374743461609), ('resembled', 0.5032988786697388)]
conjugate → [('conjugate', 0.9330419301986694), ('conjugated', 0.5791976451873779), ('subtype_selective', 0.5752800703048706)]
hold → [('hold', 0.8481835126876831), ('held', 0.7473699450492859), ('holding', 0.6816197037696838)]
see → [('see', 0.7983815670013428), ('saw', 0.7270624041557312), ('seen', 0.6300054788589478)]
walk → [('walk', 0.8874256610870361), ('walked', 0.8310598731040955), ('walking', 0.723125159740448)]
throw → [('throw', 0.9043711423873901), ('threw', 0.7848061323165894), ('throws', 0.6805372834205627)]
kick → [('kick', 0.8994205594062805), ('kicked', 0.7514143586158752), ('kicks', 0.7304542064666748)]
bring → [('bring', 0.8418816924095154), ('brought', 0.8212930560112), ('bringing', 0.6805663108825684)]
take → [('took', 0.8532754182815552), ('take', 0.8381539583206177), ('taken', 0.7338502407073975)]

```python
from gensim.models import KeyedVectors
import numpy as np

past_present_pairs = [
    ("did", "do"),
    ("jumped", "jump"),
    ("played", "play"),
    ("looked", "look"),
    ("called", "call"),
    ("talked", "talk"),
    ("opened", "open"),
    ("closed", "close"),
    ("moved", "move"),
    ("worked", "work")
]

model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

# 過去形射 Δt を構成
deltas = [model[past] - model[present] for past, present in past_present_pairs if past in model and present in model]
delta_t = np.mean(deltas, axis=0)

# テスト対象の現在形動詞
test_verbs = ["have", "like", "conjugate", "hold", "see", "walk", "throw", "kick", "bring", "take"]

for verb in test_verbs:
    if verb in model:
        shifted_vec = model[verb] + delta_t
        neighbors = model.similar_by_vector(shifted_vec, topn=3)
        print(f"{verb} → {neighbors}")
    else:
        print(f"{verb} not in model.")

```

Word2vecデータセット
https://code.google.com/archive/p/word2vec/


### スペイン語未来形でのテスト

スペイン語未来形でもテストしました。スペイン語は未来形が英語のようにwill+doではなく、単語の活用として (trabajar → trabajaré)存在するためword2vecで扱いやすいです。

結果としてはスペイン語における語用論を反映した結果が得られました。
以下で考察します。
leer → [('leer', 0.7714985013008118), ('leáis', 0.7001754641532898), ('escribiré', 0.6945518851280212)]　未来形なし

beber → [('beber', 0.8042593002319336), ('bebo', 0.7468262910842896), ('bebiere', 0.7232961654663086)]　接続法未来

amar → [('amar', 0.8477938771247864), ('amarme', 0.7441540956497192), ('amándote', 0.7179785370826721)]　未来形なし

salir → [('saldré', 0.8204919695854187), ('vendré', 0.7585237622261047), ('salgo', 0.7360261678695679)]

decir → [('diré', 0.7545633316040039), ('creeré', 0.7345491647720337), ('repito', 0.7259405851364136)]

arrojar → [('arrojar', 0.7998480200767517), ('sacaré', 0.6614207625389099), ('arrojaré', 0.6445000767707825)]　sacarがここで出てきたのは興味深いです

dejar → [('dejaré', 0.8021659851074219), ('haré', 0.7119754552841187), ('dejar', 0.7102271318435669)]

leer, beber,amarは未来形で使われにくいです。voy a leer, voy a beberの方が自然です。語の使用頻度としてそこまで高くないと推察され、未来形が語用論的に出なかったと読みます。amarはvoy a amarでも恐らくあまり使われないのではと思っています。

decir, salirは不規則活用ですが、英語同様に不規則活用についても単純な未来射で抜き出すことが出来ました。

結果として英語の過去形と比較した場合には精度は落ちたと言えますが、未来射が機能しているかと言われれば、十分機能していると判断します。

```python
from gensim.models import KeyedVectors
import numpy as np

# スペイン語現在形-未来形ペア
spanish_future_pairs = [
    ("hablar", "hablaré"),
    ("comer", "comeré"),
    ("vivir", "viviré"),
    ("trabajar", "trabajaré"),
    ("estudiar", "estudiaré"),
    ("salir", "saldré"),
    ("tener", "tendré"),
    ("venir", "vendré"),
    ("decir", "diré"),
    ("hacer", "haré")
]

model_path = ''
model = KeyedVectors.load_word2vec_format(model_path, binary=True)

# 平均差分（未来形射）を求める
deltas = [model[fut] - model[pres] for pres, fut in spanish_future_pairs if pres in model and fut in model]
delta_f = np.mean(deltas, axis=0)

# 任意の動詞に適用
test_verbs = ["leer", "beber", "amar", "salir", "decir","arrojar","dejar"]
for verb in test_verbs:
    if verb in model:
        shifted_vec = model[verb] + delta_f
        neighbors = model.similar_by_vector(shifted_vec, topn=3)
        print(f"{verb} → {neighbors}")
    else:
        print(f"{verb} not in model.")
```

スペイン語Word2Vecの典拠
Cristian Cardellino: Spanish Billion Words Corpus and Embeddings (March 2016), https://crscardellino.github.io/SBWCE/
Spanish Billion Word Corpus and Embeddings
Notes of a Computer Scientist
crscardellino.net

この記事はFair Use対象外です。
This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.