## Unidad 11: ANOVA — Análisis de la Varianza

### Motivación

Hasta la unidad 8 se comparaban medias de **1 o 2 poblaciones**. Cuando hay más de dos niveles de un factor (tratamientos), necesitamos $k$ muestras y el procedimiento se llama **Análisis de la Varianza (ANOVA)**.

> [!note] ¿Por qué no hacer muchos tests de a pares?
> Si hacemos $\binom{k}{2}$ tests de a pares con nivel $\alpha$ cada uno, el nivel real de error crece rápidamente. ANOVA controla el error global con un único test.

### Hipótesis

$$H_0: \mu_1 = \mu_2 = \dots = \mu_k$$
$$H_1: \text{Al menos una media es diferente}$$

**Condiciones para que el ANOVA sea válido:**
- Normalidad de los datos para cada nivel del factor.
- Varianza $\sigma$ común (desconocida) en todos los grupos.
- Independencia entre muestras.

### La idea central

Se tienen $k$ muestras de tamaño $n$ cada una ($N = kn$ datos en total):

<div align="center">
<svg width="420" height="130" xmlns="http://www.w3.org/2000/svg">
  <!-- Cajas de grupos -->
  <rect x="20"  y="15" width="80" height="90" fill="#dbeafe" stroke="#2980b9" stroke-width="1.2" rx="4"/>
  <rect x="170" y="15" width="80" height="90" fill="#dbeafe" stroke="#2980b9" stroke-width="1.2" rx="4"/>
  <rect x="320" y="15" width="80" height="90" fill="#dbeafe" stroke="#2980b9" stroke-width="1.2" rx="4"/>
  <!-- Puntos dentro -->
  <circle cx="60" cy="35" r="3" fill="#2980b9"/><circle cx="60" cy="50" r="3" fill="#2980b9"/>
  <circle cx="60" cy="65" r="3" fill="#2980b9"/><circle cx="60" cy="80" r="3" fill="#2980b9"/>
  <circle cx="210" cy="35" r="3" fill="#2980b9"/><circle cx="210" cy="50" r="3" fill="#2980b9"/>
  <circle cx="210" cy="65" r="3" fill="#2980b9"/><circle cx="210" cy="80" r="3" fill="#2980b9"/>
  <circle cx="360" cy="35" r="3" fill="#2980b9"/><circle cx="360" cy="50" r="3" fill="#2980b9"/>
  <circle cx="360" cy="65" r="3" fill="#2980b9"/><circle cx="360" cy="80" r="3" fill="#2980b9"/>
  <!-- Medias -->
  <line x1="25" y1="60" x2="95" y2="60" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/>
  <line x1="175" y1="45" x2="245" y2="45" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/>
  <line x1="325" y1="72" x2="395" y2="72" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/>
  <!-- Labels -->
  <text x="60"  y="118" text-anchor="middle" font-size="11">Muestra 1</text>
  <text x="210" y="118" text-anchor="middle" font-size="11">Muestra 2</text>
  <text x="360" y="118" text-anchor="middle" font-size="11">Muestra k</text>
  <text x="60"  y="10"  text-anchor="middle" font-size="9" fill="#e74c3c">y-barra 1</text>
  <text x="210" y="10"  text-anchor="middle" font-size="9" fill="#e74c3c">y-barra 2</text>
  <text x="360" y="10"  text-anchor="middle" font-size="9" fill="#e74c3c">y-barra k</text>
  <!-- Flechas variabilidad -->
  <text x="130" y="60" text-anchor="middle" font-size="9" fill="#555">. . .</text>
  <text x="280" y="60" text-anchor="middle" font-size="9" fill="#555">. . .</text>
  <!-- Etiquetas variabilidad -->
  <text x="210" y="130" text-anchor="middle" font-size="9" fill="#27ae60">variabilidad ENTRE tratamientos (SSA)</text>
</svg>
</div>

La lógica es comparar dos tipos de variabilidad:

- **SSA** (Sum of Squares Among): variabilidad **entre** grupos, es decir cuánto difieren las medias $\bar{y}_{i.}$ entre sí respecto a la gran media $\bar{\bar{y}}$.
- **SSE** (Sum of Squares Error): variabilidad **dentro** de cada grupo, es decir cuánto varían los datos alrededor de su propia media.

