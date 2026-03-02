### Conceptos

**Experimento aleatorio** ($\mathcal{E}$): Proceso cuyo resultado no se puede predecir con exactitud pero se puede proporcionar un conjunto de todos los resultados posibles.
**espacio muestral** (S): Es el conjunto de todos los resultados posibles. Hay 2 tipos.
1. Discreto: numero finito o infinito numerable de elementos.
2. continuo: intervalo continuo en $\mathbb{R}$.
**Suceso** (letras mayúsculas): Subconjunto de S.
### Calculo de probabilidades

Una forma de calcular la probabilidad de un suceso es:
$$P(A)=\frac{casos\,favorables\,a\,A}{Casos\,posibles}$$
### Definición Axiomática de probabilidad
Sea $\mathcal{E}$ un experimento aleatorio y $S$ su espacio muestral asociado. Decimos que la función $P: \mathcal{F} \to \mathbb{R}$ donde $\mathcal{F}$ es una familia de subconjuntos de $S$, tal que a cada $A \in \mathcal{F}$ le asigna un $P(A)$, es una probabilidad si se satisfacen los siguientes axiomas:
1. $\forall A \in \mathcal{F}\; P(A)\geq 0$
2. $P(S)=1$
3. Si $A_1, A_2,...$ es una sucesión de sucesos disjuntos, tal que $\forall\, i\neq j \, A_i \cap A_j = \emptyset$ entonces 
$$P \left( \bigcup_{i=1}^{\infty} A_i \right) = \sum_{i=1}^{\infty} P(A_i)$$
### Propiedades
1. $\quad P(\emptyset)=0$
2. $\quad \text{Si } A_1,A_2,\dots,A_n \text{ son tales que } \forall i\neq j,\; A_i\cap A_j=\emptyset,$
$$\qquad P\!\left(\bigcup_{i=1}^n A_i\right)=\sum_{i=1}^n P(A_i)$$
3. $\quad \forall A\subset S,\; P(A^c)=1-P(A)$
4. $\quad \forall A\subset S,\; 0\le P(A)\le 1$
5. $\quad \text{Si } A,B\subset S \text{ y } A\subset B,\; \text{entonces } P(A)\le P(B)$
6. $\quad \text{Si } A,B\subset S,\; P(A\cup B)=P(A)+P(B)-P(A\cap B)$

Generalización de la propiedad 6:

Si $A,B,C\subset S,$ entonces
$P(A\cup B\cup C) = P(A)+P(B)+P(C) - P(A\cap B) - P(A\cap C)- P(B\cap C)+ P(A\cap B\cap C)$

Recordemos que:

$A = (A\cap B^c)\;\cup\;(A\cap B)$
$(A\cup B)^c = A^c \cap B^c$
$(A\cap B)^c = A^c \cup B^c$
$A,B$ disjuntos (o mutuamente excluyentes) $\Longleftrightarrow  A\cap B=\emptyset$

### Probabilidad condicional

Sea A y B sucesos en S tales que $P(A)> 0$ definimos:
$$P(B/A) = \frac{P(B\cap A)}{P(A)}$$
*Se puede probar que para un suceso B fijo tal que* $P(B) > 0, \forall A \subset S$ *la función P(A/B) es una probabilidad o sea cumple con los axiomas de la definición de probabilidad*

1. $\forall A \in \mathcal{F}\; P(A\mid B)\geq 0$

2. $P(S\mid B)=1$

3. Si $A_1, A_2, \dots$ es una sucesión de sucesos disjuntos, tal que $\forall\, i\neq j \; A_i \cap A_j = \emptyset$, entonces

$$
P\left( \bigcup_{i=1}^{\infty} A_i \,\middle|\, B \right)
=
\sum_{i=1}^{\infty} P(A_i \mid B)
$$
### Regla del producto

Dados $\mathcal{E}$ y $S$, sean $A$ y $B$ sucesos de $S$, entonces
$$
P(A \cap B) = P(A)\,P(B \mid A)
\quad \text{si } P(A)>0
$$
o bien
$$
P(A \cap B) = P(B)\,P(A \mid B)
\quad \text{si } P(B)>0
$$
*Este teorema se puede generalizar a $n$ sucesos, por ejemplo para $n=3$:
$$
P(A \cap B \cap C)
=
P(A)\,P(B \mid A)\,P(C \mid A \cap B)
\quad \text{si } P(A \cap B)>0
$$
### Independencia de sucesos
### Sucesos independientes
Dados dos suceso $A,B$ en $S$, decimos que $A$ y $B$ son independientes si y solo si
$$P(A\cap B) = P(A)P(B)$$
### Generalización de independencia de sucesos (n=3)
Dados $\mathcal{E}$ y $S$, sean $A$, $B$ y $C$ sucesos de $S$. 
Decimos que $A$, $B$ y $C$ son mutuamente independientes si y sólo si:

1. $P(A \cap B) = P(A)\,P(B)$
2. $P(A \cap C) = P(A)\,P(C)$
3. $P(B \cap C) = P(B)\,P(C)$
4. $P(A \cap B \cap C) = P(A)\,P(B)\,P(C)$

<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 15px; display: inline-block; text-align: left;">
    <p>• <strong>Independencia</strong> es &nbsp;&nbsp;&nbsp; P(AB) = P(A)P(B) &nbsp;&nbsp;&nbsp;&nbsp; concepto estadístico</p>
    <p>• <strong>Mutuamente excluyente</strong> es &nbsp;&nbsp;&nbsp; P(A∩B) = ∅ &nbsp;&nbsp;&nbsp;&nbsp; concepto de conjuntos</p>
  </div>
</div>
