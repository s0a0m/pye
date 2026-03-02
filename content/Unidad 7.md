## Estimación puntual
Supongamos que $X_1, X_2, \dots, X_n$ es una m.a. de $X$ con distribución conocida pero **parámetros desconocidos**. Necesitamos estimar esos parámetros a partir de los valores muestrales.

> [!note] Poblacional vs. muestral
> - $\mu = EX$ es un **número fijo pero desconocido** (parámetro poblacional).
> - $\bar{X} = \dfrac{1}{n}\displaystyle\sum_{i=1}^n X_i$ es una **v.a.** que estima $\mu$ (estadístico muestral). Una vez tomada la muestra, toma un valor particular $\bar{x}$.

### Método de los momentos
**Definiciones:**
- El **momento poblacional de orden $i$** con respecto al origen es: $m_i = E(X^i)$
- El **momento muestral de orden $i$** con respecto al origen es: $\hat{m}_i = \dfrac{1}{n}\displaystyle\sum_{j=1}^n X_j^i$

El método consiste en **estimar los momentos poblacionales con los momentos muestrales**:

| Poblacional | Muestral |
|---|---|
| $EX$ | $\bar{X}$ |
| $EX^2$ | $\dfrac{1}{n}\displaystyle\sum_{i=1}^n X_i^2$ |

Si la distribución tiene $k$ parámetros $\theta_1, \dots, \theta_k$, se escriben como funciones de los momentos y se resuelve el sistema:
$$\begin{cases} \theta_1 = g_1(m_1, m_2, \dots, m_k) \\ \theta_2 = g_2(m_1, m_2, \dots, m_k) \\ \vdots \\ \theta_k = g_k(m_1, m_2, \dots, m_k) \end{cases} \quad\Longrightarrow\quad \begin{cases} \hat{\theta}_1 = g_1(\hat{m}_1, \hat{m}_2, \dots, \hat{m}_k) \\ \hat{\theta}_2 = g_2(\hat{m}_1, \hat{m}_2, \dots, \hat{m}_k) \\ \vdots \\ \hat{\theta}_k = g_k(\hat{m}_1, \hat{m}_2, \dots, \hat{m}_k) \end{cases}$$

#### Procedimiento
1. Identificar los parámetros a estimar.
2. Considerar tantas ecuaciones como parámetros a estimar.
3. Escribir los parámetros en términos de esperanzas.
4. Estimar las esperanzas con los momentos muestrales y reemplazar.

### Distribución muestral de $\bar{X}$
Sea $X$ v.a. con $EX = \mu$ y $V(X) = \sigma^2$. Sea $X_1, \dots, X_n$ m.a. de $X$. El estimador de $\mu$ por Método de los Momentos es $\hat{\mu} = \bar{X}$. Se sabe que:
$$E(\bar{X}) = \mu \qquad V(\bar{X}) = \frac{\sigma^2}{n}$$

Respecto a la distribución de $\bar{X}$:
- Si $X_1, \dots, X_n$ iid con distribución **Normal** $\Rightarrow \bar{X} \sim$ **Normal exacta**, por T. de Combinaciones Lineales.
- Si $X_1, \dots, X_n$ iid con **otra distribución** y $n$ suficientemente grande $\Rightarrow \bar{X} \approx$ **Normal**, por TCL.

Estas son buenas propiedades de $\bar{X}$ como estimador de $\mu$.

### Distribución muestral de $\hat{\sigma}^2$
Por el Método de los Momentos se obtiene como estimador de $\sigma^2$:
$$\hat{\sigma}^2 = \frac{1}{n}\sum_{i=1}^{n}(X_i - \bar{X})^2$$
Se puede probar que:
$$E(\hat{\sigma}^2) = \left(1 - \frac{1}{n}\right)\sigma^2$$
por lo que es **sesgado** (su esperanza no coincide con $\sigma^2$).

Para obtener un estimador **insesgado** de $\sigma^2$ se define:
$$s^2 = \frac{n\,\hat{\sigma}^2}{n-1} = \frac{1}{n-1}\sum_{i=1}^{n}(X_i - \bar{X})^2$$
con lo que $E(s^2) = \sigma^2$.

Un estimador insesgado para la desviación estándar $\sigma$ sería:
$$s = \sqrt{s^2} = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(X_i - \bar{X})^2}$$