$$SSA = n\sum_{i=1}^{k}(\bar{y}_{i.} - \bar{\bar{y}})^2 \qquad \bar{y}_{i.} = \frac{1}{n}\sum_{j=1}^{n}y_{ij}$$

$$SSE = \sum_{i=1}^{k}\sum_{j=1}^{n}(y_{ij} - \bar{y}_{i.})^2 \qquad \bar{\bar{y}} = \frac{1}{kn}\sum_{i=1}^{k}\sum_{j=1}^{n}y_{ij}$$

> [!note] Intuición del estadístico F
> Si las medias son iguales ($H_0$ verdadera), la variabilidad entre grupos debería ser similar a la de dentro. Si $H_1$ es verdadera, SSA será grande respecto a SSE y F será grande.
>
> - Variabilidad **DENTRO** chica y **ENTRE** grande $\Rightarrow$ $F$ grande $\Rightarrow$ **rechazo** $H_0$
> - Variabilidad **DENTRO** grande y **ENTRE** chica $\Rightarrow$ $F$ chico $\Rightarrow$ **acepto** $H_0$

### Estadístico y distribución

$$F_{obs} = \frac{SSA/(k-1)}{SSE/(n-1)k} \sim F_{k-1,\,(n-1)k}$$

La distribución $F$ **no es simétrica** y depende de los grados de libertad del numerador y denominador.

**Región de rechazo:** $F_{obs} > F_{k-1,\,(n-1)k;\,(1-\alpha)}$

**Valor p:** $P(F_{k-1,\,(n-1)k} > F_{obs})$

### Tabla del ANOVA

<div align="center">
  <table>
    <thead>
      <tr style="background-color:#1a6fa8; color:white;">
        <th>Fuente de Variación</th>
        <th>Grados de libertad</th>
        <th>Suma de Cuadrados</th>
        <th>Cuadrados medios</th>
        <th>F</th>
        <th>Valor p</th>
      </tr>
    </thead>
    <tbody>
      <tr style="background-color:#daeaf5;">
        <td>Tratamiento</td>
        <td>$k-1$</td>
        <td>$SSA$</td>
        <td>$SSA/(k-1)$</td>
        <td rowspan="2" style="vertical-align:middle; text-align:center;">$\dfrac{SSA/(k-1)}{SSE/(n-1)k}$</td>
        <td rowspan="2" style="vertical-align:middle; text-align:center;">$P(F > F_{obs})$</td>
      </tr>
      <tr style="background-color:#eaf4fb;">
        <td>Error</td>
        <td>$(n-1)k$</td>
        <td>$SSE$</td>
        <td>$SSE/(n-1)k$</td>
      </tr>
      <tr style="background-color:#daeaf5;">
        <td><strong>Total</strong></td>
        <td>$Nk-1$</td>
        <td>$SST$</td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </tbody>
  </table>
</div>

En este curso **no se calcula el estadístico a mano**, se interpreta la salida de computadora.

### Comparaciones múltiples o de a pares

Si se rechaza $H_0$, se quiere saber **cuál/es de las medias son distintas**. Se utilizan métodos que mantienen el nivel $\alpha$ global:

- **Tukey y Duncan**: comparan de a pares **todas** las medias entre sí.
- **Dunnett**: compara todas las medias contra **un grupo control**.

La salida de Tukey da un intervalo de confianza para cada diferencia $\mu_i - \mu_j$. Si el intervalo **no contiene el 0**, esas dos medias son significativamente distintas.

*Ejemplo de salida de Minitab:*
```
Tukey's pairwise comparisons
           1        2        3        4
2    -135.3
      103.3
3    -176.5  -160.5
       62.2    78.2
4     -31.2   -15.2    26.0
      207.5   223.5   264.7
5    -176.7  -160.7  -119.5  -264.8
       62.0    78.0   119.2   -26.2
```
Cada celda muestra el IC para $\mu_{col} - \mu_{fil}$. Las únicas que **no contienen el 0** son las de los pares (3,4) y (4,5): esas medias son diferentes entre sí.