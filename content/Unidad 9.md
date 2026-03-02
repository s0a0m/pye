## Unidad 9: Regresión Lineal Simple

Se estudia la relación entre dos variables para **observar una y predecir la otra**. La variable independiente $x$ es fija y controlada; la variable dependiente $Y$ es aleatoria.

### Modelo de Regresión Lineal Simple (M.R.L.S.)

$$Y_i = \alpha + \beta x_i + \varepsilon_i \qquad 1 \leq i \leq n$$

donde los errores $\varepsilon_i$ cumplen:
- $E(\varepsilon_i) = 0$ (media cero)
- $V(\varepsilon_i) = \sigma^2$ (varianza constante)
- $\text{Cov}(\varepsilon_i, \varepsilon_j) = 0$ para $i \neq j$ (no correlación)

$\alpha$, $\beta$ y $\sigma^2$ son los **parámetros a estimar**.

> [!note] Interpretación de los parámetros
> - $\beta$: cuánto **aumenta en promedio** $Y$ cuando $x$ aumenta una unidad. Es el parámetro más importante.
> - $\alpha$: valor promedio de $Y$ cuando $x = 0$ (solo tiene sentido si $x=0$ es un valor razonable).

De las hipótesis del modelo se deduce que:
$$E(Y_i) = \alpha + \beta x_i \qquad V(Y_i) = \sigma^2$$

### Método de Mínimos Cuadrados

El primer paso es construir el **diagrama de dispersión** para verificar visualmente si la relación es razonable linealizar.

Se quiere predecir $Y_i$ con $\hat{Y}_i = \hat{\alpha} + \hat{\beta} x_i$. El **residuo** de cada observación es:
$$e_i = y_i - \hat{y}_i$$

El Método de Mínimos Cuadrados busca $\hat{\alpha}$ y $\hat{\beta}$ que minimicen la suma de cuadrados de los residuos:
$$h(\hat{\alpha}, \hat{\beta}) = \sum_{i=1}^{n} e_i^2 = \sum_{i=1}^{n} \left[y_i - (\hat{\alpha} + \hat{\beta} x_i)\right]^2$$

Derivando e igualando a cero se obtienen las **ecuaciones normales**, cuya solución es:

$$\hat{\beta} = \frac{\sum x_i y_i - n\bar{x}\bar{y}}{\sum x_i^2 - n\bar{x}^2} = \frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{\sum(x_i - \bar{x})^2}$$

$$\hat{\alpha} = \bar{y} - \hat{\beta}\bar{x}$$

**Estimación de $\sigma^2$** (estimador insesgado):
$$\hat{\sigma}^2 = \frac{\sum_{i=1}^n e_i^2}{n-2} \qquad \text{Atajo: } \hat{\sigma}^2 = \frac{n}{n-2}(1-R^2)\hat{\sigma}^2_y$$

---

### Diagnóstico del modelo

El diagnóstico tiene dos etapas que **deben cumplirse ambas**:

#### Validez del modelo
Se verifica que las hipótesis del modelo se cumplan mediante el **análisis de residuos**: gráfico de $e_i$ vs $\hat{y}_i$ (o vs $x_i$).

Las hipótesis a chequear son: linealidad, $E(\varepsilon_i)=0$, $V(\varepsilon_i)=cte$ y $\text{Cov}(\varepsilon_i,\varepsilon_j)=0$.

