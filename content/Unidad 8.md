## Test de Hipótesis

### Hipótesis estadística

Una **hipótesis estadística** es una afirmación sobre el valor de un parámetro de una población.

**Hipótesis nula $H_0$:** la hipótesis que se mantiene como válida hasta que los datos indiquen su falsedad. Siempre se expresa con una **igualdad** (simple).

**Hipótesis alternativa $H_1$:** la hipótesis que se toma como cierta si $H_0$ se rechaza. Puede ser simple o compuesta.

> [!note] Importante $H_0$ nunca puede ser "probada". Solo se la rechaza o no hay evidencia suficiente para rechazarla.

### Clasificación de hipótesis

Según **cuántas poblaciones** se refieren:

- **Referidas a 1 población:** sobre el valor de 1 parámetro en 1 población.
- **Referidas a 2 poblaciones:** comparan cierto parámetro entre 2 poblaciones.

Según **cómo se definen:**

- **Simples:** quedan definidas con una igualdad. _Ejemplo: $H_0: \mu = \mu_0$_
- **Compuestas:** quedan definidas con un intervalo o unión de intervalos. _Ejemplo: $H_1: \mu \neq \mu_0$ (unión de dos intervalos) ó $\mu > \mu_0$ ó $\mu < \mu_0$_

> [!note] Convención del curso La hipótesis nula $H_0$ se toma **siempre como simple** (expresada con una igualdad), mientras que la alternativa $H_1$ puede ser simple o compuesta.

### Definición de test de hipótesis

Un **test o prueba de hipótesis** es una regla que especifica:

- Para qué valores del estadístico (calculado de la muestra) se **acepta $H_0$**.
- Para qué valores del estadístico se **rechaza $H_0$** y se acepta $H_1$.

El subconjunto del espacio muestral para el cual $H_0$ es rechazada se llama **región de rechazo** o **región crítica**. Su complemento es la **región de aceptación**.

La región de rechazo depende de $\alpha$ (**nivel de significancia**): la probabilidad de rechazar $H_0$ cuando $H_0$ es verdadera. Cuanto más chico $\alpha$, más significativo es el test.

### Toma de decisión según $H_1$

Donde $H_0: \mu = \mu_0$

#### Test de 2 colas: $H_1: \mu \neq \mu_0$

Se rechaza $H_0$ si el estadístico cae en cualquiera de los dos extremos.

<div align="center"> <svg width="360" height="130" xmlns="http://www.w3.org/2000/svg"> <!-- Curva normal --> <path d="M 20,110 Q 60,108 90,90 Q 120,60 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 260,90 Q 290,108 320,110 L 340,110" stroke="#333" stroke-width="1.5" fill="none"/> <!-- Región rechazo izquierda --> <path d="M 20,110 Q 60,108 90,90 Q 100,80 110,110 Z" fill="#e74c3c" opacity="0.6"/> <!-- Región rechazo derecha --> <path d="M 250,110 Q 260,90 290,108 Q 320,110 340,110 Z" fill="#e74c3c" opacity="0.6"/> <!-- Región aceptación --> <path d="M 110,110 Q 120,60 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 250,110 Z" fill="#2ecc71" opacity="0.3"/> <!-- Eje --> <line x1="20" y1="110" x2="345" y2="110" stroke="black" stroke-width="1"/> <!-- Etiquetas --> <text x="65" y="107" text-anchor="middle" font-size="11" fill="#e74c3c">α/2</text> <text x="180" y="75" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="295" y="107" text-anchor="middle" font-size="11" fill="#e74c3c">α/2</text> <text x="110" y="125" text-anchor="middle" font-size="10">-z</text> <text x="250" y="125" text-anchor="middle" font-size="10">z</text> </svg> </div>

#### Test de 1 cola derecha: $H_1: \mu > \mu_0$

Se rechaza $H_0$ si el estadístico es demasiado grande.

