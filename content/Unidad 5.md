### Distribuciones conjuntas (Bidimensional)

#### variable aleatoria bidimencional
Sea $\mathcal{E}$ un experimento aleatorio,$S$ su espacio muestral, $X$ e $Y$ vs. as. tal que a cada $s$ de $S$ se le asigne numeros reales $X(s)$ e $Y(s)$ respectivamente. Entonces se dice que el par $(X,Y)$ es una **v.a bidimencional**. 

#### Caso discreto
$(X,Y)$ es una v.a.b discreta si el recorrido es finito o infinito numerable.
$$R_{XY} = \{(x_i, y_j): \ i = 1, 2, \dots n, \dots \ j = 1, 2, \dots, m, \dots\}$$
Su **función de masa conjunta** se define como:
$p_{XY}(x, y) = P(X = x, Y = y)$ para todo $(x, y) \in R_{XY}$

Se debe cumplir que:
1. $p_{XY}(x, y) \geq 0 \quad$ para todo $(x,y) \in R_{XY}$
2.  $\sum_x \sum_y p_{XY}(x, y) = 1$

**Las funciones de masa marginales son:**
Para todo $x \in R_X$: $\quad p_X(x) = \sum_y p_{XY}(x, y)$
Para todo $y \in R_Y$: $\quad p_Y(y) = \sum_x p_{XY}(x, y)$
#### Caso continuo
$(X, Y)$ es una v.a.b continua si existe una función $f_{XY}$ llamada **función de densidad de probabilidad conjunta** tal que:
 $\forall A \subset \mathfrak{R}^2$: $\quad P(A) = \iint_A f_{XY}(x, y) \, dx \, dy$ 

Se debe cumplir que: 
1. $f_{XY}(x, y) \geq 0 \quad$ para todo $(x, y) \in \mathfrak{R}^2$ 
2. $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{XY}(x, y) \, dx \, dy = 1$ 

**Las funciones de densidad marginales son:** 
Para todo $x \in R_X$: $\quad f_X(x) = \int_{-\infty}^{\infty} f_{XY}(x, y) \, dy$ 
Para todo $y \in R_Y$: $\quad f_Y(y) = \int_{-\infty}^{\infty} f_{XY}(x, y) \, dx$

### Independencia de variables aleatorias
#### Caso discreto
Sean $X$ e $Y$ dos v.a. discretas, decimos que $X$ e $Y$ son independientes si:
$$p_{XY}(x, y) = p_X(x) p_Y(y) \quad \text{para todo } (x, y) \in R_{XY}$$
#### Caso continuo
Sean $X$ e $Y$ v.a. continuas, decimos que $X$ e $Y$ son independientes si: 
$$f_{XY}(x, y) = f_X(x) f_Y(y) \quad \text{para todo } (x, y) \in R_{XY}$$
### Teorema: Esperanza de una función de varias variables aleatorias
#### Caso continuo
$$\quad E[h(x,y)] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} h(x,y) f_{XY}(x,y) \, dx \, dy$$
#### Caso discreto
$$\quad E[h(x,y)] = \sum_x \sum_y h(x,y) \, p_{XY}(x,y)$$

### Propiedades de la esperanza
1. Sean $X_1, \dots, X_n$ v.a. cuyas esperanzas existen; sean $a_1, \dots, a_n$ constantes, entonces: $$E(a_1X_1 + \dots + a_nX_n) = a_1EX_1 + \dots + a_nEX_n$$
2. Si $X$ e $Y$ son v.a. independientes cuyas esperanzas existen, entonces: $E(XY) = EXEY$ **Generalización:** Sean $X_1, \dots, X_n$ v.a. independientes, tales que $EX_i < \infty$ para $i = 1, 2, \dots, n$, entonces: $$E(X_1 \cdots X_n) = \prod_{i=1}^{n} EX_i$$ **Observación:** El recíproco de la propiedad 2 no es cierto, es decir: $$E(XY) = EXEY \;\not\Rightarrow\; X \text{ e } Y \text{ son independientes}$$
### Covarianza
Es una medida de **asociación lineal** entre dos variables. Se define como:
$$\text{Cov}(X, Y) = E\left[(X - \mu_X)(Y - \mu_Y)\right] \quad \text{siempre que } \sigma_X < \infty \text{ y } \sigma_Y < \infty$$
Se puede probar que:
$$\text{Cov}(X, Y) = E(XY) - EX \cdot EY$$
#### Interpretación gráfica

