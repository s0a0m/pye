### Variable aleatoria
Sea $\mathcal{E}$ un experimento aleatorio y $S$ su espacio muestral asociado. Una variable aleatoria es una función que asigna a cada elemento $s$ de $S$ un número real $X(s)$. Es decir
$$X: S\to R$$
*El recorrido de todos los valores posibles de X se llama recorrido de la variable X, se denota con $R_x$*
La probabilidad inducida es la probabilidad sobre el nuevo espacio muestral $R_x$. Ejemplo: $P(X = 1)=0.4$
#### Variable aleatoria discreta
Cuando el recorrido es finito o infinito numerable ($R_x = \{x_1, x_2, \dots, x_n\}$ o $R_x = \{x_1, x_2, \dots\}$) donde a cada $x_i$ se le asocia una probabilidad $p_x(x_i)=P(X=x_i)$ para $i=1,2,...$ y el conjunto de valores $p_x(x_i)$ cumple:
1. $\quad p_X(x_i) \geq 0$
2. $\quad \sum_{x_i} p_X(x_i) = 1$
*Esta función se llama función de masa de probabilidad o f.m.p*
Ejemplo:

<div align="center">
  <table>
    <thead>
      <tr><th>x</th><th>pX(x)</th></tr>
    </thead>
    <tbody>
      <tr><td><strong>0</strong></td><td>10/28</td></tr>
      <tr><td><strong>1</strong></td><td>15/28</td></tr>
      <tr><td><strong>2</strong></td><td>3/28</td></tr>
      <tr><td></td><td><strong>1</strong></td></tr>
    </tbody>
  </table>
</div>

```chart
type: bar
labels: ["0", "1", "2"]
series:
  - title: "p(x)"
    data: [0.357, 0.535, 0.107]
tension: 0.2
width: 60%
labelColors: false
fill: false
beginAtZero: true
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
```
#### Variable aleatoria continua
Cuando existe una función $f_x$ no negativa, definida sobre la recta real, tal que para cualquier intervalo $A$.
$$P(X \in A) = \int f_X(x)\,dx$$
*$f_x$ se denomina función de densidad de probabilidad o f.d.p y cumple con estas condiciones:*
1. $\quad f_X(x) \geq 0$
2. $\quad \int_{-\infty}^{\infty} f_X(x)\,dx = 1$
Ejemplo:
$$f_X(x) = \begin{cases} 1/2 & 0 \leq x \leq 2 \\ 0 & \text{en otro caso} \end{cases}$$
<div align="center">
<svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrow" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
  </defs>

  <!-- Ejes -->
  <line x1="40" y1="160" x2="260" y2="160" stroke="black" stroke-width="2" marker-end="url(#arrow)"/>
  <line x1="40" y1="170" x2="40" y2="20" stroke="black" stroke-width="2" marker-end="url(#arrow)"/>

  <!-- Rectángulo área -->
  <rect x="40" y="80" width="160" height="80" fill="#aaa" opacity="0.6" stroke="black" stroke-width="1.5"/>

  <!-- Etiquetas eje X -->
  <text x="40"  y="175" text-anchor="middle" font-size="13">0</text>
  <text x="120" y="175" text-anchor="middle" font-size="13">1</text>
  <text x="200" y="175" text-anchor="middle" font-size="13">2</text>

  <!-- Etiqueta eje Y -->
  <text x="30" y="84" text-anchor="end" font-size="13">1/2</text>

  <!-- área = 1 -->
  <text x="210" y="70" font-size="12">área = 1</text>
  <line x1="205" y1="72" x2="160" y2="90" stroke="black" stroke-width="1"/>

</svg>
</div>
- *La f.d.p no es una probabilidad, es una herramienta para calcular probabilidades*.
- *En el caso de una variable aleatoria continua la probabilidad en un punto en 0*.

