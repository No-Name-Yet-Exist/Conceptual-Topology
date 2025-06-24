# Conceptual Topology Behind BERT: A Categorical Semantics of Token and Attention

# Token and Attention
We transcribe BERT terminologies in Conceptual Topology.

**Token**
Every token has connection with other tokens. This is expressed as Yoneda's lemma as follows.
```
For any concept C
token_C ≅ Hom(-, C)
```

Token is expressed as matrix. Matrix corresponds to set in the categorical sense.
```
tokenᵢ ∈ ℝᵈ

any word can behave as a set such as red = {crimson, scarlet....}.
Or in the relatoinal sense, red = {blood, apple....}.
CT: Category V
BT: V = {w₁, w₂, ..., wₙ}

CT: Hom(tokenₖ, tokenᵢ)∈ Mor(V)
BT: T = {token₁, token₂, ..., tokenₖ} ⊆ V

CT: tokenᵢ → tokenⱼ | Z = Attention
BT: tokenⱼ = Attention(Qᵢ, Kⱼ, Vⱼ)
```

**Attention**
We interpret Z frame corresponds to Attention in BERT. Z-frame is defined as fiber or retractive mediator. This depends on the perspective, however we employ retractive mediator for current situation.

```
   A
   | \
   |  \
   v   v
   Z → B  

f: A → Z  
g: Z → B
such that
g ∘ f ≅ A → B | Z
```

The masking in BERT is expressed as follows.
```
A → ? |Z
where: ? = [MASK]

More explicitly:
A → Z
Z → ?
g ∘ f ≅ A → ? | Z

A → Z: Attention(Q,K,V)
Z → ?: softmax(QKᵀ / √d) * V
```

The categorically concise input is *A is [MASK]*. This is diagramically described simple.
```
   A
   | \
   |  \  is
   v   v
   Z → ? 


f: A → Z   
g: Z → ?  
is = g ∘ f
```

This document and all conceptual content therein are © [No Name Yet Exist], 2025. 
All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