<div align="center">
<svg width="520" height="195" xmlns="http://www.w3.org/2000/svg">

  <!-- GRAFICO 1: Correcto -->
  <rect x="10" y="5" width="150" height="120" fill="white" stroke="#aaa" stroke-width="1"/>
  <line x1="10" y1="65" x2="160" y2="65" stroke="#999" stroke-width="0.8" stroke-dasharray="3,2"/>
  <circle cx="30"  cy="55" r="3" fill="#2980b9"/>
  <circle cx="45"  cy="75" r="3" fill="#2980b9"/>
  <circle cx="60"  cy="48" r="3" fill="#2980b9"/>
  <circle cx="75"  cy="70" r="3" fill="#2980b9"/>
  <circle cx="90"  cy="58" r="3" fill="#2980b9"/>
  <circle cx="105" cy="78" r="3" fill="#2980b9"/>
  <circle cx="120" cy="52" r="3" fill="#2980b9"/>
  <circle cx="135" cy="68" r="3" fill="#2980b9"/>
  <text x="85" y="140" text-anchor="middle" font-size="10" fill="#27ae60">Correcto</text>
  <text x="85" y="152" text-anchor="middle" font-size="9" fill="#555">Puntos aleatoriamente</text>
  <text x="85" y="163" text-anchor="middle" font-size="9" fill="#555">dispersos alrededor de 0</text>

  <!-- GRAFICO 2: Varianza no constante -->
  <rect x="185" y="5" width="150" height="120" fill="white" stroke="#aaa" stroke-width="1"/>
  <line x1="185" y1="65" x2="335" y2="65" stroke="#999" stroke-width="0.8" stroke-dasharray="3,2"/>
  <circle cx="205" cy="63" r="3" fill="#e74c3c"/>
  <circle cx="220" cy="67" r="3" fill="#e74c3c"/>
  <circle cx="235" cy="55" r="3" fill="#e74c3c"/>
  <circle cx="250" cy="75" r="3" fill="#e74c3c"/>
  <circle cx="265" cy="40" r="3" fill="#e74c3c"/>
  <circle cx="280" cy="90" r="3" fill="#e74c3c"/>
  <circle cx="295" cy="25" r="3" fill="#e74c3c"/>
  <circle cx="310" cy="105" r="3" fill="#e74c3c"/>
  <text x="260" y="140" text-anchor="middle" font-size="10" fill="#e74c3c">Varianza no constante</text>
  <text x="260" y="152" text-anchor="middle" font-size="9" fill="#555">Dispersion crece con</text>
  <text x="260" y="163" text-anchor="middle" font-size="9" fill="#555">y estimado (embudo)</text>

  <!-- GRAFICO 3: Correlacion -->
  <rect x="360" y="5" width="150" height="120" fill="white" stroke="#aaa" stroke-width="1"/>
  <line x1="360" y1="65" x2="510" y2="65" stroke="#999" stroke-width="0.8" stroke-dasharray="3,2"/>
  <circle cx="380" cy="45" r="3" fill="#8e44ad"/>
  <circle cx="395" cy="48" r="3" fill="#8e44ad"/>
  <circle cx="410" cy="55" r="3" fill="#8e44ad"/>
  <circle cx="425" cy="65" r="3" fill="#8e44ad"/>
  <circle cx="440" cy="75" r="3" fill="#8e44ad"/>
  <circle cx="455" cy="82" r="3" fill="#8e44ad"/>
  <circle cx="470" cy="88" r="3" fill="#8e44ad"/>
  <circle cx="485" cy="95" r="3" fill="#8e44ad"/>
  <text x="435" y="140" text-anchor="middle" font-size="10" fill="#8e44ad">Correlacion</text>
  <text x="435" y="152" text-anchor="middle" font-size="9" fill="#555">Patron sistematico:</text>
  <text x="435" y="163" text-anchor="middle" font-size="9" fill="#555">los residuos no son independientes</text>

</svg>
</div>

#### Bondad del ajuste
Mide qué proporción de la variabilidad total de $Y$ es explicada por el modelo. Se puede probar que:

$$\underbrace{\sum(y_i - \bar{y})^2}_{\text{variabilidad total}} = \underbrace{\sum(y_i - \hat{y}_i)^2}_{\text{no explicada}} + \underbrace{\sum(\hat{y}_i - \bar{y})^2}_{\text{explicada por la recta}}$$

El **coeficiente de determinación** $R^2$ se define como:
$$R^2 = 1 - \frac{\sum e_i^2}{\sum(y_i - \bar{y})^2} = \frac{\sum(\hat{y}_i - \bar{y})^2}{\sum(y_i - \bar{y})^2}$$

$R^2 \in [0, 1]$. Cuanto más próximo a 1, mejor el ajuste. Es igual al cuadrado del coeficiente de correlación $r^2$.

> [!note] Validez ≠ Bondad
> Un modelo puede tener $R^2$ alto (buen ajuste) pero no ser válido si los residuos muestran patrones. **Ambas condiciones deben cumplirse.**
> - Modelo válido + $R^2$ alto → modelo útil.
> - Modelo no válido + $R^2$ alto → el ajuste numérico es bueno pero las predicciones no son confiables.