### función de distribución acumulada 
$$\forall x \in \mathbb{R} \quad F_X(x) = P[X \leq x]$$
Es la probabilidad acumulada desde $-\infty$ hasta el punto $x$. Observación:
$$\forall x \in \mathbb{R} \quad F_X(x) = P[X \leq x]$$
#### Teorema

- Sea X v.a discreta, $p_x$ su f.m.p
$$\forall x \in \mathfrak{R} \qquad F_X(x) = \sum_{x_j \leq x} p_X(x_j)$$
<div align="center">
<svg width="300" height="280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arr1" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arr2" markerWidth="10" markerHeight="7" refX="0" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>

  <!-- Ejes -->
  <line x1="60" y1="230" x2="260" y2="230" stroke="black" stroke-width="2" marker-end="url(#arr1)"/>
  <line x1="60" y1="230" x2="60" y2="40" stroke="black" stroke-width="2" marker-end="url(#arr2)"/>

  <!-- Etiquetas eje Y -->
  <text x="55" y="195" text-anchor="end" font-size="12">3/28</text>
  <text x="55" y="155" text-anchor="end" font-size="12">10/28</text>
  <text x="55" y="105" text-anchor="end" font-size="12">15/28</text>
  <text x="50" y="60" text-anchor="end" font-size="12">p(x)</text>

  <!-- Etiquetas eje X -->
  <text x="100" y="248" text-anchor="middle" font-size="13">0</text>
  <text x="160" y="248" text-anchor="middle" font-size="13">1</text>
  <text x="220" y="248" text-anchor="middle" font-size="13">2</text>

  <!-- Barras -->
  <line x1="100" y1="230" x2="100" y2="155" stroke="black" stroke-width="6"/>
  <line x1="160" y1="230" x2="160" y2="105" stroke="black" stroke-width="6"/>
  <line x1="220" y1="230" x2="220" y2="195" stroke="black" stroke-width="6"/>
</svg>
</div>
<div align="center">
<svg width="320" height="280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arr3" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arr4" markerWidth="10" markerHeight="7" refX="" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>

  <!-- Ejes -->
  <line x1="60" y1="220" x2="290" y2="220" stroke="black" stroke-width="2" marker-end="url(#arr3)"/>
  <line x1="60" y1="220" x2="60" y2="30" stroke="black" stroke-width="2" marker-end="url(#arr4)"/>

  <!-- Etiquetas eje Y -->
  <text x="55" y="175" text-anchor="end" font-size="12">10/28</text>
  <text x="55" y="120" text-anchor="end" font-size="12">25/28</text>
  <text x="55" y="70"  text-anchor="end" font-size="12">1</text>
  <text x="45" y="45"  text-anchor="end" font-size="12">F(x)</text>

  <!-- Etiquetas eje X -->
  <text x="60"  y="238" text-anchor="middle" font-size="13">0</text>
  <text x="130" y="238" text-anchor="middle" font-size="13">1</text>
  <text x="200" y="238" text-anchor="middle" font-size="13">2</text>
  <text x="275" y="238" text-anchor="middle" font-size="13">x</text>

  <!-- Segmento antes de 0 -->
  <line x1="20" y1="220" x2="60" y2="220" stroke="blue" stroke-width="2.5"/>

  <!-- Segmento [0,1) y=10/28 -->
  <line x1="60" y1="175" x2="130" y2="175" stroke="blue" stroke-width="2.5"/>

  <!-- Segmento [1,2) y=25/28 -->
  <line x1="130" y1="120" x2="200" y2="120" stroke="blue" stroke-width="2.5"/>

  <!-- Segmento [2,∞) y=1 -->
  <line x1="200" y1="70" x2="280" y2="70" stroke="blue" stroke-width="2.5"/>

  <!-- Círculos abiertos al FINAL de cada segmento -->
  <circle cx="130" cy="175" r="5" fill="white" stroke="blue" stroke-width="2"/>
  <circle cx="200" cy="120" r="5" fill="white" stroke="blue" stroke-width="2"/>
  <circle cx="60"  cy="220" r="5" fill="white" stroke="blue" stroke-width="2"/>