<div align="center">
<svg width="520" height="190" xmlns="http://www.w3.org/2000/svg">
  <!-- GRÁFICO 1: Asociación positiva -->
  <text x="90" y="15" text-anchor="middle" font-size="11" font-weight="bold">Asociación positiva</text>
  <!-- Ejes -->
  <line x1="30" y1="160" x2="170" y2="160" stroke="black" stroke-width="1.5"/>
  <line x1="30" y1="160" x2="30"  y2="20"  stroke="black" stroke-width="1.5"/>
  <!-- μX μY -->
  <line x1="100" y1="160" x2="100" y2="20" stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <line x1="30"  y1="90"  x2="170" y2="90" stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <text x="100" y="175" text-anchor="middle" font-size="10">μX</text>
  <text x="18"  y="93"  text-anchor="middle" font-size="10">μY</text>
  <!-- Puntos con tendencia positiva -->
  <circle cx="45"  cy="148" r="4" fill="#1a6fa8"/>
  <circle cx="60"  cy="130" r="4" fill="#1a6fa8"/>
  <circle cx="75"  cy="115" r="4" fill="#1a6fa8"/>
  <circle cx="88"  cy="105" r="4" fill="#1a6fa8"/>
  <circle cx="110" cy="75"  r="4" fill="#1a6fa8"/>
  <circle cx="125" cy="60"  r="4" fill="#1a6fa8"/>
  <circle cx="145" cy="42"  r="4" fill="#1a6fa8"/>
  <!-- Etiqueta -->
  <text x="90" y="185" text-anchor="middle" font-size="10" fill="#555">E[(X−μX)(Y−μY)] &gt; 0</text>

  <!-- GRÁFICO 2: Asociación negativa -->
  <text x="290" y="15" text-anchor="middle" font-size="11" font-weight="bold">Asociación negativa</text>
  <line x1="210" y1="160" x2="370" y2="160" stroke="black" stroke-width="1.5"/>
  <line x1="210" y1="160" x2="210" y2="20"  stroke="black" stroke-width="1.5"/>
  <line x1="290" y1="160" x2="290" y2="20"  stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <line x1="210" y1="90"  x2="370" y2="90"  stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <text x="290" y="175" text-anchor="middle" font-size="10">μX</text>
  <text x="198" y="93"  text-anchor="middle" font-size="10">μY</text>
  <circle cx="225" cy="42"  r="4" fill="#c0392b"/>
  <circle cx="240" cy="58"  r="4" fill="#c0392b"/>
  <circle cx="258" cy="72"  r="4" fill="#c0392b"/>
  <circle cx="272" cy="85"  r="4" fill="#c0392b"/>
  <circle cx="308" cy="110" r="4" fill="#c0392b"/>
  <circle cx="328" cy="130" r="4" fill="#c0392b"/>
  <circle cx="348" cy="148" r="4" fill="#c0392b"/>
  <text x="290" y="185" text-anchor="middle" font-size="10" fill="#555">E[(X−μX)(Y−μY)] &lt; 0</text>

  <!-- GRÁFICO 3: Sin asociación -->
  <text x="460" y="15" text-anchor="middle" font-size="11" font-weight="bold">Sin asociación</text>
  <line x1="400" y1="160" x2="520" y2="160" stroke="black" stroke-width="1.5"/>
  <line x1="400" y1="160" x2="400" y2="20"  stroke="black" stroke-width="1.5"/>
  <line x1="460" y1="160" x2="460" y2="20"  stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <line x1="400" y1="90"  x2="520" y2="90"  stroke="#aaa" stroke-width="1" stroke-dasharray="4,3"/>
  <text x="460" y="175" text-anchor="middle" font-size="10">μX</text>
  <text x="388" y="93"  text-anchor="middle" font-size="10">μY</text>
  <circle cx="418" cy="55"  r="4" fill="#27ae60"/>
  <circle cx="430" cy="140" r="4" fill="#27ae60"/>
  <circle cx="442" cy="75"  r="4" fill="#27ae60"/>
  <circle cx="452" cy="120" r="4" fill="#27ae60"/>
  <circle cx="470" cy="45"  r="4" fill="#27ae60"/>
  <circle cx="480" cy="130" r="4" fill="#27ae60"/>
  <circle cx="500" cy="65"  r="4" fill="#27ae60"/>
  <text x="460" y="185" text-anchor="middle" font-size="10" fill="#555">E[(X−μX)(Y−μY)] ≅ 0</text>
