# 概念の基本定義

ConceptSpace：概念は対象 C∈Ob(ConceptSpace) として存在し以下のように定義できる。

C = { a1_vec, a2_vec, ..., an_vec }
それぞれが属性射ベクトル（意味射f）集合を内部に持つ意味集合
※Yoneda補論と同型

如何なる概念も以下を満たす
id_C : C → C
A is A
※これを満たさないのはvoid概念
void概念は空集合を持つ概念とする
以下id_Cの近似的証明
https://note.com/xoreaxeax/n/n4b1dc4237d9d

意味射ベクトルは次のように定義される
f⃗ : C₁ → C₂ | 属性 = (方向, 強度)

また概念は単語レベルではなく文章全体を概念一つとして扱うことが可能。

This is what I said.
Pointed Object → This (直詞射) → "what I said" → Pointed Object
(循環構造がある)

“My father is the same father I had as a child,” but also “He’s a different person because old age changed him”
{(Father ≈ Father’ | memory ⋀ observation) ~ (Father ≉ Father’ | appearance
⋀ behavior ⋀ age)} | my father

### Void概念
C_v = ∅
1. 以下に示す定義の定義よりunrapturableな概念 e.g. 知覚不可能性
　C_v := ∅ if ∀Δt→0, ∃f∈C(A,B∣R) such that f is invertiblee
2. モノイドの単位元Neutral⃗


# 意味射ベクトルの変形操作

意味射 f⃗:C1→C2は、単なるマッピングではなく、「意味変換の方向性と強度」を持つベクトル。 ベクトルは、抽象度軸やカテゴリ軸を含む多次元構造上に存在。

概念の変形操作は次で定義：
f_add−sub(C)=C−α⃗+Δ⃗
ここで、
α⃗ = 既存の射・属性のうち、削除されるベクトル成分
Δ⃗ = 新たに加算される意味ベクトル（新射 or 付加属性）

α=Conflict(C,Δ) 追加するベクトル Δ⃗によって干渉・削除される既存属性 結果、新たな概念 C′が形成される。

f_add−sub(queen,woman,man)=queen−woman+man = king ここで、α⃗=Female⃗、Δ⃗=Male⃗


# 差分操作と意味射ベクトル生成

Diff(C1, C2) ⇒ f_vec : C2 → C1
A + Δ = B

例：
dog − cat = {Canine⃗,Feline⃗}
cat +Δ = dog
{Feline⃗} + Δ = {Canine⃗}
{Feline⃗} + Δ → {Canine⃗ }
Feline⃗ → Canine⃗ という意味射ベクトル

差分が単なる残りではなく、概念間の変換射（方向ベクトル）を生むこと。 つまり、 Feline⃗ → Canine⃗ という「概念変換の意味的経路」が生成される。

差異 = 共通性の消失によって対になる本質が浮かび上がる現象とも解釈可能。

Diff(A, B) = { Pure(A), Pure(B), Transform(A↔B) }
Pure(A) = Aに固有の本質（犬らしさ）
Pure(B) = Bに固有の本質（猫らしさ）

Transform(A↔B) = 両者を接続する意味的射

以下が実際のword2vec上での適用例



# 意味加算原則（Semantic Additivity Principle）




# 意味保存の三角形

```
A − (A − B) ≈ A

            f: A → B （black → white）
    B
    ▲
   /    \
  /        \  Δ = A − B
 /           \       
δ            ↑
 \           /
  \         /
   A <── r: −Δ

```         

A：出発点の意味（例：black）
B：目的地の意味（例：white）
A − (A − B)：引いた差分を再加算して戻ってきた再構成された意味　
（＝実験的に cosim ≒ 0.8 で A に戻る）

f：通常の意味変換射
δ : 差異射: 差異抽出を行う写像
r: 復元射: 差異（反転方向）を加算して元の意味構造に戻す操作
Δ: 差分空間: 意味的には A から B を引いたときに残る構造的意味成分


# R は概念間の「断絶（rupture）」または「連続性の座標軸」


With R:
C1 —[ Local Rupture(R) ]—> C2

Without R :
C1 —[ Continuity Path ]—> C2

同じベクトルでも、Rの有無でその意味論的解釈が反転する。


# 意味素

最も小さな概念であり、対立概念の逆射(-OC)一つのみを要素として持つ意味集合。この時意味素は以下の通りに定義できる。

C₀ = {-OC}

ただし上記は理論モデルであり現実においては以下のように定義される。

C₀ = {-OC, ε } // ε は概念固有の文脈/文化／用法差

意味素は必ず同じコンテキストで使われるわけではない。片方の概念が特定の用法や含意でしか使われないことがある。それがεとなる。
意味集合の計算


# 意味集合の演算
　- 意味集合 A ∪ B = 意味融合（概念の合成）
　- 意味集合 A − B = 概念の純化 or 差異化
　
　例: king - man + woman = queen

意味集合の階層化・包含関係
　- Animal ⊃ {Dog, Cat}
　- Emotion ⊃ {Joy, Sadness}
　※仮説段階

意味集合間の射を定義することで、概念進化をモデル化
　- 例：「Stone → Tool」みたいな、意味変容の歴史パスを射で示す。
　こちらは動詞の過去形/未来形で近似的な実験データがあります。
CTL


# 結合法則成立：
 (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C) が成立
Queen = {Royalty⃗, Female⃗, Human⃗} かつ King = {Royalty⃗, Male⃗, Human⃗}のとき以下が成り立つ

Queen ⊕ ({Male⃗} ⊕ −{Female⃗}) = King
(Queen ⊕ {Male⃗}) ⊕ −{Female⃗} = King


# 単位元（Identity Element）：
Neutral⃗ = 「意味を変えない無属性集合」

X ⊕ Neutral⃗ = X anything is anything
¬X ⊕ Neutral⃗ = ¬X nothing is nothing
X ⊖ Neutral⃗ = X  "dog"
Neutral⃗ ⊕ Neutral⃗ = Neutral⃗ ""


概念位相論的に、Neutral⃗ は恒等射に近い。

恒等射 idₓ : X → X

X ⊕ Neutral⃗ ≡ idₓ(X)
¬X ⊕ Neutral⃗ ≡ id_{¬X}(¬X)

つまり、Neutral⃗ は概念空間における意味的恒等射として機能する


This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
