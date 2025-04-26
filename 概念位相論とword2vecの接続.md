ここで言っていることを一言でまとめると
word2vecは意味要素の削除と追加で再構成されているということになります

1. 概念空間の基本定義

ConceptSpace：概念は対象C∈Ob(ConceptSpace) として存在し以下のように定義できる。
C = { a1_vec, a2_vec, ..., an_vec }
それぞれが属性射ベクトル（意味射）集合を内部に持つ。
   
f⃗ : C₁ → C₂ | 属性 = (方向, 強度)

2. 射ベクトルの性質
射 f⃗:C1→C2は、単なるマッピングではなく、「意味変換の方向性と強度」を持つベクトル。
ベクトルは、抽象度軸やカテゴリ軸を含む多次元構造上に存在。

概念の変形操作は次で定義：
f_add−sub(C)=C−α⃗+Δ⃗
ここで、
α⃗ = 既存の射・属性のうち、削除されるベクトル成分
Δ⃗ = 新たに加算される意味ベクトル（新射 or 属性変換）

α=Conflict(C,Δ)
追加するベクトル Δ⃗によって干渉・削除される既存属性
結果、新たな概念 C′が形成される。

f_add−sub(queen,woman,man)=queen−woman+man = king
ここで、α⃗=Female⃗、Δ⃗=Male⃗

3. 差分操作と射ベクトル生成
Diff(C1, C2) ⇒ f_vec : C2 → C1

例：
dog − cat = {Canine⃗,Feline⃗}
Feline⃗ → Canine⃗　という射ベクトル

差分が「単なる残り」ではなく、カテゴリ間の変換射（方向ベクトル）を生むこと。
つまり、Feline⃗ → Canine⃗ という「概念変換の意味的経路」が生成される。

差異 = 共通性の消失によって対になる本質が浮かび上がる現象とも解釈可能。
 Diff(A, B) = { Pure(A), Pure(B), Transform(A↔B) }
 Pure(A) = Aに固有の本質（犬らしさ）
 Pure(B) = Bに固有の本質（猫らしさ）

 Transform(A↔B) = 両者を接続する意味的射



4. Z は概念間の「断絶（rupture）」または「連続性の座標軸」。

過去の実証結果に基づき、Zが存在する場合：
With Z :
C1 —[ Local Rupture (Z) ]—> C2

Without Z :
C1 —[ Continuity Path ]—> C2
同じベクトルでも、Zの有無でその意味論的解釈が反転する。


5. dampingとの統合
Damping(C1, C2 | Z) = | Proj_before − Proj_after |

damping値が高いほど、「Z成分が概念間に強い断絶を与えていた」と解釈。
これは「概念間張力の緩和量」＝Z除去による連続性回復度を示す指標。


6. 実証例とその解釈

queen - woman + man = king 

queen = 基本概念ノード + 属性射集合
queen = {Royalty⃗, Female⃗, Human⃗}

「− woman」は、Female⃗ の削除（= α⃗）
「+ man」は、Male⃗（= Δ⃗）の加算

結果として：
f_add−sub(queen) = Queen − Female⃗ + Male⃗
= {Royalty⃗, Human⃗, Male⃗} = king


dog − cat ≈ cat − animal

 各概念の定義（属性ベクトル集合で表現）
dog = {Animal⃗, Canine⃗, Domesticated⃗, Pet⃗}
cat = {Animal⃗, Feline⃗, Domesticated⃗, Pet⃗}

dog − cat は「dogの構造から、catとの共通属性を“打ち消す”操作」になる
共通属性 = {Animal⃗, Domesticated⃗, Pet⃗}

dog − cat = {Canine⃗,Feline⃗}
Feline⃗ → Canine⃗　という射ベクトル

Dog-animalという操作はdogの同一性を保ちながら変形可能なベクトル成分を残す処理となり、dog-animal = {Canine⃗, Domesticated⃗, Pet⃗}という射ベクトルを生成する。ここで重要なのは、この操作によってカテゴリ内での差異ベクトルが強調される点である。カテゴリ内での変換射（例：Feline⃗ → Canine⃗）の方向性に整列するのは、上記のような概念空間の持つ内在的な構造的性質によるもの。


これを噛み砕くと、共通フレーム（Animal⃗）を除去した瞬間に、カテゴリ内での差異を示すベクトル、犬らしさが強調されたことになる。しかしこの「犬らしさ」は、必然的に「猫との差異の方向」に沿うことになる。どういうことかというと、これは犬がただの固有性ではなく、猫との差異方向としての犬らしさが現れるという意味である(差異はそれ単体で発現できない。必ず対照が必要)。これを言い換えれば、概念空間には差異を配置する見えないルールが存在するとも言える。（例：Feline と Canine は、Animalの下位カテゴリとして差異ベクトルで繋がっている）したがって、dog − animal をした瞬間、Canine側に寄る差異ベクトルが発生する。結果的に、そのベクトルは「Feline⃗ → Canine⃗」の方向に揃ってしまう


骨格語に対する解釈
今の理論的な枠組みで言えばblack whiteはそれ自体が射ベクトルの関係なのか もしくは射ベクトルに入っている要素集合が多すぎて、一つ一つが影響力を持たないと読めるが実証待ち

This document and all conceptual content therein are © [No Name Yet Exist], 2025. 
All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.