> [!note] Observación
> Aunque $s^2$ es insesgado para $\sigma^2$, al tomar la raíz cuadrada la propiedad no se conserva: $E(s) \neq \sigma$. Es decir, $s$ es un estimador **sesgado** de $\sigma$. Sin embargo, se utiliza igual porque es la mejor opción práctica disponible.

## Estimación por intervalos
La estimación puntual difícilmente coincide exactamente con el verdadero parámetro. La **estimación por intervalos** da un rango de valores donde se espera que esté el parámetro con un cierto grado de certeza.

### Definición: Intervalo de confianza
Sea $X_1, \dots, X_n$ una m.a. de $X$ con FDA $F_X(x, \theta)$, y sea $\theta$ el parámetro a estimar. Un **intervalo de $(1-\alpha)100\%$ de confianza para $\theta$** es un par de v.a. $\hat{\theta}_1$ y $\hat{\theta}_2$, funciones de la muestra, tales que:
$$P(\hat{\theta}_1 \leq \theta \leq \hat{\theta}_2) = 1 - \alpha$$

### Interpretación
Un intervalo del 95% de confianza significa: si se tomaran 100 muestras distintas y se construyera el intervalo en cada una, aproximadamente **95 de esos intervalos contendrían el verdadero valor de $\theta$**.

<div align="center">
<svg width="380" height="220" xmlns="http://www.w3.org/2000/svg">
  <!-- Curva Normal esquemática -->
  <path d="M 60,170 Q 100,165 130,140 Q 160,100 190,55 Q 220,100 250,140 Q 280,165 320,170" 
        stroke="#c0392b" stroke-width="2" fill="none"/>
  <!-- Línea vertical theta -->
  <line x1="190" y1="170" x2="190" y2="45" stroke="#1a6fa8" stroke-width="2" stroke-dasharray="5,3"/>
  <text x="190" y="185" text-anchor="middle" font-size="13" fill="#1a6fa8">θ</text>
  <!-- Zona central 95% -->
  <text x="190" y="90" text-anchor="middle" font-size="11" fill="#c0392b">95%</text>
  <text x="100" y="165" text-anchor="middle" font-size="10" fill="#555">2.5%</text>
  <text x="280" y="165" text-anchor="middle" font-size="10" fill="#555">2.5%</text>
  <!-- Intervalos: varios, uno no contiene theta -->
  <line x1="130" y1="170" x2="370" y2="170" stroke="#888" stroke-width="1"/>
  <!-- IC 1 contiene theta -->
  <line x1="155" y1="195" x2="230" y2="195" stroke="#27ae60" stroke-width="2.5"/>
  <circle cx="155" cy="195" r="3" fill="#27ae60"/><circle cx="230" cy="195" r="3" fill="#27ae60"/>
  <!-- IC 2 -->
  <line x1="148" y1="203" x2="225" y2="203" stroke="#27ae60" stroke-width="2.5"/>
  <circle cx="148" cy="203" r="3" fill="#27ae60"/><circle cx="225" cy="203" r="3" fill="#27ae60"/>
  <!-- IC 3 no contiene theta -->
  <line x1="210" y1="211" x2="310" y2="211" stroke="#c0392b" stroke-width="2.5"/>
  <circle cx="210" cy="211" r="3" fill="#c0392b"/><circle cx="310" cy="211" r="3" fill="#c0392b"/>
  <!-- IC 4 -->
  <line x1="160" y1="219" x2="240" y2="219" stroke="#27ae60" stroke-width="2.5"/>
  <circle cx="160" cy="219" r="3" fill="#27ae60"/><circle cx="240" cy="219" r="3" fill="#27ae60"/>
</svg>
</div>

> [!note] Importante
> $\theta$ es un número fijo desconocido, no es aleatorio. Lo que cambia de muestra en muestra son los extremos del intervalo $\hat{\theta}_1$ y $\hat{\theta}_2$. El intervalo en rojo es el que no contiene al verdadero $\theta$.

### IC para $\mu$ con $\sigma$ conocido
Sea $X_1, \dots, X_n$ m.a. de $X \sim N(\mu, \sigma)$ con $\sigma$ **conocido**.

**Estadístico pivote:**
$$\frac{\bar{X} - \mu}{\sigma/\sqrt{n}} \sim N(0,1)$$