</svg>
</div>
*Da un salto en cada punto recorrido igual a la probabilidad de dicho punto.*

- Sea X v.a continua, $f_x$ su f.d.p
$$\forall x \in \mathfrak{R} \qquad F_X(x) = \int_{-\infty}^{x} f_X(t)\, dt$$
Ejemplo:
<div align="center">
<svg width="380" height="250" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY" markerWidth="10" markerHeight="7" refX="" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>

  <!-- Ejes -->
  <line x1="100" y1="170" x2="350" y2="170" stroke="black" stroke-width="2" marker-end="url(#arrX)"/>
  <line x1="100" y1="200" x2="100" y2="30" stroke="black" stroke-width="2" marker-end="url(#arrY)"/>

  <!-- Etiquetas eje Y -->
  <text x="90" y="105" text-anchor="end" font-size="13">1/2</text>
  <text x="85" y="50"  text-anchor="end" font-size="13">f(x)</text>

  <!-- Etiquetas eje X -->
  <text x="190" y="188" text-anchor="middle" font-size="13">1</text>
  <text x="270" y="188" text-anchor="middle" font-size="13">2</text>
  <text x="340" y="188" text-anchor="middle" font-size="13">x</text>

  <!-- Marca eje Y -->
  <line x1="96" y1="105" x2="104" y2="105" stroke="black" stroke-width="1.5"/>

  <!-- Segmento y=0 antes de 1 -->
  <line x1="20" y1="170" x2="100" y2="170" stroke="blue" stroke-width="3"/>

  <!-- Segmento y=1/2 entre 1 y 2 -->
  <line x1="100" y1="105" x2="270" y2="105" stroke="blue" stroke-width="3"/>

  <!-- Segmento y=0 después de 2 -->
  <line x1="270" y1="170" x2="345" y2="170" stroke="blue" stroke-width="3"/>

</svg>
</div>

<div align="center">
  <svg width="380" height="280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrX" markerWidth="10" markerHeight="7" refX="" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
    <marker id="arrY" markerWidth="10" markerHeight="7" refX="4" refY="3.5" orient="auto">
      <polygon points="10 3.5, 0 7, 0 0" fill="black"/>
    </marker>
  </defs>

  <!-- Ejes -->
  <line x1="80" y1="200" x2="350" y2="200" stroke="black" stroke-width="2" marker-end="url(#arrX)"/>
  <line x1="80" y1="200" x2="80" y2="15" stroke="black" stroke-width="2" marker-end="url(#arrY)"/>

  <!-- Etiquetas eje Y -->
  <text x="70" y="115" text-anchor="end" font-size="13">1</text>
  <text x="60" y="30"  text-anchor="end" font-size="13">F(x)</text>

  <!-- Etiquetas eje X -->
  <text x="80"  y="218" text-anchor="middle" font-size="13">0</text>
  <text x="160" y="218" text-anchor="middle" font-size="13">1</text>
  <text x="240" y="218" text-anchor="middle" font-size="13">2</text>
  <text x="340" y="218" text-anchor="middle" font-size="13">x</text>

  <!-- Marcas eje X -->
  <line x1="160" y1="196" x2="160" y2="204" stroke="black" stroke-width="1.5"/>
  <line x1="240" y1="196" x2="240" y2="204" stroke="black" stroke-width="1.5"/>

  <!-- Marca eje Y -->
  <line x1="76" y1="110" x2="84" y2="110" stroke="black" stroke-width="1.5"/>

  <!-- Segmento horizontal izquierdo (antes de 0, y=0) -->
  <line x1="20" y1="200" x2="80" y2="200" stroke="blue" stroke-width="2.5"/>

  <!-- Segmento diagonal (de 0 a 2, sube de 0 a 1) -->
  <line x1="80" y1="200" x2="240" y2="110" stroke="blue" stroke-width="2.5"/>

  <!-- Segmento horizontal derecho (después de 2, y=1) -->
  <line x1="240" y1="110" x2="340" y2="110" stroke="blue" stroke-width="2.5"/>

