### Variable aleatoria
Sea $\mathcal{E}$ un experimento aleatorio y $S$ su espacio muestral asociado. Una variable aleatoria es una función que asigna a cada elemento $s$ de $S$ un número real $X(s)$. Es decir:
$$X: S \to \mathbb{R}$$
*El conjunto de todos los valores posibles de X se llama recorrido de la variable X, se denota con $R_X$.*

La **probabilidad inducida** es la probabilidad sobre el nuevo espacio muestral $R_X$. Ejemplo: $P(X = 1) = 0.4$

#### Variable aleatoria discreta
Cuando el recorrido es finito o infinito numerable ($R_X = \{x_1, x_2, \dots, x_n\}$ o $R_X = \{x_1, x_2, \dots\}$), donde a cada $x_i$ se le asocia una probabilidad $p_X(x_i) = P(X = x_i)$ para $i = 1, 2, \dots$ y cumple:
1. $p_X(x_i) \geq 0$
2. $\sum_{x_i} p_X(x_i) = 1$

*Esta función se llama **función de masa de probabilidad** o f.m.p.*

Ejemplo:

<div align="center">
  <table>
    <thead>
      <tr><th>x</th><th>p_X(x)</th></tr>
    </thead>
    <tbody>
      <tr><td><strong>0</strong></td><td>10/28</td></tr>
      <tr><td><strong>1</strong></td><td>15/28</td></tr>
      <tr><td><strong>2</strong></td><td>3/28</td></tr>
      <tr><td></td><td><strong>1</strong></td></tr>
    </tbody>
  </table>
</div>

<div align="center">
<svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX1" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY1" markerWidth="10" markerHeight="7" refX="0" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>
  <line x1="40" y1="160" x2="260" y2="160" stroke="black" stroke-width="2" marker-end="url(#arrX1)"/>
  <line x1="40" y1="170" x2="40" y2="20" stroke="black" stroke-width="2" marker-end="url(#arrY1)"/>
  <text x="30" y="50" text-anchor="end" font-size="11">p(x)</text>
  <!-- Barras: 10/28≈0.357, 15/28≈0.535, 3/28≈0.107. Max=0.535, escala: 120px=0.535 -->
  <line x1="90"  y1="160" x2="90"  y2="80"  stroke="#4a90d9" stroke-width="10"/>
  <line x1="150" y1="160" x2="150" y2="40"  stroke="#4a90d9" stroke-width="10"/>
  <line x1="210" y1="160" x2="210" y2="140" stroke="#4a90d9" stroke-width="10"/>
  <!-- Etiquetas valores -->
  <text x="90"  y="75"  text-anchor="middle" font-size="10">10/28</text>
  <text x="150" y="35"  text-anchor="middle" font-size="10">15/28</text>
  <text x="210" y="135" text-anchor="middle" font-size="10">3/28</text>
  <!-- Labels eje X -->
  <text x="90"  y="177" text-anchor="middle" font-size="13">0</text>
  <text x="150" y="177" text-anchor="middle" font-size="13">1</text>
  <text x="210" y="177" text-anchor="middle" font-size="13">2</text>
</svg>
</div>

#### Variable aleatoria continua
Cuando existe una función $f_X$ no negativa, definida sobre la recta real, tal que para cualquier intervalo $A$:
$$P(X \in A) = \int_A f_X(x)\,dx$$

*$f_X$ se denomina **función de densidad de probabilidad** o f.d.p. y cumple:*
1. $f_X(x) \geq 0$
2. $\int_{-\infty}^{\infty} f_X(x)\,dx = 1$

Ejemplo:
$$f_X(x) = \begin{cases} 1/2 & 0 \leq x \leq 2 \\ 0 & \text{en otro caso} \end{cases}$$