<div align="center"> <svg width="360" height="130" xmlns="http://www.w3.org/2000/svg"> <path d="M 20,110 Q 60,108 90,90 Q 120,60 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 260,90 Q 290,108 320,110 L 340,110" stroke="#333" stroke-width="1.5" fill="none"/> <!-- Región rechazo derecha --> <path d="M 260,90 Q 290,108 320,110 L 340,110 L 340,110 Q 310,110 260,90 Z" fill="#e74c3c" opacity="0.6"/> <!-- Región aceptación --> <path d="M 20,110 Q 60,108 90,90 Q 120,60 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 260,90 L 260,110 Z" fill="#2ecc71" opacity="0.3"/> <line x1="20" y1="110" x2="345" y2="110" stroke="black" stroke-width="1"/> <text x="150" y="80" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="305" y="107" text-anchor="middle" font-size="11" fill="#e74c3c">α</text> <text x="260" y="125" text-anchor="middle" font-size="10">z</text> </svg> </div>

#### Test de 1 cola izquierda: $H_1: \mu < \mu_0$

Se rechaza $H_0$ si el estadístico es demasiado pequeño.

<div align="center"> <svg width="360" height="130" xmlns="http://www.w3.org/2000/svg"> <path d="M 20,110 Q 60,108 90,90 Q 120,60 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 260,90 Q 290,108 320,110 L 340,110" stroke="#333" stroke-width="1.5" fill="none"/> <!-- Región rechazo izquierda --> <path d="M 20,110 Q 60,108 90,90 L 100,110 Z" fill="#e74c3c" opacity="0.6"/> <!-- Región aceptación --> <path d="M 100,110 Q 110,80 140,25 Q 160,5 180,3 Q 200,5 220,25 Q 240,60 260,90 Q 290,108 320,110 L 340,110 L 340,110 Z" fill="#2ecc71" opacity="0.3"/> <line x1="20" y1="110" x2="345" y2="110" stroke="black" stroke-width="1"/> <text x="55" y="107" text-anchor="middle" font-size="11" fill="#e74c3c">α</text> <text x="220" y="75" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="100" y="125" text-anchor="middle" font-size="10">-z</text> </svg> </div>

> [!note] Recomendación En general se recomienda usar un **test de 2 colas** salvo que haya razones claras para usar uno de 1 cola.

---

## Metodología para hacer un test

### Paso 1: Definir $H_0$ y $H_1$

$$H_0: \mu = \mu_0 \qquad H_1: \mu \neq \mu_0 \quad \text{ó} \quad \mu > \mu_0 \quad \text{ó} \quad \mu < \mu_0$$

### Paso 2: Definir el estadístico y su distribución bajo $H_0$

La forma general del estadístico es:

$$\text{Estadístico} = \frac{\text{Estimador} - \text{Parámetro bajo } H_0}{\text{Desvío estándar del estimador}}$$

Por ejemplo para $\mu$: $$t_{obs} = \frac{\bar{x} - \mu_0}{s/\sqrt{n}} \sim t_{(n-1)} \quad (\sigma \text{ desconocido})$$

$$z_{obs} = \frac{\bar{x} - \mu_0}{\sigma/\sqrt{n}} \sim N(0,1) \quad (\sigma \text{ conocido})$$

### Paso 3a: Región crítica y decisión

|$H_1$|$t$ crítico|Región de rechazo|
|---|---|---|
|$\mu \neq \mu_0$|$t_{1-\alpha/2}^{(n-1)}$|$\|t_{obs}\| > t_{crit}$|
|$\mu > \mu_0$|$t_{1-\alpha}^{(n-1)}$|$t_{obs} > t_{crit}$|
|$\mu < \mu_0$|$t_{\alpha}^{(n-1)}$|$t_{obs} < t_{crit}$|

#### Test de 2 colas: $H_1: \mu \neq \mu_0$

<div align="center"> <svg width="360" height="140" xmlns="http://www.w3.org/2000/svg"> <path d="M 20,115 Q 60,113 90,95 Q 120,65 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 260,95 Q 290,113 320,115 L 340,115" stroke="#333" stroke-width="1.5" fill="none"/> <path d="M 20,115 Q 50,113 80,100 Q 90,93 100,115 Z" fill="#e74c3c" opacity="0.7"/> <path d="M 260,95 Q 280,110 310,114 L 340,115 L 260,115 Z" fill="#e74c3c" opacity="0.7"/> <path d="M 100,115 Q 110,85 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 260,95 L 260,115 Z" fill="#2ecc71" opacity="0.25"/> <line x1="20" y1="115" x2="345" y2="115" stroke="black" stroke-width="1"/> <line x1="100" y1="115" x2="100" y2="95" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <line x1="260" y1="115" x2="260" y2="95" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <text x="55" y="112" text-anchor="middle" font-size="11" fill="#e74c3c">α/2</text> <text x="180" y="72" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="305" y="112" text-anchor="middle" font-size="11" fill="#e74c3c">α/2</text> <text x="100" y="130" text-anchor="middle" font-size="10">-t crit</text> <text x="260" y="130" text-anchor="middle" font-size="10">t crit</text> <text x="55" y="140" font-size="9" fill="#e74c3c" text-anchor="middle">Rechazo</text> <text x="305" y="140" font-size="9" fill="#e74c3c" text-anchor="middle">Rechazo</text> </svg> </div>

