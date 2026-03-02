## Unidad 10: Control de Calidad

### Procesos bajo control

Un **proceso** es una serie repetible de pasos que conduce a un resultado. Todo proceso tiene variabilidad, que puede ser de dos tipos:

<div align="center">
  <table>
    <thead>
      <tr>
        <th style="background-color:#7d5ba6; color:white;">Causas NO asignables</th>
        <th style="background-color:#3aafa9; color:white;">Causas asignables</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Muchas, cada una de pequeña importancia</td>
        <td>Pocas, pero de fuertes efectos</td>
      </tr>
      <tr>
        <td>Producen variabilidad estable</td>
        <td>Producen variabilidad impredecible</td>
      </tr>
      <tr>
        <td>Difícil reducir sus efectos</td>
        <td>Sus efectos desaparecen al eliminar la causa</td>
      </tr>
      <tr>
        <td>Errores <strong>accidentales o aleatorios</strong></td>
        <td>Errores <strong>sistemáticos</strong></td>
      </tr>
      <tr>
        <td>Ej: calidad de materia prima, habilidad del operario, clima</td>
        <td>Ej: desajuste de máquina, lotes defectuosos, errores humanos</td>
      </tr>
    </tbody>
  </table>
</div>

Se dice que un proceso está **bajo control** cuando se han eliminado todas las causas asignables, de modo que la variabilidad sea debida solo a causas no asignables. En ese caso $X \sim N(\mu, \sigma)$.

> [!note] Corrección vs cambio de proceso
> Eliminar una causa asignable **no cambia el proceso**, solo lo restaura. Reducir la variabilidad por causas no asignables sí **implica un cambio en el proceso** (por ejemplo, clasificar la materia prima antes de fabricar).

---

### Intervalos de tolerancia y Capacidad del Proceso

El **intervalo de tolerancia** $(LT_1, LT_2)$ es el conjunto de valores admisibles. Lo fija la empresa. Es simétrico respecto de $\mu$ (valor nominal).

La **capacidad del proceso** se define como:
$$CP = 6\hat{\sigma}$$

Representa el ancho del intervalo natural del proceso: el 99.7% de las unidades fabricadas caen en $(\mu - 3\sigma,\ \mu + 3\sigma)$.

El **índice de capacidad** relaciona la tolerancia con la capacidad:
$$\hat{IC} = \frac{LT_2 - LT_1}{6\hat{\sigma}}$$

| $\hat{IC}$ | Interpretación |
|---|---|
| $< 1$ | Proporción de defectuosos muy elevada ($>0.3\%$). Proceso **no adecuado** |
| $\approx 1$ | Proporción $\approx 0.3\%$. Hoy se considera insuficiente |
| $> 1$ | Proporción $< 0.3\%$. Proceso **adecuado** |

---

### Determinación de la Capacidad del Proceso

Se toman $k$ muestras de tamaño $n$ igualmente espaciadas. La estimación de $\sigma$ se hace con:
$$\hat{\sigma} = \frac{\bar{s}}{c_2}$$

donde $\bar{s}$ es el promedio de las desviaciones estándar muestrales y $c_2$ es un coeficiente tabulado en función de $n$.

**Paso 1 — Homogeneidad para las desviaciones** (banda del 99%):
$$(B_3 \bar{s},\ B_4 \bar{s})$$

$B_3$ y $B_4$ se obtienen de tabla según $n$. Si alguna $s_i$ cae fuera: se descarta esa muestra y se recalcula.

**Paso 2 — Homogeneidad para las medias** (banda del 99.7%):
$$\left(\bar{\bar{X}} - 3\frac{\hat{\sigma}}{c_2\sqrt{n}},\ \bar{\bar{X}} + 3\frac{\hat{\sigma}}{c_2\sqrt{n}}\right)$$

Si alguna $\bar{x}_i$ cae fuera: se descarta y se recalcula.

**Paso 3** — Si todas las muestras quedan dentro de ambas bandas, se chequea normalidad y se estima $\hat{IC}$.

---

### Gráficos de Control (Control de fabricación)

Una vez estimada la capacidad, se construyen los gráficos para monitorear el proceso en el tiempo.

**Gráfico de control para la media** — banda del 99.7%:

<div align="center">
<svg width="420" height="130" xmlns="http://www.w3.org/2000/svg">
  <!-- Banda -->
  <rect x="50" y="20" width="350" height="90" fill="#f0f8ff" stroke="#aaa" stroke-width="1"/>
  <!-- Línea central -->
  <line x1="50" y1="65" x2="400" y2="65" stroke="#1a6fa8" stroke-width="1.5"/>
  <!-- Límite superior -->
  <line x1="50" y1="25" x2="400" y2="25" stroke="#e74c3c" stroke-width="1.2" stroke-dasharray="5,3"/>
  <!-- Límite inferior -->
  <line x1="50" y1="105" x2="400" y2="105" stroke="#e74c3c" stroke-width="1.2" stroke-dasharray="5,3"/>
  <!-- Etiquetas -->
  <text x="10" y="28" font-size="10" fill="#e74c3c">LSC</text>
  <text x="10" y="68" font-size="10" fill="#1a6fa8">X doble barra</text>
  <text x="10" y="108" font-size="10" fill="#e74c3c">LIC</text>
  <!-- Puntos dentro -->
  <circle cx="80"  cy="55" r="4" fill="#2980b9"/>
  <circle cx="120" cy="75" r="4" fill="#2980b9"/>
  <circle cx="160" cy="50" r="4" fill="#2980b9"/>
  <circle cx="200" cy="70" r="4" fill="#2980b9"/>
  <circle cx="240" cy="60" r="4" fill="#2980b9"/>
  <circle cx="280" cy="80" r="4" fill="#2980b9"/>
  <circle cx="320" cy="55" r="4" fill="#2980b9"/>
  <!-- Punto fuera -->
  <circle cx="360" cy="18" r="4" fill="#e74c3c"/>
  <line x1="80" y1="55" x2="120" y2="75" stroke="#2980b9" stroke-width="1"/>
  <line x1="120" y1="75" x2="160" y2="50" stroke="#2980b9" stroke-width="1"/>
  <line x1="160" y1="50" x2="200" y2="70" stroke="#2980b9" stroke-width="1"/>
  <line x1="200" y1="70" x2="240" y2="60" stroke="#2980b9" stroke-width="1"/>
  <line x1="240" y1="60" x2="280" y2="80" stroke="#2980b9" stroke-width="1"/>
  <line x1="280" y1="80" x2="320" y2="55" stroke="#2980b9" stroke-width="1"/>
  <line x1="320" y1="55" x2="360" y2="18" stroke="#e74c3c" stroke-width="1"/>
</svg>
</div>

$$LSC = \bar{\bar{X}} + 3\frac{\hat{\sigma}}{c_2\sqrt{n}} \qquad LIC = \bar{\bar{X}} - 3\frac{\hat{\sigma}}{c_2\sqrt{n}}$$

**Gráfico de control para las desviaciones** — banda del 99%:
$$LSC = B_4\hat{\sigma} \qquad LIC = B_3\hat{\sigma}$$

---

### Interpretación de los gráficos de control

Un punto fuera de banda es señal de alarma, pero también los **patrones dentro de banda**:

**a) Cambio brusco** — un punto extremo indica cambio en la media (solo gráfico de medias) o en la varianza (ambos gráficos).

**b) Tendencia o racha** — 7 puntos consecutivos por encima de la línea central, o en orden creciente/decreciente, indica anormalidad aunque estén dentro de banda.

<div align="center">
<svg width="350" height="90" xmlns="http://www.w3.org/2000/svg">
  <rect x="30" y="5" width="310" height="75" fill="#fff9f0" stroke="#aaa" stroke-width="1"/>
  <line x1="30" y1="42" x2="340" y2="42" stroke="#1a6fa8" stroke-width="1.2" stroke-dasharray="4,2"/>
  <line x1="30" y1="10" x2="340" y2="10" stroke="#e74c3c" stroke-width="1" stroke-dasharray="4,2"/>
  <line x1="30" y1="75" x2="340" y2="75" stroke="#e74c3c" stroke-width="1" stroke-dasharray="4,2"/>
  <circle cx="60"  cy="55" r="3.5" fill="#e67e22"/>
  <circle cx="95"  cy="52" r="3.5" fill="#e67e22"/>
  <circle cx="130" cy="49" r="3.5" fill="#e67e22"/>
  <circle cx="165" cy="45" r="3.5" fill="#e67e22"/>
  <circle cx="200" cy="42" r="3.5" fill="#e67e22"/>
  <circle cx="235" cy="38" r="3.5" fill="#e67e22"/>
  <circle cx="270" cy="34" r="3.5" fill="#e67e22"/>
  <line x1="60" y1="55" x2="270" y2="34" stroke="#e67e22" stroke-width="1"/>
  <text x="185" y="88" font-size="10" fill="#e67e22" text-anchor="middle">Tendencia — proceso fuera de control</text>
</svg>
</div>

**c) Inestabilidad** — grandes fluctuaciones. Puede deberse a materias primas mezcladas o falta de entrenamiento del operario.

**d) Periodicidad** — patrón cíclico. Puede deberse a diferencias entre turnos o lotes de materia prima.

**e) Sobreestabilidad** — variabilidad menor a la esperada. Puede ser positivo (mejora real) o negativo (datos tomados incorrectamente o límites mal calculados). Se detecta cuando más del 68% de los puntos se concentran en la zona central del intervalo.