</svg>
</div>

*Bajo algunas condiciones se cumple que:$$F'_X(x) = f_X(x)$$*
#### Propiedades 

1. La función $F_X$ es no decreciente, es decir: si $x_1 \leq x_2 \Rightarrow F_X(x_1) \leq F_X(x_2)$

2. $\lim_{x \to \infty} F_X(x) = 1$ $\qquad \lim_{x \to -\infty} F_X(x) = 0$

3. Para todo $a, b \in \mathbb{R}$, $a < b \Rightarrow P(a < X \leq b) = F_X(b) - F_X(a)$

En caso continuo:
$$P(a < X \leq b) = P(a \leq X < b) = P(a < X < b) = P(a \leq X \leq b) = F_X(b) - F_X(a)$$

<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 15px; display: inline-block; text-align: left; max-width: 500px;">
    <p>La <strong>f.m.p.</strong> (discreta), la <strong>f.d.p.</strong> (continua) y la <strong>f.d.a.</strong> (discreta o continua) son formas equivalentes de especificar la distribución de probabilidad de una variable aleatoria.</p>
  </div>
</div>

### Transformación de variables aleatorias
Sea X una v.a con distribución de probabilidad conocida entonces. 
$$Y = g(X)$$
También es una v.a.
### Casos de transformación
#### Caso discreto 
Si $X$ es v.a discreta entonces $Y=g(X)$ también.
Sean $R_X = \{x_1, x_2, \dots, x_n\}$ y $R_Y = \{x_1, x_2, \dots, x_n\}$ los recorridos de $X,Y$
La f.m.p de X es conocida.
Sea $y_i \in R_Y$
$$p_Y(y_i) = P[Y = y_i] = P\{x \in R_X : g(x) = y_i\} = \sum_{x \in R_X : g(x) = y_i} p_X(x)$$
#### Caso continuo - discreto
Si $X$ es v.a continua entonces $Y=g(X)$ puede ser continua o discreta.
Se procede como en el caso discreto.
#### Caso continuo - continuo
Si $X$ es v.a continua entonces $Y=g(X)$ puede ser continua o discreta.
Se determina la f.d.p de $Y$ a partir de la de $X$
Este procedimiento es para una función g monótona creciente:
1. Representar gráficamente $Y=g(X)$ 
2. Obtener $R_Y$
3. Obtener la f.d.a de $Y$ $F_Y$
$$y \in \mathfrak{R}$$
$$F_Y(y) = P(Y \leq y) = P(g(X) \leq y) = P(X \leq g^{-1}(y)) = F_X(g^{-1}(y))$$
$$F_Y(y) = \begin{cases} 0 & y < \dots \\ F_X(|g^{-1}(y)|) & \dots \leq y < \dots \\ 1 & y \geq \dots \end{cases}$$
4. Derivar $F_Y$ respecto de $y$ a fin de obtener $f_y$ 

### Características de las variables aleatorias
Son parámetros que ayudan a describir la distribución de probabilidad.