</svg>
</div>

#### Propiedades de la covarianza
Sean $X$ e $Y$ v.a. tales que existen $\sigma_X^2$ y $\sigma_Y^2$:
1. $\text{Cov}^2(X, Y) \leq \sigma_X^2 \cdot \sigma_Y^2$
2. $\text{Cov}(aX+b, \ cY+d) = ac \cdot \text{Cov}(X, Y) \quad \forall \, a, b, c, d \in \mathbb{R}$
3. $\text{Cov}(X+Y, Z) = \text{Cov}(X,Z) + \text{Cov}(Y,Z)$
4. $X$ e $Y$ independientes $\Rightarrow \text{Cov}(X, Y) = 0$

> [!note] Observación
> $\text{Cov}(X, Y) = 0 \;\not\Rightarrow\; X$ e $Y$ independientes. El recíproco de la propiedad 4 **no es cierto** en general.

### Coeficiente de correlación
La covarianza tiene el inconveniente de que **no está acotada** y depende de las unidades de medida de $X$ e $Y$, por ello no podemos saber cuándo la asociación lineal es fuerte o débil. Por eso se define el **coeficiente de correlación lineal**:
$$\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \, \sigma_Y}$$
#### Propiedades
Sean $X$ e $Y$ v.a. tales que existen $\sigma_X^2$ y $\sigma_Y^2$:
1. $|\rho(X, Y)| \leq 1$
	- $|\rho(X, Y)| \approx 1$ → Existe una fuerte asociación lineal (positiva o negativa) entre las variables.
	- $\rho(X, Y) \approx 0$ → No hay asociación lineal entre las variables *(no indica independencia)*.
2. $X$ e $Y$ independientes $\Rightarrow \rho(X, Y) = 0$ (el reciproco es falso)
3. $Y = aX + b, \; a \neq 0 \;\Longleftrightarrow\; \rho(X,Y) = \begin{cases} 1 & \text{si } a > 0 \\ -1 & \text{si } a < 0 \end{cases}$

## Propiedades de la varianza
Sean $X$ e $Y$ v.a. tales que $\sigma_X^2 < \infty$ y $\sigma_Y^2 < \infty$:
1. Sea $X$ una v.a. tal que $\sigma_X^2 < \infty$ y sean $a, b \in \mathbb{R}$, entonces:
$$V(aX + b) = a^2 V(X)$$
2. Sean $X$ e $Y$ v.a. tales que $\sigma_X^2 < \infty$ y $\sigma_Y^2 < \infty$, entonces:
$$V(X + Y) = V(X) + V(Y) + 2\,\text{Cov}(X, Y)$$
**Consecuencia:** Si $X$ e $Y$ son independientes, entonces $V(X+Y) = V(X) + V(Y)$

**Generalización:** Si $X_1, \dots, X_n$ son v.a. independientes tales que $\sigma_{X_i}^2 < \infty$ para todo $i$, entonces:
$$V\!\left(\sum_{i=1}^{n} X_i\right) = \sum_{i=1}^{n} V(X_i)$$
### Muestra aleatoria (m.a.)
Sea $X$ una v.a. Una **m.a.** de $X$ es un conjunto de v.a. $X_1, X_2, \dots, X_n$ **independientes e idénticamente distribuidas** (iid) como $X$.

Dada una m.a. con media $\mu$ y varianza $\sigma^2$, se tiene que:
$$E\!\left(\sum_{i=1}^{n} X_i\right) = n\mu \qquad V\!\left(\sum_{i=1}^{n} X_i\right) = n\sigma^2$$ $$E(\bar{X}) = \mu \qquad V(\bar{X}) = \frac{\sigma^2}{n}$$

