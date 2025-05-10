### Object: Yoneda' Lemma × Structralism

Let OC be an opposite concept
Object = {–OC₁, –OC₂, ..., –OCₙ}

Elemental object
A = {–B}
A = {–B} ⇔ B = {–A}
Object is always relational and oppositional

Theoretical Background:
https://github.com/No-Name-Yet-Exist/Articles/blob/main/conceptual-topology/theorems/definition-of-object-concept.md


### Morphism
f: A → B | R
f: A ≈ B | Z_local
f: A ~ B | Z_global

Z: variable which ensures the continuity 
R: rupture

Rupture = アゲハ → キアゲハ | spices
Z_local = local Continuity or Local Morphic Path: (アゲハ ≈ キアゲハ | アゲハチョウ科)
Z_global: Global Continuity or Global Morphic Path (アゲハ ~ キアゲハ | 蝶)
isomorphism アゲハ = アゲハ'

蝶 → アゲハ蝶 → spicesは、下記で示す圏構造 Ci → Ci+1 → C+2 で対応する

### Category
Ci = GenCategory()

ruptureによる構造分化によって、C₀ → C₁ → C₂ → … という圏の分化が生じる
生成関手：生成されるたびに新たな定義的構造が追加される

### Functor
F: C₀ → C₁ 　
潜在圏 → 明示圏への構造の浮上
構造浮上関手：潜在圏（非区別空間）→ 明示圏（構造空間）
rupture R によって可逆写像が破られ、圏C₀の部分圏が可視的構造として発現する

### Z
The variable which preserves the continuity
アゲハ蝶 → キアゲハ | Z = アゲハチョウ科

### rupture
The rupture of continuity
アゲハ蝶 ≉ キアゲハ | 種

### Local vs Global
Local: Local Continuity
Global: Global Continuity which includes Local Continuity

```
Let C=Category of 食べ物
Let Ob(C)⊃鯛,たい焼き
Let Zp​ragmatics:
ContextualFrame → C //語用論的対照枠をCに写す関手
Then: f: 食べ物→たい焼き∣Zp​ragmatics ∈ Mor(C)
But:∄g:鯛→たい焼き∣Zp​ragmatics
such that g∈Iso(C)→ rupture at (鯛,たい焼き) under Z
```

### morphic identity
preserved structure through deformation


### 恒等射(id)の成立条件
Let node_a be A
Let node_b be B
A = {-B} and B = {-A}
If:
∀Δt→0, ∄f∈C(A, B∣R) > θ such that f is invertible and f≅f′ under continuous homeo-transformation
Then:
μ(A):=Δt→ϵlim[∃Z:C(A_t, A_t+Δt, Z) is stable] > 0
∴ A ≈ id_A

### Semantic Additivity Principle
king - man + woman = queen
{Royalty⃗, Male⃗, Human⃗} - {Male⃗} + {Female⃗} = {Royalty⃗, Female⃗, Human⃗}

``` 
      f
    K → Q
    |     \
  r |       \ g
    ↓         \
    M' ——→ W'
        h
K = king
Q = queen
M' = man
W' = woman

r: Differential Morphism（King → Man）
g: Differential Morphism（Queen → Woman）
f: Composed Semantic Morphism g ∘ h ∘ r 
h: Differential Morphism(Man → Woman)
```

non-invertibility prinicple
f: A → B | Δ− where A and B are not void

light → black | ￢light ⇒ true
black → white | ￢light ⇒ false

This is true:
black → white | color ⇒ true


# CTL (Conceptual Topology Language)

~ : Global Homeomorphism
A ~ B (≃, quasi-iso)

≈ : Local Continuity / Local Homeomorphism
f: A ≅ B (Local isomorphism / homeomorphism)

≅: isomorphic
id_A ≈ f
アゲハ蝶 ≅ アゲハ蝶' | Z where Z = 種

=: 一致
アゲハ蝶 = アゲハ蝶 | Z where Z = perception

≉ : Local Rupture
f ∉ Iso(C), かつ ∃Z_local において構造不整合

≁: Global Rupture
f ∉ Fun(C₁ → C₂) preserving global limits/colimits

→: 不可逆射
f: A → B where no f⁻¹ exists

| : Given contrast frame — axis or observation context. You put a morphic path or rupture frame


A‘: The changed state of A
f: A → A'

¬: absence or place where ruptured
A∈Ob(C),but ∀X,Hom(X,A)≅Hom(X,B)
light → black | ￢light

//: Comment

Δt : Time-delta — deformation through temporal contrast
f: A_t → A_{t+Δt}

Δ: difference, 変化量
δ: f ↦ Δ(f) （関手/写像の自然変換間の差）


This document and all conceptual content therein are © [No Name Yet Exist], 2025. 
All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.