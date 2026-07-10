# Clôtures

* $\rightarrow^*$ = **clôture réflexive-transitive** de $\rightarrow$ (étoile de Kleene)
= plus petit préordre contenant $\rightarrow$
$u \rightarrow^* v$ ssi il existe une **réduction** (un chemin)
$$u = u_0 \rightarrow u_1 \rightarrow \dots u_{n-1} \rightarrow u_n = v, \text{ avec } n \ge 0$$

* $\rightarrow^+$ = **clôture transitive** de $\rightarrow$
= plus petite relation transitive contenant $\rightarrow$
$u \rightarrow^+ v$ ssi il existe une **réduction non vide**
$$u = u_0 \rightarrow u_1 \rightarrow \dots u_{n-1} \rightarrow u_n = v, \text{ avec } n \ge 1$$

* $\leftrightarrow^* = (\leftarrow \cup \rightarrow)^*$ est la $\beta$-équivalence (parfois notée $=_\beta$)
-