## Unidad 2: Probabilidad

### Conceptos previos

**Experimento aleatorio** ($\mathcal{E}$): Proceso cuyo resultado no se puede predecir con exactitud, pero se puede proporcionar un conjunto de todos los resultados posibles.

**Espacio muestral** ($S$): Conjunto de todos los resultados posibles de $\mathcal{E}$. Hay dos tipos:
1. **Discreto**: número finito o infinito numerable de elementos.
2. **Continuo**: intervalo continuo en $\mathbb{R}$.

**Suceso** (letras mayúsculas): Subconjunto de $S$.

### Cálculo de probabilidades

Una forma de calcular la probabilidad de un suceso es:
$$P(A) = \frac{\text{casos favorables a } A}{\text{casos posibles}}$$

> [!note] Interpretaciones de la probabilidad
> Hay tres corrientes filosóficas: **clásica** (sucesos igualmente verosímiles), **frecuencialista** ($p = fr$) y **subjetiva** (depende del sujeto). Como no hay acuerdo entre ellas, se adopta la **definición axiomática**.

### Definición Axiomática de Probabilidad

Sea $\mathcal{E}$ un experimento aleatorio y $S$ su espacio muestral asociado. Decimos que la función $P: \mathcal{F} \to \mathbb{R}$, donde $\mathcal{F}$ es una familia de subconjuntos de $S$, tal que a cada $A \in \mathcal{F}$ le asigna un $P(A)$, es una **probabilidad** si satisface los siguientes axiomas:

1. $\forall A \in \mathcal{F},\quad P(A) \geq 0$
2. $P(S) = 1$
3. Si $A_1, A_2, \dots$ es una sucesión de sucesos disjuntos tal que $\forall\, i \neq j,\ A_i \cap A_j = \emptyset$, entonces: $$P\!\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)$$

### Propiedades

1. $P(\emptyset) = 0$
2. Si $A_1, A_2, \dots, A_n$ son tales que $\forall\, i \neq j,\ A_i \cap A_j = \emptyset$: $$P\!\left(\bigcup_{i=1}^{n} A_i\right) = \sum_{i=1}^{n} P(A_i)$$
3. $\forall A \subset S,\quad P(A^c) = 1 - P(A)$
4. $\forall A \subset S,\quad 0 \leq P(A) \leq 1$
5. Si $A, B \subset S$ y $A \subset B$, entonces $P(A) \leq P(B)$
6. Si $A, B \subset S$: $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Generalización de la propiedad 6:**
$$P(A \cup B \cup C) = P(A)+P(B)+P(C) - P(A\cap B) - P(A\cap C) - P(B\cap C) + P(A\cap B\cap C)$$

**Recordar:**

$$A = (A \cap B^c) \cup (A \cap B)$$
$$(A \cup B)^c = A^c \cap B^c$$
$$(A \cap B)^c = A^c \cup B^c$$
$$A, B \text{ disjuntos} \Longleftrightarrow A \cap B = \emptyset$$

### Probabilidad condicional

Sea $A$ y $B$ sucesos en $S$ tales que $P(A) > 0$, definimos:
$$P(B \mid A) = \frac{P(B \cap A)}{P(A)}$$
Se puede probar que para un suceso $B$ fijo tal que $P(B) > 0$, $\forall A \subset S$, la función $P(A \mid B)$ es una probabilidad, o sea cumple con los axiomas de la definición de probabilidad.

1. $\forall A \in \mathcal{F},\quad P(A \mid B) \geq 0$
2. $P(S \mid B) = 1$
3. Si $A_1, A_2, \dots$ es una sucesión de sucesos disjuntos tal que $\forall\, i \neq j,\ A_i \cap A_j = \emptyset$, entonces: $$P\!\left(\bigcup_{i=1}^{\infty} A_i \,\middle|\, B\right) = \sum_{i=1}^{\infty} P(A_i \mid B)$$

### Regla del producto

Dados $\mathcal{E}$ y $S$, sean $A$ y $B$ sucesos de $S$:
$$P(A \cap B) = P(A)\,P(B \mid A) \quad \text{si } P(A) > 0$$
$$P(A \cap B) = P(B)\,P(A \mid B) \quad \text{si } P(B) > 0$$

*Generalización para $n = 3$:*
$$P(A \cap B \cap C) = P(A)\,P(B \mid A)\,P(C \mid A \cap B) \quad \text{si } P(A \cap B) > 0$$

### Independencia de sucesos

**Idea intuitiva:** la ocurrencia de un suceso no afecta la probabilidad del otro, es decir $P(B \mid A) = P(B)$. Pero esto requiere $P(A) > 0$, por lo que se generaliza con la siguiente definición.

**Definición:** Dados dos sucesos $A, B$ en $S$, decimos que $A$ y $B$ son **independientes** si y solo si:
$$P(A \cap B) = P(A)\,P(B)$$

**Generalización para $n = 3$:** Decimos que $A$, $B$ y $C$ son **mutuamente independientes** si y solo si se cumplen las cuatro condiciones:
1. $P(A \cap B) = P(A)\,P(B)$
2. $P(A \cap C) = P(A)\,P(C)$
3. $P(B \cap C) = P(B)\,P(C)$
4. $P(A \cap B \cap C) = P(A)\,P(B)\,P(C)$

> [!note] No confundir independencia con mutuamente excluyente
> - **Independencia:** $P(A \cap B) = P(A)\,P(B)$ → concepto **estadístico**
> - **Mutuamente excluyentes:** $A \cap B = \emptyset$ → concepto de **conjuntos**

