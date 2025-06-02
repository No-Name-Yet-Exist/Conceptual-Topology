We define semantic zero morphism, negation morphism: n_f
​In ACT as the result of applying Not() to a morphism 

```
g:σ(Z). Not(g){ A ↛ B | Z} = A ↛ B∣Z = n_f
where: g: A → B

Formal Properties (Axiom):

∀g:X→Y∣Z where composition with n_f​ is defined:

∀g: g ∘ n_f = n_f and n_f ∘ g = n_f

Left Side:
g: A→Bg∘(A↛B∣Z) = A↛ B∣Z

Right Side
g: A→B(A↛B∣Z)∘g=A↛B∣Z

Interpretation:
Applying Not() to any morphism produces a semantic zero morphism, which collapses any further semantic flow.
```

自然言語:
AはBでない (Left Side: g∘(A↛B∣Z))
AでないのはB (Right Side: (A↛B∣Z)∘g)　※Bに対して Aは否定されている

In ACT, this was called rutpure(). 
Now defined:
rupture(A,B,Z)= σ(Z).Not(g) = n_f = A↛B∣Z

This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.