#### Esperanza matemática o valor esperado
- No tiene porque ser un valor del recorrido de la variable.
- Es una medida de posición de la distribución de probabilidad (es el centro de gravedad)
- Cuando el número de observaciones es muy grande la media muestral tiende a la esperanza matemática.
##### Caso discreto 
Sea $X$ una v.a discreta, $R_x = \{x_1, x_2, \dots, x_n\}$ su recorrido y $p_X(x_i)$ con $i=1,2,...$ su f.m.p. El valor esperado se define como:
$$E(X) = \mu_X = \sum_{i=1}^{\infty} x_i \, p_X(x_i) \quad \text{siempre que exista} \quad \sum_{i=1}^{\infty} |x_i| \, p_X(x_i)$$
##### Caso continuo
Sea $X$ una v.a continua, $f_x$ su f.d.p. El valor esperado de X se define como:
$$EX = \mu_X = \int_{-\infty}^{\infty} x f_X(x) \, dx \quad \text{siempre que exista} \quad \int_{-\infty}^{\infty} |x| f_X(x) \, dx$$
##### Propiedades
- Sea $X$ v.a. tal que existe $EX$, sean $a, b \in \mathfrak{R}$, entonces $E(aX + b) = a \, EX + b$
- Sean $X$, $Y$ v.a. tales que existen $EX$ y $EY$. Entonces $E(X + Y) = EX + EY$
##### Esperanza de una transformada de v.a (teorema)
Sea $X$ una v.a. y sea $Y = g(X)$, entonces:
- Si $X$ es discreta con función de masa $p_X$
$$EY = E(g(X)) = \sum_{j=1}^{\infty} g(x_j) \, p_X(x_j)$$
- Si $X$ es continua con densidad $f_X$
$$EY = E(g(X)) = \int_{-\infty}^{\infty} g(x) f_X(x) \, dx$$
####  Varianza 
Sea $X$ una v.a. La varianza de $X$ se define como:
$$V(X) = E(X - EX)^2 = \sigma_X^2 \quad \text{siempre que } E(X^2) < \infty$$
*La raíz cuadrada de la varianza se denomina desviación estándar* ($\sigma_X$).
##### Caso continuo
$$V(X) = \sigma_X^2 = \int_{-\infty}^{\infty} (x - \mu)^2 f_X(x) \, dx \quad \text{siempre que exista } E(X^2)$$
##### Caso discreto
$$V(X) = \sigma_X^2 = \sum_{i=1}^{\infty} (x_i - \mu)^2 \, p_X(x_i) \quad \text{siempre que exista } E(X^2)$$
##### Propiedades
- Sea $X$ v.a. tal que existe $V(X)$, entonces $V(X) = EX^2 - (EX)^2$
- Sea $X$ v.a. tal que existe $V(X)$ y sean $a, b \in \mathfrak{R}$, entonces $V(aX + b) = a^2 \, V(X)$
### Desigualdad de Chebyshev
Sea $X$ una v.a. con $EX = \mu$ y $Var(X) = \sigma^2$, entonces:
$$P\left(|X - \mu| \geq k\sigma\right) \leq \frac{1}{k^2}$$
donde $k$ es un número real positivo. También se puede escribir de la forma:
$$P\left(|X - \mu| < k\sigma\right) \geq 1 - \frac{1}{k^2}$$
*La cota puede ser precisa o alejada, proporciona información sobre probabilidad sin conocer la distribución y es una forma de acotar la probabilidad de ciertos intervalos*.
### Esperanza y varianza aproximada de la transformada de una v.a
Sí g tiene derivadas continuas en el recorrido de X entonces se desarrolla la serie de Taylor en g alrededor de $x=\mu_X$ hasta el termino de orden 1.
$$y = g(x) \approx g(\mu_X) + g'(\mu_X)(x - \mu_X) + \frac{1}{2!} g''(\mu_X)(x - \mu_X)^2$$
*Para la esperanza se toma la esperanza en ambos miembros y para la varianza se desprecia el termino de orden 2 y tomamos la varianza. Queda:*
$$Ey \approx g(\mu_X) + \sigma_X^2 \frac{g''(\mu_X)}{2}$$
$$V(Y) \approx \left[g'(\mu_X)\right]^2 \sigma_X^2$$
<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 15px; display: inline-block; text-align: left; max-width: 500px;">
    <p>La esperanza de una transformada de una v.a. podemos hacerlo:</p>
    <p><strong>De manera exacta:</strong></p>
    <ul>
      <li>Por definición, encontrando primero la función de densidad de la transformada y luego la esperanza.</li>
      <li>Por el teorema.</li>
    </ul>
    <p><strong>De manera aproximada:</strong></p>
    <ul>
      <li>Por Taylor, encontrando la esperanza y varianza aproximadas solo a partir de la esperanza y varianza de la variable original.</li>
    </ul>
  </div>
</div>
