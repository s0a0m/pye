## Inferencia Estadística
La idea es estudiar una **población** a partir de una **muestra**, ya que en muchos casos es imposible acceder a todos los valores de la población por costo económico, costo en tiempo o muestreo destructivo.

**Población:** es una variable aleatoria $X$ con una cierta distribución de probabilidad y sus correspondientes parámetros (desconocidos). *Ejemplo: el peso de los recién nacidos en Tucumán en septiembre 2019.*

Se toma entonces una **muestra aleatoria** de $X$: un conjunto de v.a. $X_1, X_2, \dots, X_n$ iid como $X$, y a partir de ella se quiere conocer:
- De qué distribución proviene la muestra.
- Cuáles son sus parámetros.

> [!note] ¿Qué quiero?
> Dada una v.a. de interés $X$ y una muestra observada: se desea conocer su distribución y sus parámetros. Si se puede tomar muestras reales se usan, sino se **simulan**.

## Simulación de una muestra aleatoria
Cuando no es posible tomar muestras reales, se puede **simular** una muestra usando el **método de Montecarlo**, que permite generar datos de cualquier distribución de probabilidad a partir de números aleatorios uniformes.

### Teorema de la transformación integral
Sea $X$ v.a. continua con función de distribución acumulada $F_X$, $\forall x \in [a,b]$ con $f_X(x) > 0$. Si se define:
$$U = F_X(X)$$
entonces $U$ tiene **distribución Uniforme en $[0,1]$**.

$U = F_X(X)$ se llama la **Transformada Integral** de $X$.

**Aplicación:** $U = F_X(X) \Rightarrow X = F_X^{-1}(U)$

Es decir: dado un número aleatorio $u \sim U[0,1]$, se puede obtener un valor $x$ con la distribución deseada aplicando la inversa de la FDA.

### Procedimiento caso continuo
**Objetivo:** generar una m.a. $x_1, \dots, x_n$ de una población $X$.
1. Tomar $n$ números aleatorios $u_1, \dots, u_n \sim U[0,1]$ de la tabla, con tantos dígitos como precisión se desee.
2. Obtener cada valor simulado mediante:
$$x_i = F_X^{-1}(u_i)$$
donde $F_X$ es la FDA de la v.a. en cuestión.

### Procedimiento caso discreto
1. Tomar $n$ números aleatorios $u_1, \dots, u_n \sim U[0,1]$ de la tabla, con tantos dígitos como precisión se desee.
2. Considerar a $u_i$ como un valor de la distribución acumulada $F_X$ (tabulada) y tomar el **menor** $x_i$ que verifique:
$$F_X(x_i) > u_i$$

> [!note] Diferencia entre casos
> En el caso continuo se **despeja** $x$ analíticamente de la FDA. En el caso discreto, como la FDA es una escalera, se **busca en la tabla** el primer valor cuya acumulada supere a $u_i$.

## Identificación del modelo (chequeo de distribución)
Cuando se observa una m.a. y la distribución es desconocida, se postula una distribución y luego se **verifica** si los datos responden a ella.

### Teorema para verificar distribuciones
Sea $X$ v.a. continua con FDA $F_X$, sea $X_1, \dots, X_n$ una m.a. de $X$ y sea $X_{(1)}, X_{(2)}, \dots, X_{(n)}$ la **muestra ordenada**, entonces:
$$E\left[F_X(X_{(j)})\right] = \frac{j}{n+1}$$

**Aplicación:** para una muestra observada y ordenada $x_{(1)}, \dots, x_{(n)}$ suficientemente grande:
$$F_X\!\left(x_{(j)}\right) \approx \frac{j}{n+1}$$

**Interpretación:** los valores observados dividen el área bajo la curva en $n+1$ partes iguales, cada una de área $\frac{1}{n+1}$.

---

### Caso particular 1: Distribución Exponencial
Si los datos provienen de una $E(\lambda)$, entonces para $n$ grande:
$$F_X\!\left(x_{(j)}\right) \approx \frac{j}{n+1} \;\Rightarrow\; 1 - e^{-\lambda\, x_{(j)}} \approx \frac{j}{n+1}$$
Despejando:
$$x_{(j)} \approx \frac{1}{\lambda}\left[-\ln\!\left(1 - \frac{j}{n+1}\right)\right]$$

Si graficamos $x_{(j)}$ vs $-\ln\!\left(1 - \dfrac{j}{n+1}\right)$ debe ajustar a una **recta que pasa por el origen** con pendiente $\dfrac{1}{\lambda}$.

<div align="center">
<svg width="280" height="200" xmlns="http://www.w3.org/2000/svg">
  <rect x="40" y="10" width="220" height="160" fill="white" stroke="#ccc" stroke-width="1"/>
  <!-- Ejes -->
  <line x1="40" y1="170" x2="260" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="40" y1="170" x2="40"  y2="10"  stroke="black" stroke-width="1.5"/>
  <!-- Labels -->
  <text x="150" y="195" text-anchor="middle" font-size="11">-ln(1 - j/(n+1))</text>
  <text x="15"  y="95"  text-anchor="middle" font-size="11" transform="rotate(-90,15,95)">x(j)</text>
  <!-- Recta desde origen -->
  <line x1="40" y1="170" x2="240" y2="30" stroke="#1a6fa8" stroke-width="2"/>
  <!-- Puntos -->
  <circle cx="80"  cy="142" r="4" fill="#c0392b"/>
  <circle cx="110" cy="120" r="4" fill="#c0392b"/>
  <circle cx="150" cy="95"  r="4" fill="#c0392b"/>
  <circle cx="185" cy="68"  r="4" fill="#c0392b"/>
  <circle cx="220" cy="45"  r="4" fill="#c0392b"/>
  <!-- Anotaciones -->
  <text x="245" y="28"  font-size="10" fill="#1a6fa8">m = 1/λ</text>
  <text x="42"  y="185" font-size="10" fill="#555">b = 0</text>
