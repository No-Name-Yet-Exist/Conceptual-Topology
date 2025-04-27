# 元となる理論と実証結果

以前存在や意味の発生メカニズムを連続性及びフレームZによって捕捉するモデリングを行いました。それを数理的に証明することは難しく、実証主義でのアプローチに切り替えて行いました。結果として概念空間における連続性と骨格語が数学におけるトポロジーと特異点の構造に類似する結果が見出されました。以下その内容です。
実証結果との照らし合わせ

本研究は、存在と意味の生成・維持メカニズムに関する理論的枠組みに対し、word2vecによる語彙空間の実験的観測を通じて実証的検証を行ったものである。

その結果以下のことが確認された。
意味の連続性は共起頻度と連続性によって捉えられうること
また意味は媒介変数Z（contrast frame）により維持・生成されること

さらに、元理論における未定義部分として以下が観測された。
構造的にrupture（断裂）や媒介Zの消失後も存在し続ける語群（=骨格語）数学的特異点（singularity）に類似する振る舞いを示す語彙の存在

一方で「存在」そのものについては、論理的に検出可能性（detectability）として捉えられるに留まっており、必ずしも意味の連続性と同一視できるものではない点に留意する必要がある。

解説

### 1. Δt（連続的変化・動的要素）の実装

元理論におけるΔt（対象の連続的内部的変動）は、word2vecにおいては語の出現頻度および共起頻度により統計的に代替され、語の位置（embedding）が連続的に変化・更新される仕組みとして現れている。つまり、語の持つ「変動」はそのまま「頻度的パターン」へと変換され、意味空間上に存在を生み出す条件となっている。

### 2. Z（媒介・座標軸・コントラスト枠組）の実装

また、Zに相当する媒介要素は、word2vec空間のベクトル演算により実装可能である。具体的には、PCAや概念ベクトルの選択・除去によって、語の位置や関係性を連続的かつ操作的に変形させることができる。Zは、文脈依存的な媒介だけでなく、座標軸そのものの形成やrupture（断裂）の制御として機能する点で、word2vecの操作的特性と一致する。

### 3.Semantinc Singlarity (概念空間における絶対座標軸)

骨格語はいかなるZ、Z_local, Z_globalに依存せず存在を維持し続けることが実証された。言い換えればこれらの語は自己完結的に空間上の位置を持ち、自らが存在することによって周辺の語を座標化する基準点として機能できる可能性を示している。この性質は、語概念空間における「絶対座標的概念（Semantic Singularity）」として位置づけうるものであり、意味空間における特異点的存在としての骨格語の独自性を示唆する重要な知見である。
dogとcatに関する観測と解釈

dogとcatはanimalの意味成分を抜くことでdog-catの差分ベクトルに大きく接近しました。これはanimalというlocal rupture（局所的断裂）によってその独立性が維持されていたと解釈できます。言い換えるとanimalを取り除く操作により、dogとcatの間に存在していたrupture（断裂）が解消され、結果として両者はdog-catベクトル、すなわち連続的変換の方向ベクトル（連続変換の経路）へと大きく接近したとなります。

ここで重要なのは、このdog-catベクトルが、Z=animalが存在する間は「非連続性＝断裂の指標」であったにもかかわらず、Zが除去されると「連続的変形のための経路（identity through deformation）」としてその意味を転換する点です。

これは本質的に、語概念間の非連続性（独立性）がZ（媒介語またはlocal rupture）によって保証されており、そのZが消失すると、語は本来持つ変形可能性の空間に回収され、連続的な概念へと再構成されることを示唆しています。

With Z (animal)
dog ---Local Rupture--- cat

Without Z
dog ---- Continuity Path (identity morphism) ---- cat
※dogとcatが連続

### 今後の展開

本研究では、これまでに示した存在と意味の創発モデルを基盤として、意味空間における概念力学（Conceptual Dynamics）の構築を試みます。このモデルは、語や概念の位置や関係がどのように変化し、維持され、または破断されるかを操作論的に記述するものです。すでに意味空間上におけるいくつかの法則性の存在が示唆されており、それらを含め体系的にまとめていく予定です。

ただし、このモデルは現段階では完全な厳密性を保証するものではなく、今後の実験的・理論的検証とともに、継続的な改善と修正を必要とする試論的な位置づけにあります。以下に、いくつかの基本的な操作とその例を示します。

※ "~" は同位同相（homeomorphism）を意味します。すなわち、連続的な変化や変換の先で一致・同一性が成立する状態を指します。

Physics of Rupture
状況：自己や対象が、ある強いコントラスト（+contrast）によって、それ以前と以後で位相的に非連続（≉）になる現象。

記述例：
(me ≉ me′ | +contrast: trauma) = rupture
= “I’m not who I used to be.”
(man≉man' | hospital) = rupture (生と死、存在の境界)

Physics of Metaphor or Poem
状況：異なる存在AとBが、直接のコントラスト（contrast）を欠いた状況において、連続的な変化の先に同位同相（~）として結びつく現象。

記述例：
(A ~ B | ¬contrast) ~ metaphor
Example: (grief ~ love | ¬presence) ~ a quality of poem

Local Rupture and Global Continuity （局所的断裂と全体的連続性）
状況：局所的には対象が変化し（≉）、一方で全体的・記憶的には同一性（~）が維持されている状態。

記述例：
“My father is the same father I had as a child,” but also “He’s a different person because old age changed him”
{(Father ≈ Father’ | memory ⋀ observation) ~ (Father ≉ Father’ | appearance
⋀ behavior ⋀ age)} | my father

© 2025 [No Name Yet Exist]
This repository contains original theoretical works on the emergence of existence and meaning, collectively referred to as "Conceptual Dynamics" or "Conceptual Topology". All contents are protected under copyright law.Unauthorized reproduction or redistribution without explicit permission is prohibited.