#### Test de 1 cola derecha: $H_1: \mu > \mu_0$

<div align="center"> <svg width="360" height="140" xmlns="http://www.w3.org/2000/svg"> <path d="M 20,115 Q 60,113 90,95 Q 120,65 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 260,95 Q 290,113 320,115 L 340,115" stroke="#333" stroke-width="1.5" fill="none"/> <path d="M 265,93 Q 285,110 310,114 L 340,115 L 265,115 Z" fill="#e74c3c" opacity="0.7"/> <path d="M 20,115 Q 60,113 90,95 Q 120,65 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 265,93 L 265,115 Z" fill="#2ecc71" opacity="0.25"/> <line x1="20" y1="115" x2="345" y2="115" stroke="black" stroke-width="1"/> <line x1="265" y1="115" x2="265" y2="93" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <text x="150" y="80" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="308" y="112" text-anchor="middle" font-size="11" fill="#e74c3c">α</text> <text x="265" y="130" text-anchor="middle" font-size="10">t crit</text> <text x="308" y="140" font-size="9" fill="#e74c3c" text-anchor="middle">Rechazo</text> </svg> </div>

#### Test de 1 cola izquierda: $H_1: \mu < \mu_0$

<div align="center"> <svg width="360" height="140" xmlns="http://www.w3.org/2000/svg"> <path d="M 20,115 Q 60,113 90,95 Q 120,65 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 260,95 Q 290,113 320,115 L 340,115" stroke="#333" stroke-width="1.5" fill="none"/> <path d="M 20,115 Q 50,113 80,100 Q 90,93 95,115 Z" fill="#e74c3c" opacity="0.7"/> <path d="M 95,115 Q 100,90 140,30 Q 160,8 180,6 Q 200,8 220,30 Q 240,65 260,95 Q 290,113 320,115 L 340,115 Z" fill="#2ecc71" opacity="0.25"/> <line x1="20" y1="115" x2="345" y2="115" stroke="black" stroke-width="1"/> <line x1="95" y1="115" x2="95" y2="95" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <text x="52" y="112" text-anchor="middle" font-size="11" fill="#e74c3c">α</text> <text x="220" y="75" text-anchor="middle" font-size="11" fill="#27ae60">1-α</text> <text x="95" y="130" text-anchor="middle" font-size="10">-t crit</text> <text x="50" y="140" font-size="9" fill="#e74c3c" text-anchor="middle">Rechazo</text> </svg> </div>

---

### Paso 3b: Valor p (forma alternativa)

El **valor p** es la probabilidad de obtener un estadístico tan extremo o más extremo que el observado, asumiendo $H_0$ verdadera.

|$H_1$|Valor p|
|---|---|
|$\mu \neq \mu_0$|$P(\|t\| > \|t_{obs}\|)$|
|$\mu > \mu_0$|$P(t > t_{obs})$|
|$\mu < \mu_0$|$P(t < t_{obs})$|

**Decisión con valor p:**

- Valor p $< 0.01$ ó $0.05$ (pequeño) $\Rightarrow$ se **rechaza $H_0$**
- Valor p $> 0.01$ ó $0.05$ (grande) $\Rightarrow$ **no hay evidencia suficiente** para rechazar $H_0$

