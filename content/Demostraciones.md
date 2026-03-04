## Unidad 1 - Estadística Descriptiva

### Propiedad: La media equilibra los desvíos

$$\sum_{i=1}^{n} (x_i - \bar{x}) = 0$$

Partimos de la expresión original y distribuimos la sumatoria: $$\sum_{i=1}^{n} (x_i - \bar{x}) = \sum_{i=1}^{n} x_i - \sum_{i=1}^{n} \bar{x}$$

Sabemos por definición que la media muestral es $\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i$. Despejando la sumatoria: $$\sum_{i=1}^{n} x_i = n \cdot \bar{x}$$

Por otro lado, sumar una constante $\bar{x}$ n veces es igual a multiplicarla por n: $$n \cdot \bar{x} - n \cdot \bar{x} = 0$$

## Unidad 2 - Probabilidad

### Propiedad 2: Aditividad finita

Sea $S$ y $A_1, A_2, \dots, A_n$ tales que $\forall, i \neq j \quad A_i \cap A_j = \emptyset$.

Sea $A_{n+1} = A_{n+2} = \dots = \emptyset$

Entonces $\forall, i \neq j \quad A_i \cap A_j = \emptyset$

Luego por Axioma iii) se tiene que: $$P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)$$

Entonces: $$P\left(\bigcup_{i=1}^{n} A_i\right) = P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i) = \sum_{i=1}^{n} P(A_i)$$

### Propiedad 3: Probabilidad del complemento

$$\forall A \subset S, \quad P(A^c) = 1 - P(A)$$

Sabemos que el espacio muestral se puede escribir como la unión de un suceso y su complemento: $S = A \cup A^c$.

Por definición, $A$ y $A^c$ son disjuntos (mutuamente excluyentes): $A \cap A^c = \emptyset$.

Aplicando el Axioma 3 (aditividad para sucesos disjuntos): $P(S) = P(A) + P(A^c)$.

Por el Axioma 2, sabemos que $P(S) = 1$.

Sustituyendo: $1 = P(A) + P(A^c)$.

Despejando: $P(A^c) = 1 - P(A)$.

### Propiedad 4: Acotación de la probabilidad

$$\forall A \subset S, \quad 0 \leq P(A) \leq 1$$

$P(A) \geq 0$ por Axioma 1.

$S = A \cup A^c$

$P(S) = P(A) + P(A^c)$ por Axioma 3.

$P(S) = 1$ por Axioma 2.

Sustituyendo: $1 = P(A) + P(A^c)$.

Despejando: $P(A^c) = 1 - P(A)$.

Como $P(A^c) \geq 0$ por Axioma 1, si a la unidad le restamos un valor mayor o igual a cero, el resultado tiene que ser menor o igual a 1. Por lo tanto: $P(A) \leq 1$.

### Propiedad 5: Monotonía

$$\forall A, B \subset S ; \text{y} ; A \subset B, \quad P(A) \leq P(B)$$

$A \subset B \Rightarrow B = A \cup (B \cap A^c)$

Por construcción, $A$ y $(B \cap A^c)$ son disjuntos, ya que $A \cap (B \cap A^c) = \emptyset$.

Como son disjuntos, aplicamos el Axioma 3: $$P(B) = P(A) + P(B \cap A^c)$$

$P(B \cap A^c) \geq 0$ por Axioma 1.

Entonces $P(A) \leq P(B)$.

### Propiedad 6: Regla de la suma

$$\forall A, B \subset S, \quad P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

$A \cup B = A \cup (B \cap A^c)$

Como $A$ y $A^c \cap B$ son disjuntos por definición, aplicamos el Axioma 3: $$P(A \cup B) = P(A) + P(B \cap A^c)$$

Ahora hacemos lo mismo pero solo para el conjunto $B$: $$B = (A \cap B) \cup (B \cap A^c)$$ $$P(B) = P(A \cap B) + P(B \cap A^c) \quad \text{por Axioma 3}$$

