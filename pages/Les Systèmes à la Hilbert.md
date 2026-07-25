- md_content = """- **Définition 1.7.1** Un système de Hilbert est la donnée d'un ensemble $A$ d'axiomes et d'un ensemble $R$ de règles.
  	1. Soit $\Gamma$ un ensemble de formules. Une $\Gamma$-dérivation est une suite finie $A_{1},...,A_{n}$ de formules telle que pour tout $i\le n$, l'une des conditions suivantes est réalisée :
	- $A_{i}\in A$ ou $A_{i}\in\Gamma$.
	- $A_{i}$ est la conclusion de l'une des règles de $R$ dont les prémisses appartiennent à $\{A_{1},...,A_{i-1}\}$.
	  2. Une formule $A$ est $\Gamma$-dérivable (notation $\Gamma \vdash A$) s'il existe une $\Gamma$-dérivation qui se termine par $A$.
	  3. Une formule $A$ est un théorème (notation $\vdash A$) si elle est $\emptyset$-dérivable.
- **Définition 1.7.2** Voici un système de Hilbert usuel :
	- **Axiomes**
		- $H_{1} : A\rightarrow B\rightarrow A$
		- $H_{2} : (A\rightarrow B\rightarrow C)\rightarrow(A\rightarrow B)\rightarrow(A\rightarrow C)$
		- $H_{3} : A\wedge B\rightarrow A$
		- $H_{4} : A\wedge B\rightarrow B$
		- $H_{5} : A\rightarrow B\rightarrow A\wedge B$
		- $H_{6} : A\rightarrow A\vee B$
		- $H_{7} : B\rightarrow A\vee B$
		- $H_{8} : (A\rightarrow C)\rightarrow(B\rightarrow C)\rightarrow(A\vee B)\rightarrow C$
		- $H_{9} : \neg A\leftrightarrow(A\rightarrow\perp)$
		- $H_{10} : \perp\rightarrow A$
		- $H_{11} : A\vee\neg A$
		- $H_{12} : A[x:=t]\rightarrow\exists x~A[x]\quad(*)$
		- $H_{13} : \forall x~A[x]\rightarrow A[x:=t]\quad(*)$
	- **Règles**
		- $(R_{1}) \frac{A~A\rightarrow B}{B}$
		- $(R_{2}) \frac{C\rightarrow A[x]}{C\rightarrow\forall x~A[x]}\quad(**)$
		- $(R_{3}) \frac{A[x]\rightarrow C}{\exists x~A[x]\rightarrow C}\quad(**)$
	- $(*)$ $t$ est un terme du langage.
	- $(**)$ $x$ n'a pas d'occurrence libre dans $C$ et dans les formules qui précèdent l'application de la règle.
	  """