<div align="center"> <svg width="500" height="145" xmlns="http://www.w3.org/2000/svg"> <!-- Curva izquierda: valor p grande --> <path d="M 20,115 Q 50,113 75,95 Q 95,70 110,40 Q 120,20 130,15 Q 140,10 150,8 Q 160,10 170,20 Q 185,40 200,90 Q 210,113 230,115" stroke="#333" stroke-width="1.5" fill="none"/> <path d="M 155,115 Q 158,70 170,20 Q 185,40 200,90 Q 210,113 230,115 Z" fill="#2ecc71" opacity="0.5"/> <line x1="20" y1="115" x2="235" y2="115" stroke="black" stroke-width="1"/> <line x1="155" y1="115" x2="155" y2="60" stroke="#555" stroke-width="1.5" stroke-dasharray="4,2"/> <text x="193" y="100" font-size="9" fill="#27ae60">valor p</text> <text x="193" y="110" font-size="9" fill="#27ae60">grande</text> <text x="125" y="135" font-size="9" text-anchor="middle">No rechazo H0</text> <text x="155" y="130" font-size="9" text-anchor="middle">t obs</text> <!-- Curva derecha: valor p pequeño --> <path d="M 270,115 Q 300,113 325,95 Q 345,70 360,40 Q 370,20 380,15 Q 390,10 400,8 Q 410,10 420,20 Q 435,40 450,90 Q 460,113 480,115" stroke="#333" stroke-width="1.5" fill="none"/> <path d="M 445,115 Q 448,88 455,70 Q 462,50 480,115 Z" fill="#e74c3c" opacity="0.6"/> <line x1="270" y1="115" x2="485" y2="115" stroke="black" stroke-width="1"/> <line x1="445" y1="115" x2="445" y2="85" stroke="#555" stroke-width="1.5" stroke-dasharray="4,2"/> <text x="463" y="100" font-size="9" fill="#e74c3c">valor p</text> <text x="463" y="110" font-size="9" fill="#e74c3c">pequeño</text> <text x="375" y="135" font-size="9" text-anchor="middle">Rechazo H0</text> <text x="445" y="130" font-size="9" text-anchor="middle">t obs</text> </svg> </div>

> [!note] Los dos caminos llevan a la misma decisión Usar región crítica o valor p son métodos equivalentes. La ventaja del valor p es que cuantifica **cuánta** evidencia hay contra $H_0$: un valor p = 0.001 es evidencia mucho más fuerte que un valor p = 0.048, aunque ambos rechacen con $\alpha = 0.05$.

---

## Test para una población

### Test para la media $\mu$ en población Normal

Se aplica en dos casos:

- **Caso 1:** $X_1, \dots, X_n$ iid como $X \sim N(\mu, \sigma)$ con $\sigma$ desconocido $\Rightarrow$ distribución **exacta**.
- **Caso 2:** $X_1, \dots, X_n$ iid como $X \sim F_X$ cualquiera, con $EX = \mu$, $V(X) = \sigma^2$ desconocido, y $n$ grande $\Rightarrow$ distribución **aproximada** por TCL.

**Estadístico:** $$t_{obs} = \frac{\bar{x} - \mu_0}{s/\sqrt{n}} \sim t_{(n-1)}$$

**Región de rechazo según $H_1$:**

|$H_1$|$t$ crítico|Región de rechazo|
|---|---|---|
|$\mu \neq \mu_0$|$t_{1-\alpha/2}^{(n-1)}$|$\|t_{obs}\| > t_{crit}$|
|$\mu > \mu_0$|$t_{1-\alpha}^{(n-1)}$|$t_{obs} > t_{crit}$|
|$\mu < \mu_0$|$t_{\alpha}^{(n-1)}$|$t_{obs} < t_{crit}$|

---

### Test para la proporción $p$ en población Bernoulli

$X_1, \dots, X_n$ iid como $X \sim B(p)$, $p$ desconocido, $n$ grande para aplicar TCL.

Como $EX = p$, se usa $\bar{X}$ como estimador de $p$.

**Estadístico:** $$z_{obs} = \frac{\bar{x} - p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}} \approx N(0,1)$$

> [!note] Diferencia clave con el test de media En el test de media se usa $s$ (estimado de los datos) en el denominador. En el test de proporción se usa $p_0$ (el valor bajo $H_0$), **no** $\bar{x}$, porque bajo $H_0$ asumís que $p = p_0$ es conocido. Por eso el pivote es Normal y no t de Student.

**Región de rechazo según $H_1$:**

|$H_1$|$z$ crítico|Región de rechazo|
|---|---|---|
|$p \neq p_0$|$z_{1-\alpha/2}$|$\|z_{obs}\| > z_{crit}$|
|$p > p_0$|$z_{1-\alpha}$|$z_{obs} > z_{crit}$|
|$p < p_0$|$z_{\alpha}$|$z_{obs} < z_{crit}$|