Despejamos $P(B \cap A^c)$: $$P(B \cap A^c) = P(B) - P(A \cap B)$$

Reemplazamos: $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

## Unidad 3 - Variables Aleatorias

### Propiedad 1: La FDA es no decreciente

Si $x_1 \leq x_2 \rightarrow F_X(x_1) \leq F_X(x_2)$

Sea el suceso $A = {X \leq x_1}$ y el suceso $B = {X \leq x_2}$. Como $x_1 \leq x_2$, tenemos que $A \subset B$ y por la propiedad de monotonía $P(A) \leq P(B)$, entonces: $$F_X(x_1) \leq F_X(x_2)$$

### Propiedad 3: Probabilidad en un intervalo mediante la FDA

$$\forall, a, b \in \mathbb{R}, ; a < b, \quad P(a < X \leq b) = F_X(b) - F_X(a)$$

La FDA se define como: $$F_X(x) = \int_{-\infty}^{x} f_X(t),dt$$

La probabilidad de que la variable caiga en un intervalo $(a, b]$ es: $$P(a < X \leq b) = \int_{a}^{b} f_X(t),dt$$

Por propiedad de integrales: $$\int_{-\infty}^{b} f_X(t),dt = \int_{-\infty}^{a} f_X(t),dt + \int_{a}^{b} f_X(t),dt$$

Entonces: $$\int_{a}^{b} f_X(t),dt = \int_{-\infty}^{b} f_X(t),dt - \int_{-\infty}^{a} f_X(t),dt$$

Por definición: $$P(a < X \leq b) = F_X(b) - F_X(a)$$

## Unidad 4 - Distribuciones

### Distribución de Bernoulli

Una variable aleatoria $X$ tiene distribución de Bernoulli si solo tiene dos resultados posibles: éxito (1) con probabilidad $p$, o fracaso (0) con probabilidad $1 - p$.

#### Es función de masa

Para que sea función de masa, la suma de todas las probabilidades sobre su rango $R_X = {0, 1}$ debe ser igual a 1. $$\sum_{x \in R_X} p_X(x) = p_X(0) + p_X(1)$$

Sustituimos por definición: $$(1 - p) + p = 1 - p + p = 1$$

#### Esperanza y varianza

**Esperanza** $E[X] = p$: $$E[X] = \sum x , p_X(x) = 0 \cdot p_X(0) + 1 \cdot p_X(1) = 0 \cdot (1 - p) + 1 \cdot p = p$$

**Varianza** $V(X) = p(1 - p)$:

Usamos $V(X) = E[X^2] - (E[X])^2$. Primero calculamos $E[X^2]$: $$E[X^2] = \sum x^2 , p_X(x) = 0 \cdot (1 - p) + 1 \cdot p = p$$

Ahora restamos: $$V(X) = p - p^2 = p(1 - p)$$

### Distribución Uniforme

#### La integral de la densidad es 1

$$\int_{a}^{b} f_X(x),dx = 1$$

Por definición $f_X(x) = \frac{1}{b - a}$ para $a \leq x \leq b$. Entonces: $$\int_{a}^{b} \frac{1}{b - a},dx = \frac{1}{b - a} \int_{a}^{b} dx = \frac{1}{b - a}[x]_{a}^{b} = \frac{1}{b - a}(b - a) = 1$$

#### Esperanza y varianza

**Esperanza** $E[X] = \frac{a + b}{2}$: $$E[X] = \int_{a}^{b} x \cdot \frac{1}{b - a},dx = \frac{1}{b - a} \left[\frac{x^2}{2}\right]_{a}^{b} = \frac{1}{b - a} \cdot \frac{b^2 - a^2}{2} = \frac{(a + b)(b - a)}{2(b - a)} = \frac{a + b}{2}$$

**Varianza** $V(X) = \frac{(b - a)^2}{12}$:

Usamos $V(X) = E[X^2] - (E[X])^2$. Primero hallamos $E[X^2]$: $$E[X^2] = \int_{a}^{b} x^2 \cdot \frac{1}{b - a},dx = \frac{1}{b - a} \left[\frac{x^3}{3}\right]_{a}^{b} = \frac{b^3 - a^3}{3(b - a)} = \frac{a^2 + ab + b^2}{3}$$

Entonces: $$V(X) = \frac{a^2 + ab + b^2}{3} - \left(\frac{a + b}{2}\right)^2 = \frac{4(a^2 + ab + b^2) - 3(a + b)^2}{12} = \frac{(b - a)^2}{12}$$

### Distribución Normal Estándar

Si $X \sim N(\mu, \sigma)$ entonces $Z = \frac{X - \mu}{\sigma} \sim N(0, 1)$.

#### Esperanza $E[Z] = 0$

Usamos linealidad de la esperanza: $$E[Z] = E\left[\frac{X - \mu}{\sigma}\right] = \frac{1}{\sigma}(E[X] - \mu)$$

Como $E[X] = \mu$: $$E[Z] = \frac{1}{\sigma}(\mu - \mu) = 0$$

#### Varianza $V(Z) = 1$

Usamos que $V(aX + b) = a^2 V(X)$: $$V(Z) = V\left(\frac{1}{\sigma}X - \frac{\mu}{\sigma}\right) = \frac{1}{\sigma^2} V(X)$$

Como $V(X) = \sigma^2$: $$V(Z) = \frac{1}{\sigma^2} \cdot \sigma^2 = 1$$

## Unidad 5 - Variables Aleatorias Bidimensionales

### Covarianza: forma alternativa

$$\text{Cov}(X, Y) = E(XY) - E(X),E(Y)$$

Partimos de la definición: $$\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]$$

Expandimos: $$= E[XY - X\mu_Y - \mu_X Y + \mu_X \mu_Y]$$

Por linealidad de la esperanza: $$= E[XY] - E[X\mu_Y] - E[\mu_X Y] + E[\mu_X \mu_Y]$$

Donde:

- $E[X\mu_Y] = \mu_Y E[X] = \mu_Y \mu_X$
- $E[\mu_X Y] = \mu_X E[Y] = \mu_X \mu_Y$
- $E[\mu_X \mu_Y] = \mu_X \mu_Y$ (la esperanza de una constante es la misma constante)

Entonces: $$\text{Cov}(X, Y) = E[XY] - \mu_X \mu_Y - \mu_X \mu_Y + \mu_X \mu_Y = E[XY] - E[X],E[Y]$$

### Propiedad: Covarianza con transformación lineal

$$\text{Cov}(aX + b,; cY + d) = ac,\text{Cov}(X, Y)$$

Definimos $U = aX + b$ y $V = cY + d$. Sus esperanzas son $E[U] = aE[X] + b$ y $E[V] = cE[Y] + d$.

$$U - E[U] = (aX + b) - (aE[X] + b) = a(X - E[X])$$ $$V - E[V] = (cY + d) - (cE[Y] + d) = c(Y - E[Y])$$

Sustituimos en la definición: $$\text{Cov}(U, V) = E[a(X - E[X]) \cdot c(Y - E[Y])]$$

Como $a$ y $c$ son constantes, salen de la esperanza: $$= ac,E[(X - E[X])(Y - E[Y])] = ac,\text{Cov}(X, Y)$$

### Propiedad: Aditividad de la covarianza

$$\text{Cov}(X + Y,; Z) = \text{Cov}(X, Z) + \text{Cov}(Y, Z)$$

Usando $\text{Cov}(U, V) = E[UV] - E[U]E[V]$: $$\text{Cov}(X + Y, Z) = E[(X + Y)Z] - E[X + Y],E[Z]$$ $$= (E[XZ] + E[YZ]) - (E[X] + E[Y]),E[Z]$$