**Cálculo auxiliar:**
$$P\!\left(-z_{1-\alpha/2} < \frac{\bar{X}-\mu}{\sigma/\sqrt{n}} < z_{1-\alpha/2}\right) = 1-\alpha$$
$$P\!\left(-z_{1-\alpha/2}\frac{\sigma}{\sqrt{n}} < \bar{X}-\mu < z_{1-\alpha/2}\frac{\sigma}{\sqrt{n}}\right) = 1-\alpha$$
$$P\!\left(\bar{X} - z_{1-\alpha/2}\frac{\sigma}{\sqrt{n}} < \mu < \bar{X} + z_{1-\alpha/2}\frac{\sigma}{\sqrt{n}}\right) = 1-\alpha$$

**Intervalo del $(1-\alpha)100\%$ de confianza para $\mu$:**
$$\bar{X} \pm z_{1-\alpha/2}\frac{\sigma}{\sqrt{n}}$$

> [!note] Nota
> Si $n$ es suficientemente grande no hace falta suponer distribución Normal. El intervalo tiene la misma forma pero es **aproximado**, ya que $\bar{X} \approx N(\mu, \sigma/\sqrt{n})$ por TCL.

---

### IC para $\mu$ con $\sigma$ desconocido — Distribución t de Student
Sea $X_1, \dots, X_n$ m.a. de $X \sim N(\mu, \sigma)$ con $\sigma$ **desconocido**.

No se puede usar el pivote anterior porque $\sigma$ es desconocido. Se estima con $s = \sqrt{\dfrac{1}{n-1}\sum(X_i-\bar{X})^2}$, y entonces:

**Estadístico pivote:**
$$\frac{\bar{X} - \mu}{s/\sqrt{n}} \sim t_{(n-1)}$$

donde $t_{(n-1)}$ es la **distribución t de Student con $n-1$ grados de libertad**.

**Propiedades de la t de Student:**
- Simétrica alrededor de cero, forma similar a la Normal.
- Tiene **mayor varianza** que la $N(0,1)$ (colas más pesadas).
- A medida que $n$ crece, se aproxima a la $N(0,1)$.
- Para $n > 120$ son prácticamente iguales.

**Cálculo auxiliar:**
$$P\!\left(-t_{1-\alpha/2}^{(n-1)} < \frac{\bar{X}-\mu}{s/\sqrt{n}} < t_{1-\alpha/2}^{(n-1)}\right) = 1-\alpha$$
$$P\!\left(-t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}} < \bar{X}-\mu < t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}}\right) = 1-\alpha$$
$$P\!\left(\bar{X} - t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}} < \mu < \bar{X} + t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}}\right) = 1-\alpha$$

**Intervalo del $(1-\alpha)100\%$ de confianza para $\mu$:**
$$\bar{X} \pm t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}}$$

> [!note] ¿Cuándo usar cada uno?
> - $\sigma$ **conocido** → pivote $N(0,1)$
> - $\sigma$ **desconocido** → pivote $t_{(n-1)}$ ← caso habitual en la práctica
> - $\sigma$ desconocido pero $n > 120$ → se puede usar $N(0,1)$ como aproximación

### IC para la diferencia de medias $\mu_X - \mu_Y$
Se tienen **dos poblaciones independientes** con la misma varianza $\sigma$ desconocida:
$$X_1, \dots, X_n \text{ m.a. de } X \sim N(\mu_X, \sigma) \qquad Y_1, \dots, Y_m \text{ m.a. de } Y \sim N(\mu_Y, \sigma)$$

El estimador natural de $\mu_X - \mu_Y$ es $\bar{X} - \bar{Y}$. Por el T. de Combinaciones Lineales:
$$E(\bar{X} - \bar{Y}) = \mu_X - \mu_Y \qquad V(\bar{X} - \bar{Y}) = \frac{\sigma^2}{n} + \frac{\sigma^2}{m} = \sigma^2\!\left(\frac{1}{n}+\frac{1}{m}\right)$$

Como $\sigma$ es desconocido pero **común** a ambas poblaciones, se estima combinando ambas muestras con la **varianza pooled**:
$$s_p^2 = \frac{(n-1)s_X^2 + (m-1)s_Y^2}{n + m - 2}$$

> [!note] ¿Por qué pooled?
> En general $s_X^2 \neq s_Y^2$ porque provienen de muestras distintas, pero se sabe por información adicional que el $\sigma$ poblacional es el mismo. Entonces conviene combinar toda la información disponible en un único estimador de $\sigma^2$ en lugar de usar solo una de las dos.

**Estadístico pivote:**
$$\frac{\bar{X} - \bar{Y} - (\mu_X - \mu_Y)}{s_p\sqrt{\dfrac{1}{n}+\dfrac{1}{m}}} \sim t_{(n+m-2)}$$