<div align="center">
<svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX2" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY2" markerWidth="10" markerHeight="7" refX="0" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>
  <line x1="40" y1="160" x2="260" y2="160" stroke="black" stroke-width="2" marker-end="url(#arrX2)"/>
  <line x1="40" y1="170" x2="40" y2="20"  stroke="black" stroke-width="2" marker-end="url(#arrY2)"/>
  <rect x="40" y="80" width="160" height="80" fill="#7bafd4" opacity="0.6" stroke="#2980b9" stroke-width="1.5"/>
  <text x="40"  y="175" text-anchor="middle" font-size="13">0</text>
  <text x="120" y="175" text-anchor="middle" font-size="13">1</text>
  <text x="200" y="175" text-anchor="middle" font-size="13">2</text>
  <text x="30"  y="84"  text-anchor="end"    font-size="13">1/2</text>
  <text x="210" y="70"  font-size="12">área = 1</text>
  <line x1="205" y1="72" x2="160" y2="90" stroke="black" stroke-width="1"/>
</svg>
</div>

- *La f.d.p. no es una probabilidad, es una herramienta para calcular probabilidades.*
- *En el caso de una v.a. continua, la probabilidad en un punto es 0.*

### Función de distribución acumulada (f.d.a.)
$$\forall x \in \mathbb{R} \qquad F_X(x) = P(X \leq x)$$
Es la probabilidad acumulada desde $-\infty$ hasta el punto $x$.

#### Caso discreto
Sea $X$ v.a. discreta, $p_X$ su f.m.p:
$$\forall x \in \mathbb{R} \qquad F_X(x) = \sum_{x_j \leq x} p_X(x_j)$$

*Da un salto en cada punto del recorrido igual a la probabilidad de dicho punto.*

<div align="center">
<svg width="300" height="240" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX3" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY3" markerWidth="10" markerHeight="7" refX="0" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>
  <line x1="60" y1="200" x2="270" y2="200" stroke="black" stroke-width="2" marker-end="url(#arrX3)"/>
  <line x1="60" y1="200" x2="60" y2="30"  stroke="black" stroke-width="2" marker-end="url(#arrY3)"/>
  <text x="45" y="165" text-anchor="end" font-size="11">10/28</text>
  <text x="45" y="115" text-anchor="end" font-size="11">25/28</text>
  <text x="45" y="65"  text-anchor="end" font-size="11">1</text>
  <text x="45" y="45"  text-anchor="end" font-size="11">F(x)</text>
  <text x="60"  y="218" text-anchor="middle" font-size="13">0</text>
  <text x="130" y="218" text-anchor="middle" font-size="13">1</text>
  <text x="200" y="218" text-anchor="middle" font-size="13">2</text>
  <text x="260" y="218" text-anchor="middle" font-size="13">x</text>
  <!-- Segmentos escalera -->
  <line x1="20"  y1="200" x2="60"  y2="200" stroke="#2980b9" stroke-width="2.5"/>
  <line x1="60"  y1="160" x2="130" y2="160" stroke="#2980b9" stroke-width="2.5"/>
  <line x1="130" y1="110" x2="200" y2="110" stroke="#2980b9" stroke-width="2.5"/>
  <line x1="200" y1="60"  x2="265" y2="60"  stroke="#2980b9" stroke-width="2.5"/>
  <!-- Círculos abiertos -->
  <circle cx="60"  cy="200" r="4" fill="white" stroke="#2980b9" stroke-width="2"/>
  <circle cx="130" cy="160" r="4" fill="white" stroke="#2980b9" stroke-width="2"/>
  <circle cx="200" cy="110" r="4" fill="white" stroke="#2980b9" stroke-width="2"/>
  <!-- Círculos cerrados -->
  <circle cx="60"  cy="160" r="4" fill="#2980b9"/>
  <circle cx="130" cy="110" r="4" fill="#2980b9"/>
  <circle cx="200" cy="60"  r="4" fill="#2980b9"/>
</svg>
</div>

#### Caso continuo
Sea $X$ v.a. continua, $f_X$ su f.d.p:
$$\forall x \in \mathbb{R} \qquad F_X(x) = \int_{-\infty}^{x} f_X(t)\, dt$$

Ejemplo para $f_X(x) = 1/2$ en $[0,2]$:

<div align="center">
<svg width="320" height="230" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX4" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY4" markerWidth="10" markerHeight="7" refX="0" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>
  <line x1="60" y1="180" x2="300" y2="180" stroke="black" stroke-width="2" marker-end="url(#arrX4)"/>
  <line x1="60" y1="190" x2="60" y2="20"  stroke="black" stroke-width="2" marker-end="url(#arrY4)"/>
  <text x="50" y="90"  text-anchor="end" font-size="13">1</text>
  <text x="45" y="30"  text-anchor="end" font-size="11">F(x)</text>
  <text x="60"  y="198" text-anchor="middle" font-size="13">0</text>
  <text x="140" y="198" text-anchor="middle" font-size="13">1</text>
  <text x="220" y="198" text-anchor="middle" font-size="13">2</text>
  <text x="295" y="198" text-anchor="middle" font-size="13">x</text>
  <line x1="76"  y1="176" x2="76"  y2="184" stroke="black" stroke-width="1.5"/>
  <line x1="56"  y1="90"  x2="64"  y2="90"  stroke="black" stroke-width="1.5"/>
  <!-- Segmento y=0 antes de 0 -->
  <line x1="10"  y1="180" x2="60"  y2="180" stroke="#2980b9" stroke-width="2.5"/>
  <!-- Diagonal de 0 a 2 -->
  <line x1="60"  y1="180" x2="220" y2="90"  stroke="#2980b9" stroke-width="2.5"/>
  <!-- Segmento y=1 después de 2 -->
  <line x1="220" y1="90"  x2="295" y2="90"  stroke="#2980b9" stroke-width="2.5"/>
</svg>
</div>

*Bajo algunas condiciones se cumple que $F'_X(x) = f_X(x)$.*

#### Propiedades de la f.d.a.
1. $F_X$ es no decreciente: si $x_1 \leq x_2 \Rightarrow F_X(x_1) \leq F_X(x_2)$
2. $\lim_{x \to \infty} F_X(x) = 1 \qquad \lim_{x \to -\infty} F_X(x) = 0$
3. Para todo $a < b$: $\quad P(a < X \leq b) = F_X(b) - F_X(a)$

En el caso continuo todos los extremos son equivalentes:
$$P(a < X \leq b) = P(a \leq X < b) = P(a < X < b) = P(a \leq X \leq b) = F_X(b) - F_X(a)$$

<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 15px; display: inline-block; text-align: left; max-width: 500px;">
    <p>La <strong>f.m.p.</strong> (discreta), la <strong>f.d.p.</strong> (continua) y la <strong>f.d.a.</strong> (discreta o continua) son formas equivalentes de especificar la distribución de probabilidad de una variable aleatoria.</p>
  </div>
</div>

### Transformación de variables aleatorias
Sea $X$ una v.a. con distribución de probabilidad conocida, entonces $Y = g(X)$ también es una v.a.

#### Caso discreto
Si $X$ es v.a. discreta entonces $Y = g(X)$ también es discreta.
Sean $R_X = \{x_1, x_2, \dots, x_n\}$ y $R_Y = \{y_1, y_2, \dots, y_m\}$ los recorridos de $X$ e $Y$.
Sea $y_i \in R_Y$:
$$p_Y(y_i) = P(Y = y_i) = P\{x \in R_X : g(x) = y_i\} = \sum_{x \in R_X:\, g(x) = y_i} p_X(x)$$

#### Caso continuo → discreto
Si $X$ es v.a. continua, $Y = g(X)$ puede resultar discreta. Se obtiene $R_Y$ y se calcula $P(Y = y_i)$ directamente integrando $f_X$ sobre el conjunto $\{x : g(x) = y_i\}$.

#### Caso continuo → continuo
Si $X$ es v.a. continua, $Y = g(X)$ es continua. Se determina la f.d.p. de $Y$ a partir de la de $X$.

Procedimiento para $g$ **monótona creciente**:
1. Representar gráficamente $Y = g(X)$.
2. Obtener $R_Y$.
3. Obtener la f.d.a. de $Y$:
$$F_Y(y) = P(Y \leq y) = P(g(X) \leq y) = P(X \leq g^{-1}(y)) = F_X(g^{-1}(y))$$
$$F_Y(y) = \begin{cases} 0 & y < \cdots \\ F_X(g^{-1}(y)) & \cdots \leq y < \cdots \\ 1 & y \geq \cdots \end{cases}$$
4. Derivar $F_Y$ respecto de $y$ para obtener $f_Y$.