---

### Observaciones generales

> [!note] Observaciones
> 
> - Cuando los datos no dan suficiente evidencia para rechazar $H_0$, ésta **no se puede rechazar**. Los datos no dan suficiente evidencia cuando el valor observado del estadístico es un valor de alta probabilidad (valor p grande), o equivalentemente cuando **no cae en la región de rechazo**.
> - Todos los procedimientos de test son similares: **solo cambian los estadísticos** a utilizar.
> - Decir que se "acepta $H_0$" es decir en realidad que **no hay evidencia suficiente para rechazarla**. En base a datos (información parcial) no es posible demostrar que sea verdadera.

---

## Test para dos poblaciones

### Test para diferencia de medias — poblaciones independientes

$$X_1, \dots, X_n \text{ iid } \sim N(\mu_X, \sigma) \qquad Y_1, \dots, Y_m \text{ iid } \sim N(\mu_Y, \sigma)$$

Independientes entre sí, $\sigma$ **común** desconocido.

**1. Hipótesis:** $$H_0: \mu_X = \mu_Y \qquad H_1: \mu_X \neq \mu_Y \quad \text{ó} \quad \mu_X > \mu_Y \quad \text{ó} \quad \mu_X < \mu_Y$$

**2. Estadístico** (usando varianza pooled):

$$s_p^2 = \frac{(n-1)s_X^2 + (m-1)s_Y^2}{n+m-2}$$

$$t_{obs} = \frac{\bar{X} - \bar{Y} - (\mu_X - \mu_Y)}{s_p\sqrt{\frac{1}{n}+\frac{1}{m}}} \sim t_{(n+m-2)}$$

Bajo $H_0: \mu_X = \mu_Y$:

$$t_{obs} = \frac{\bar{X} - \bar{Y}}{s_p\sqrt{\frac{1}{n}+\frac{1}{m}}} \sim t_{(n+m-2)}$$

**3. Región de rechazo según $H_1$:**

|$H_1$|$t$ crítico|Región de rechazo|
|---|---|---|
|$\mu_X \neq \mu_Y$|$t_{1-\alpha/2}^{(n+m-2)}$|$\|t_{obs}\| > t_{crit}$|
|$\mu_X > \mu_Y$|$t_{1-\alpha}^{(n+m-2)}$|$t_{obs} > t_{crit}$|
|$\mu_X < \mu_Y$|$t_{\alpha}^{(n+m-2)}$|$t_{obs} < t_{crit}$|

---

### Test para medias pareadas — poblaciones dependientes

Se usa cuando **la misma población es observada en dos momentos o situaciones diferentes**. Por ejemplo: peso antes y después de un tratamiento, producción de una máquina con y sin ajuste.

$$X_1^1, \dots, X_n^1 \text{ m.a. de } X_1 \sim N(\mu_1, \sigma) \qquad X_1^2, \dots, X_n^2 \text{ m.a. de } X_2 \sim N(\mu_2, \sigma)$$

Dependientes entre sí, $\sigma$ común.

Se define la **diferencia** para cada par: $$D_i = X_i^1 - X_i^2 \qquad \Rightarrow \qquad D_1, \dots, D_n \text{ iid } \sim N(\mu_D, \sigma_D)$$

El problema se **reduce a un test de una media** sobre las diferencias.

**1. Hipótesis** (en general con $\mu_{D_0} = 0$): $$H_0: \mu_D = 0 \qquad H_1: \mu_D \neq 0 \quad \text{ó} \quad \mu_D > 0 \quad \text{ó} \quad \mu_D < 0$$

**2. Estadístico:** $$t_{obs} = \frac{\bar{d} - \mu_{D_0}}{s_D/\sqrt{n}} \sim t_{(n-1)}$$

**3. Región de rechazo:** análoga al test de una media con $t_{(n-1)}$.

> [!note] ¿Cuándo usar pareadas vs independientes?
> 
> - **Pareadas:** misma unidad medida dos veces (antes/después, con/sin tratamiento). Las muestras tienen el **mismo tamaño** $n$.
> - **Independientes:** dos grupos distintos. Pueden tener tamaños $n$ y $m$ diferentes. Usar pareadas cuando corresponde elimina la variabilidad entre individuos y hace el test más potente.