Reagrupamos: $$= (E[XZ] - E[X]E[Z]) + (E[YZ] - E[Y]E[Z])$$ $$= \text{Cov}(X, Z) + \text{Cov}(Y, Z)$$

### Propiedad: Independencia implica covarianza nula

Si $X$ e $Y$ son independientes $\Rightarrow \text{Cov}(X, Y) = 0$

Si $X$ e $Y$ son independientes, se cumple que $E[XY] = E[X],E[Y]$.

Como $\text{Cov}(X, Y) = E[XY] - E[X],E[Y]$: $$\text{Cov}(X, Y) = E[X],E[Y] - E[X],E[Y] = 0$$

## Unidad 6 - Simulación

### Teorema de la transformación integral

Sea $X$ v.a. continua con FDA $F_X$, $\forall x \in R_X$, $f_X(x) > 0$. Si definimos la variable aleatoria $U = F_X(X)$, entonces **U tiene distribución Uniforme en [0, 1]**.

**Demostración:**

Sea $u < 0$: $\quad F_U(u) = P(U \leq u) = P(F_X(X) \leq u) = 0$ por ser $F_X(x)$ una probabilidad.

Sea $0 \leq u < 1$: $\quad F_U(u) = P(U \leq u) = P(F_X(X) \leq u) = P(X \leq F_X^{-1}(u)) = F_X(F_X^{-1}(u)) = u$

Sea $u \geq 1$: $\quad F_U(u) = P(U \leq u) = P(F_X(X) \leq u) = 1$ por ser $F_X(X)$ una probabilidad.

Derivando obtenemos:

$$f_U(u) = \begin{cases} 1 & 0 \leq u \leq 1 \ 0 & \text{en otro caso} \end{cases}$$

Con lo que podemos concluir que $U \sim U[0, 1]$.

## Unidad 9 - Regresión Lineal

### Los estimadores por Mínimos Cuadrados son insesgados

#### Insesgadez de $\hat{\beta}$ (pendiente)

$$E(\hat{\beta}) = E\left(\frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{\sum(x_i - \bar{x})^2}\right) = E\left(\frac{\sum(x_i - \bar{x})y_i - \bar{y}\sum(x_i - \bar{x})}{\sum(x_i - \bar{x})^2}\right) = \frac{\sum(x_i - \bar{x})E(y_i)}{\sum(x_i - \bar{x})^2}$$

Como $E(y_i) = \alpha + \beta x_i$: $$= \frac{\sum(x_i - \bar{x})(\alpha + \beta x_i)}{\sum(x_i - \bar{x})^2} = \frac{\alpha\sum(x_i - \bar{x}) + \beta\sum(x_i - \bar{x})x_i}{\sum(x_i - \bar{x})^2}$$

Recordando que $\sum(x_i - \bar{x}) = 0$ y que $\sum(x_i - \bar{x})x_i = \sum(x_i - \bar{x})^2$: $$= \beta \cdot \frac{\sum(x_i - \bar{x})^2}{\sum(x_i - \bar{x})^2} = \beta$$

#### Insesgadez de $\hat{\alpha}$ (ordenada)

$$E(\hat{\alpha}) = E(\bar{y} - \hat{\beta}\bar{x}) = E\left(\frac{\sum y_i}{n} - \hat{\beta}\frac{\sum x_i}{n}\right) = E\left(\frac{1}{n}\sum(y_i - \hat{\beta}x_i)\right)$$

Como $y_i = \alpha + \beta x_i + \varepsilon_i$: $$= E\left(\frac{1}{n}\sum(\alpha + \beta x_i + \varepsilon_i - \hat{\beta}x_i)\right) = E\left(\frac{1}{n}\sum(\alpha + (\beta - \hat{\beta})x_i + \varepsilon_i)\right)$$

$$= \frac{1}{n}\sum(\alpha + E(\beta - \hat{\beta})x_i) = \frac{1}{n} \cdot n\alpha = \alpha$$