*Para $g$ monótona decreciente el procedimiento es análogo pero cambia el sentido de la desigualdad en el paso 3: $P(g(X) \leq y) = P(X \geq g^{-1}(y)) = 1 - F_X(g^{-1}(y))$.*

### Características de las variables aleatorias
Son parámetros que ayudan a describir la distribución de probabilidad.

#### Esperanza matemática o valor esperado
- No tiene por qué ser un valor del recorrido de la variable.
- Es una medida de posición de la distribución de probabilidad (centro de gravedad).
- Cuando el número de observaciones es muy grande, la media muestral tiende a la esperanza matemática.

##### Caso discreto
$$E(X) = \mu_X = \sum_{i=1}^{\infty} x_i \, p_X(x_i) \quad \text{siempre que exista} \quad \sum_{i=1}^{\infty} |x_i| \, p_X(x_i)$$

##### Caso continuo
$$E(X) = \mu_X = \int_{-\infty}^{\infty} x\, f_X(x)\, dx \quad \text{siempre que exista} \quad \int_{-\infty}^{\infty} |x|\, f_X(x)\, dx$$

##### Propiedades
- Sea $X$ v.a. tal que existe $EX$, $a, b \in \mathbb{R}$: $\quad E(aX + b) = a\,EX + b$
- Sean $X$, $Y$ v.a. tales que existen $EX$ y $EY$: $\quad E(X + Y) = EX + EY$

##### Esperanza de una transformada (teorema)
Sea $X$ una v.a. y $Y = g(X)$:
- Si $X$ es **discreta**:
$$E(g(X)) = \sum_{j=1}^{\infty} g(x_j)\, p_X(x_j)$$
- Si $X$ es **continua**:
$$E(g(X)) = \int_{-\infty}^{\infty} g(x)\, f_X(x)\, dx$$

#### Varianza
$$V(X) = E(X - EX)^2 = \sigma_X^2 \quad \text{siempre que } E(X^2) < \infty$$
*La raíz cuadrada de la varianza se denomina desviación estándar $\sigma_X$.*

##### Caso continuo
$$V(X) = \int_{-\infty}^{\infty} (x - \mu)^2\, f_X(x)\, dx$$

##### Caso discreto
$$V(X) = \sum_{i=1}^{\infty} (x_i - \mu)^2\, p_X(x_i)$$

##### Propiedades
- $V(X) = EX^2 - (EX)^2$
- $V(aX + b) = a^2\, V(X)$

### Desigualdad de Chebyshev
Sea $X$ una v.a. con $EX = \mu$ y $V(X) = \sigma^2$ y $k$ un numero real positivo:
$$P\left(|X - \mu| \geq k\sigma\right) \leq \frac{1}{k^2}$$
Equivalentemente:
$$P\left(|X - \mu| < k\sigma\right) \geq 1 - \frac{1}{k^2}$$
*La cota puede ser precisa o alejada, proporciona información sobre probabilidad sin conocer la distribución.*

### Esperanza y varianza aproximadas de una transformada
Si $g$ tiene derivadas continuas en el recorrido de $X$, se desarrolla en serie de Taylor alrededor de $\mu_X$ **hasta el término de orden 2**, despreciando los demás términos:
$$g(x) \approx g(\mu_X) + g'(\mu_X)(x - \mu_X) + \frac{1}{2}\, g''(\mu_X)(x - \mu_X)^2$$

**Para la esperanza** se toma esperanza en ambos miembros usando los 3 términos:
$$E(Y) \approx g(\mu_X) + \frac{\sigma_X^2\, g''(\mu_X)}{2}$$

**Para la varianza** se desprecia el término de orden 2 y se toma varianza solo sobre el término de orden 1:
$$V(Y) \approx \left[g'(\mu_X)\right]^2 \sigma_X^2$$

> [!note]
> La esperanza de una transformada se puede calcular:
> - **Exacta:** por definición (encontrando primero la f.d.p. de la transformada) o por el teorema.
> - **Aproximada:** por Taylor, usando solo $\mu_X$ y $\sigma_X^2$.