**Cálculo auxiliar:**
$$P\!\left(-t_{1-\alpha/2}^{(n+m-2)} < \frac{\bar{X}-\bar{Y}-(\mu_X-\mu_Y)}{s_p\sqrt{\frac{1}{n}+\frac{1}{m}}} < t_{1-\alpha/2}^{(n+m-2)}\right) = 1-\alpha$$

$$P\!\left(-t_{1-\alpha/2}^{(n+m-2)}\, s_p\sqrt{\tfrac{1}{n}+\tfrac{1}{m}} < \bar{X}-\bar{Y}-(\mu_X-\mu_Y) < t_{1-\alpha/2}^{(n+m-2)}\, s_p\sqrt{\tfrac{1}{n}+\tfrac{1}{m}}\right) = 1-\alpha$$

$$P\!\left(\bar{X}-\bar{Y} - t_{1-\alpha/2}^{(n+m-2)}\, s_p\sqrt{\tfrac{1}{n}+\tfrac{1}{m}} < \mu_X-\mu_Y < \bar{X}-\bar{Y} + t_{1-\alpha/2}^{(n+m-2)}\, s_p\sqrt{\tfrac{1}{n}+\tfrac{1}{m}}\right) = 1-\alpha$$

**Intervalo del $(1-\alpha)100\%$ de confianza para $\mu_X - \mu_Y$:**
$$(\bar{X} - \bar{Y}) \pm t_{1-\alpha/2}^{(n+m-2)}\; s_p\sqrt{\frac{1}{n}+\frac{1}{m}}$$

> [!note] Interpretación del intervalo
> - Si el intervalo **no contiene al 0**: las medias son distintas ($\mu_X \neq \mu_Y$).
> - Si el intervalo **contiene al 0**: no hay evidencia suficiente para afirmar que las medias difieren.

> [!note] Observaciones generales sobre IC
> 1. Mayor confiabilidad $(1-\alpha)$ → intervalo más ancho → menor precisión.
> 2. Mayor precisión → menor confiabilidad.
> 3. Para mayor precisión **sin** perder confiabilidad → aumentar el tamaño muestral $n$ y/o $m$.

### IC para la proporción $p$ (muestras grandes)
Se tiene una población Bernoulli: cada observación vale 1 (éxito) o 0 (fracaso) con probabilidad $p$ desconocida. Se quiere estimar $p$.

Sean $X_1, \dots, X_n$ m.a. de $X \sim B(p)$, con $n$ suficientemente grande.

El estimador natural de $p$ es $\bar{X}$ (proporción muestral). Por TCL:

**Estadístico pivote:**
$$\frac{\bar{X} - p}{\sqrt{\dfrac{p(1-p)}{n}}} \approx N(0,1)$$

**Cálculo auxiliar:**
$$P\!\left(-z_{1-\alpha/2} < \frac{\bar{X}-p}{\sqrt{\frac{p(1-p)}{n}}} < z_{1-\alpha/2}\right) = 1-\alpha$$

$$P\!\left(\bar{X} - \sqrt{\frac{p(1-p)}{n}}\,z_{1-\alpha/2} < p < \bar{X} + \sqrt{\frac{p(1-p)}{n}}\,z_{1-\alpha/2}\right) = 1-\alpha$$

$$IC_{(1-\alpha)100\%} = \bar{X} \pm z_{1-\alpha/2}\sqrt{\frac{p(1-p)}{n}}$$

Pero el intervalo **depende de $p$**, que es justamente lo que se quiere estimar. Se reemplaza $p$ por su estimador $\hat{p} = \bar{X}$:

**Intervalo aproximado del $(1-\alpha)100\%$ de confianza para $p$:**
$$\bar{X} \pm z_{1-\alpha/2}\sqrt{\frac{\bar{X}(1-\bar{X})}{n}}$$

> [!note] Diferencias con los casos anteriores
> - En el IC para $\mu$ con $\sigma$ conocido: el pivote es **exactamente** $N(0,1)$ (si $X \sim N$).
> - En el IC para $\mu$ con $\sigma$ desconocido: se usa $t_{(n-1)}$ para compensar la incertidumbre de estimar $\sigma$.
> - En el IC para $p$: el pivote es **aproximadamente** $N(0,1)$ por TCL, y además se reemplaza $p$ por $\hat{p}$ en el desvío. Por eso el intervalo es doblemente aproximado. Solo es válido para $n$ grande.