</svg>
</div>

**Conclusión:** si $x_{(j)}$ vs $-\ln\!\left(1 - \dfrac{j}{n+1}\right)$ ajusta a una recta, los datos provienen de una distribución Exponencial. La ordenada al origen es $0$ y la pendiente es $\dfrac{1}{\lambda}$.

---

### Caso particular 2: Distribución Normal
Si los datos provienen de una $N(\mu, \sigma)$, entonces para $n$ grande:
$$\Phi\!\left(\frac{x_{(j)} - \mu}{\sigma}\right) \approx \frac{j}{n+1} \;\Rightarrow\; x_{(j)} \approx \mu + \sigma\,\Phi^{-1}\!\left(\frac{j}{n+1}\right)$$

Si graficamos $x_{(j)}$ vs $\Phi^{-1}\!\left(\dfrac{j}{n+1}\right)$ debe ajustar a una **recta**.

<div align="center">
<svg width="280" height="200" xmlns="http://www.w3.org/2000/svg">
  <rect x="40" y="10" width="220" height="160" fill="white" stroke="#ccc" stroke-width="1"/>
  <!-- Ejes -->
  <line x1="40" y1="170" x2="260" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="40" y1="170" x2="40"  y2="10"  stroke="black" stroke-width="1.5"/>
  <!-- Labels -->
  <text x="150" y="195" text-anchor="middle" font-size="11">Φ⁻¹(j/(n+1))</text>
  <text x="15"  y="95"  text-anchor="middle" font-size="11" transform="rotate(-90,15,95)">x(j)</text>
  <!-- Recta -->
  <line x1="55" y1="155" x2="245" y2="25" stroke="#1a6fa8" stroke-width="2"/>
  <!-- Puntos -->
  <circle cx="75"  cy="148" r="4" fill="#c0392b"/>
  <circle cx="110" cy="122" r="4" fill="#c0392b"/>
  <circle cx="150" cy="93"  r="4" fill="#c0392b"/>
  <circle cx="190" cy="63"  r="4" fill="#c0392b"/>
  <circle cx="225" cy="38"  r="4" fill="#c0392b"/>
  <!-- Anotaciones -->
  <text x="220" y="22"  font-size="10" fill="#1a6fa8">m = σ</text>
  <text x="42"  y="142" font-size="10" fill="#555">b = μ</text>
</svg>
</div>

**Conclusión:** si $x_{(j)}$ vs $\Phi^{-1}\!\left(\dfrac{j}{n+1}\right)$ ajusta a una recta, los datos provienen de una distribución Normal. La ordenada al origen es $\mu$ y la pendiente es $\sigma$.

> [!note] Nota
> No debe esperarse una relación lineal exacta.

---

### Caso discreto: Distribución Poisson
La técnica es diferente porque la FDA no es continua. Se usa que la frecuencia relativa observada aproxima a la probabilidad:
$$\frac{f_{\text{obs}}(x)}{n} \approx P(X = x) = e^{-\lambda}\frac{\lambda^x}{x!}$$
Aplicando logaritmo natural:
$$\ln\!\left(f_{\text{obs}}(x)\right) - \ln(n) \approx -\lambda + x\ln\lambda - \ln(x!)$$
Despejando:
$$\ln\!\left(f_{\text{obs}}(x)\right) + \ln(x!) \approx x\ln\lambda + \ln(n) - \lambda$$

Si graficamos $x$ vs $\ln\!\left(f_{\text{obs}}(x)\right) + \ln(x!)$ debe ajustar a una **recta** con pendiente $\ln\lambda$ y ordenada al origen $\ln(n) - \lambda$.

<div align="center">
<svg width="280" height="200" xmlns="http://www.w3.org/2000/svg">
  <rect x="40" y="10" width="220" height="160" fill="white" stroke="#ccc" stroke-width="1"/>
  <!-- Ejes -->
  <line x1="40" y1="170" x2="260" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="40" y1="170" x2="40"  y2="10"  stroke="black" stroke-width="1.5"/>
  <!-- Labels -->
  <text x="150" y="195" text-anchor="middle" font-size="11">ln f_obs(x) + ln x!</text>
  <text x="15"  y="95"  text-anchor="middle" font-size="11" transform="rotate(-90,15,95)">x</text>
  <!-- Recta -->
  <line x1="60" y1="155" x2="235" y2="30" stroke="#1a6fa8" stroke-width="2"/>
  <!-- Puntos (x=0,1,2,3,4) -->
  <circle cx="68"  cy="148" r="4" fill="#c0392b"/>
  <circle cx="105" cy="128" r="4" fill="#c0392b"/>
  <circle cx="145" cy="95"  r="4" fill="#c0392b"/>
  <circle cx="185" cy="65"  r="4" fill="#c0392b"/>
  <circle cx="222" cy="38"  r="4" fill="#c0392b"/>
  <!-- Anotaciones -->
  <text x="210" y="25"  font-size="10" fill="#1a6fa8">m = ln λ</text>
  <text x="42"  y="145" font-size="10" fill="#555">b = ln(n)−λ</text>
</svg>
</div>

**Conclusión:** si $x$ vs $\ln\!\left(f_{\text{obs}}(x)\right) + \ln(x!)$ ajusta a una recta, los datos provienen de una distribución Poisson. La pendiente es $\ln\lambda$.