### Teorema de las combinaciones lineales
Sean $X_1, X_2, \dots, X_n$ v.a. **independientes** tales que $\forall \, i = 1, \dots, n$: $X_i \sim N(\mu_i, \sigma_i)$ con $\sigma_i < \infty$, y sean $a_1, \dots, a_n$ constantes reales. Entonces:
$$\sum_{i=1}^{n} a_i X_i \;\sim\; N\!\left(\sum_{i=1}^{n} a_i \mu_i,\; \sqrt{\sum_{i=1}^{n} a_i^2 \sigma_i^2}\right)$$

### Teorema Central del Límite (TCL)
Sean $X_1, \dots, X_n$ v.a. iid. como $X$ tal que $EX = \mu$ y $V(X) = \sigma^2$, con $0 < \sigma^2 < \infty$. Entonces para todo $x \in \mathbb{R}$:
$$\lim_{n \to \infty} P\!\left[\frac{\displaystyle\sum_{i=1}^{n} X_i - n\mu}{\sqrt{n}\,\sigma} \leq x\right] = \Phi(x)$$
donde $\Phi$ es la función de distribución acumulada de la distribución Normal estándar.

#### Formas equivalentes
- $\dfrac{\displaystyle\sum_{i=1}^{n} X_i - n\mu}{\sqrt{n}\,\sigma} \approx N(0,1)$ cuando $n \to \infty$

- $\bar{X} \approx N\!\left(\mu,\, \dfrac{\sigma}{\sqrt{n}}\right)$ cuando $n \to \infty$
- $\frac{\bar{X} - \mu}{\sigma/\sqrt{n}} \approx N(0,1) \quad \text{cuando } n \to \infty$
### Comparación entre teoremas

|                   | **TCL**             | **Combinaciones lineales**             |
| ----------------- | ------------------- | -------------------------------------- |
| **Independencia** | ✓                   | ✓                                      |
| **Distribución**  | Cualquiera (iid)    | Normales (no necesariamente idénticas) |
| **Tamaño**        | $n \to \infty$      | $n \geq 2$                             |
| **Resultado**     | Normal *aproximada* | Normal *exacta*                        |
*Las hipótesis son independencia, distribución y tamaño.*

> [!note] Similitudes
> Ambos teoremas requieren **independencia**, trabajan con $\sum X_i$ o $\bar{X}$, y llevan a la distribución Normal.
> 
### Aproximación de la distribución Binomial por una Normal
Sea $X \sim b(n, p)$, entonces para $n \to \infty$:
$$X \approx N\!\left(np,\; \sqrt{np(1-p)}\right) \quad \text{por TCL}$$
Estandarizando:
$$Z = \frac{X - np}{\sqrt{np(1-p)}} \approx N(0,1)$$

> [!note] Observaciones
> 1. En la práctica si $np(1-p) > 5$ la aproximación es aceptable.
> 2. Se está aproximando una v.a. discreta por una continua, por lo tanto debe aplicarse **corrección por continuidad**.

#### Corrección por continuidad
- $P(a \leq X \leq b) \approx P(a - 0.5 \leq X \leq b + 0.5)$
- $P(a \leq X < b) \approx P(a - 0.5 \leq X < b - 0.5)$
- $P(a < X \leq b) \approx P(a + 0.5 < X \leq b + 0.5)$
- $P(a < X < b) \approx P(a + 0.5 < X < b - 0.5)$

### Aproximación de la distribución Poisson por una Normal
Sea $X \sim P(\lambda)$, entonces para $\lambda$ suficientemente grande:
$$X \approx N\!\left(\lambda,\; \sqrt{\lambda}\right) \quad \text{por TCL}$$
Estandarizando:
$$Z = \frac{X - \lambda}{\sqrt{\lambda}} \approx N(0,1)$$

> [!note] Observaciones
> 1. En la práctica si $\lambda > 5$ la aproximación es aceptable.
> 2. También debe aplicarse **corrección por continuidad**.