---

### Test para diferencia de proporciones — poblaciones Bernoulli

$$X_1, \dots, X_n \text{ iid } \sim B(p_X) \qquad Y_1, \dots, Y_m \text{ iid } \sim B(p_Y)$$

Independientes entre sí, $n$ y $m$ suficientemente grandes (TCL).

**1. Hipótesis:** $$H_0: p_X = p_Y \qquad H_1: p_X \neq p_Y \quad \text{ó} \quad p_X > p_Y \quad \text{ó} \quad p_X < p_Y$$

**2. Estadístico:** bajo $H_0$ se asume $p_X = p_Y = p$, se estima con la **proporción combinada**:

$$\hat{p} = \frac{n\bar{X} + m\bar{Y}}{n + m} \qquad \hat{q} = 1 - \hat{p}$$

$$z_{obs} = \frac{\bar{X} - \bar{Y}}{\sqrt{\hat{p}\hat{q}\left(\frac{1}{n}+\frac{1}{m}\right)}} \approx N(0,1)$$

> [!note] ¿Por qué se usa $\hat{p}$ combinado? Bajo $H_0$ asumís que $p_X = p_Y$, es decir que ambas poblaciones tienen la misma proporción. Entonces lo más eficiente es estimar ese $p$ común usando **todos** los datos juntos, no cada muestra por separado.

**3. Región de rechazo según $H_1$:**

|$H_1$|$z$ crítico|Región de rechazo|
|---|---|---|
|$p_X \neq p_Y$|$z_{1-\alpha/2}$|$\|z_{obs}\| > z_{crit}$|
|$p_X > p_Y$|$z_{1-\alpha}$|$z_{obs} > z_{crit}$|
|$p_X < p_Y$|$z_{\alpha}$|$z_{obs} < z_{crit}$|

---

## Test de Hipótesis vs Intervalo de Confianza

En general, **cada IC corresponde a un test de hipótesis y viceversa**. La región de aceptación del test puede pensarse como un IC en versión estandarizada. El nivel de significancia $\alpha$ del test corresponde al nivel de confianza $(1-\alpha)$ del IC.

### Caso: media con $\sigma$ desconocido

Sean $X_1, \dots, X_n$ iid $\sim N(\mu, \sigma)$, $\sigma$ desconocido. Ambos métodos se basan en el mismo estadístico:

$$\frac{\bar{X} - \mu_0}{s/\sqrt{n}} \sim t_{(n-1)}$$

El test $H_0: \mu = \mu_0$ vs $H_1: \mu \neq \mu_0$ a nivel $\alpha$ es **equivalente** a calcular el $IC_{(1-\alpha)100%}$ para $\mu$.

**Regla de decisión por IC:**

> [!note] Conclusión Si $\mu_0 \notin IC_{1-\alpha}$ $\Rightarrow$ hay suficiente evidencia para **rechazar $H_0$**. Si $\mu_0 \in IC_{1-\alpha}$ $\Rightarrow$ **no hay evidencia suficiente** para rechazar $H_0$.

**¿Por qué funciona?** La región de aceptación del test es: $$-t_{1-\alpha/2}^{(n-1)} < \frac{\bar{x} - \mu_0}{s/\sqrt{n}} < t_{1-\alpha/2}^{(n-1)}$$

Despejando $\mu_0$, esto equivale exactamente a: $$\bar{x} - t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}} < \mu_0 < \bar{x} + t_{1-\alpha/2}^{(n-1)}\frac{s}{\sqrt{n}}$$

que es justamente el $IC_{(1-\alpha)100%}$ para $\mu$. Son la misma expresión.

<div align="center"> <svg width="420" height="130" xmlns="http://www.w3.org/2000/svg"> <!-- Curva --> <path d="M 30,105 Q 70,103 100,85 Q 130,55 150,22 Q 165,5 180,3 Q 195,5 210,22 Q 230,55 250,85 Q 280,103 320,105 L 350,105" stroke="#333" stroke-width="1.5" fill="none"/> <!-- Región rechazo izq --> <path d="M 30,105 Q 60,103 85,90 Q 95,82 105,105 Z" fill="#e74c3c" opacity="0.7"/> <!-- Región rechazo der --> <path d="M 255,83 Q 275,100 305,104 L 340,105 L 255,105 Z" fill="#e74c3c" opacity="0.7"/> <!-- Región aceptación = IC --> <path d="M 105,105 Q 115,75 150,22 Q 165,5 180,3 Q 195,5 210,22 Q 230,55 255,83 L 255,105 Z" fill="#2ecc71" opacity="0.25"/> <line x1="30" y1="105" x2="355" y2="105" stroke="black" stroke-width="1"/> <line x1="105" y1="105" x2="105" y2="85" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <line x1="255" y1="105" x2="255" y2="83" stroke="#e74c3c" stroke-width="1.5" stroke-dasharray="4,2"/> <!-- Etiquetas --> <text x="55" y="102" text-anchor="middle" font-size="10" fill="#e74c3c">α/2</text> <text x="180" y="65" text-anchor="middle" font-size="10" fill="#27ae60">Región de aceptación</text> <text x="180" y="78" text-anchor="middle" font-size="10" fill="#27ae60">= IC(1-α)%</text> <text x="310" y="102" text-anchor="middle" font-size="10" fill="#e74c3c">α/2</text> <text x="105" y="120" text-anchor="middle" font-size="9">-t crit</text> <text x="255" y="120" text-anchor="middle" font-size="9">t crit</text> <!-- mu0 dentro --> <line x1="190" y1="105" x2="190" y2="40" stroke="#1a6fa8" stroke-width="1.5" stroke-dasharray="3,2"/> <text x="190" y="125" text-anchor="middle" font-size="9" fill="#1a6fa8">μ0 dentro: no rechazo</text> </svg> </div>

### Región de aceptación para la proporción $p = p_0$

$$\hat{p} - z_{1-\alpha/2}\sqrt{\frac{\hat{p}(1-\hat{p})}{n}} \leq p \leq \hat{p} + z_{1-\alpha/2}\sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$$

### Región de aceptación para la diferencia de medias $\mu_X - \mu_Y$

$$(\bar{x}-\bar{y}) - t_{1-\alpha/2}^{(n+m-2)}, s_p\sqrt{\frac{1}{n}+\frac{1}{m}} \leq \mu_X - \mu_Y \leq (\bar{x}-\bar{y}) + t_{1-\alpha/2}^{(n+m-2)}, s_p\sqrt{\frac{1}{n}+\frac{1}{m}}$$

> [!note] Ventaja del IC sobre el test El IC no solo dice si rechazás o no $H_0$, sino que además **muestra un rango de valores plausibles** para el parámetro. Aporta más información que la simple decisión binaria del test.

---

## Errores al realizar un test de Hipótesis

Al tomar una decisión con datos (información parcial) se pueden cometer dos tipos de errores:

|Decisión|$H_0$ Verdadera|$H_0$ Falsa|
|---|---|---|
|**Aceptar $H_0$**|Decisión correcta|Error Tipo II — $\beta$|
|**Rechazar $H_0$**|Error Tipo I — $\alpha$|Decisión correcta|

**Error Tipo I** = $P(\text{Rechazar } H_0 \mid H_0 \text{ verdadera}) = \alpha$

Es el nivel de significación del test. **Se controla directamente** eligiendo $\alpha$.

**Error Tipo II** = $P(\text{Aceptar } H_0 \mid H_0 \text{ falsa}) = \beta$

Para calcularlo se necesita conocer el valor específico de $H_1$.

> [!note] Observaciones
> 
> 1. Cuando $\alpha \downarrow \Rightarrow \beta \uparrow$: reducir el error tipo I aumenta el error tipo II y viceversa. Son errores que compiten. La única forma de reducir ambos simultáneamente es **aumentar $n$**.
> 2. **Potencia del test** $= 1 - \beta = P(\text{Rechazar } H_0 \mid H_0 \text{ falsa})$. Es la probabilidad de detectar correctamente que $H_0$ es falsa. Un test potente rechaza $H_0$ cuando debe rechazarla.
> 3. Es preferible informar el **valor p** en lugar de fijar un $\alpha$, pues así se sabe cuán lejos o cerca se está de rechazar $H_0$.
> 4. Aceptar $H_0$ significa en realidad que **no hay evidencia suficiente para rechazarla**. En base a datos (información parcial) no es posible demostrar que sea verdadera.