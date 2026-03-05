## Unidad 4: Distribuciones con nombre propio

### Distribución Bernoulli

Esta situación se modela con una Distribución de Bernoulli: $X \sim \beta(p)$

- Sea $X$ v.a. tal que $R_X = \{0,1\}$, $\quad p_X(1) = p;\quad p_X(0) = 1-p\quad$ con $0 \leq p \leq 1$
- Lo que es lo mismo: $p_X(x) = p^x(1-p)^{1-x}$ con $x = 0, 1$
- $EX = p, \quad V(X) = p(1-p)$

#### Proceso de Bernoulli — Hipótesis

1. El proceso consiste en un número fijo $n$ de repeticiones de un experimento (ensayos).
2. En cada repetición hay dos resultados posibles: éxito y fracaso.
3. La probabilidad de éxito $p$ se mantiene constante de repetición en repetición.
4. Los ensayos son independientes entre sí: la probabilidad de éxito es siempre la misma ante cualquier combinación de éxitos y fracasos observados hasta esa repetición.

---

### Distribución Binomial

En un proceso de Bernoulli, la v.a. Binomial $X \sim b(n,p)$ se define como $X =$ "Número de éxitos en $n$ ensayos de Bernoulli".

- $R_X = \{0, 1, 2, \dots, n\}$
- $P(X = k) = \dbinom{n}{k} p^k (1-p)^{n-k} \quad k = 0,1,2,\dots,n \quad$ donde $0! = 1$
- $EX = np, \quad V(X) = np(1-p)$

> [!note] Observación
> Si $X_1, X_2, \dots, X_n$ son v.a. independientes con cada $X_i \sim \beta(p)$, entonces $\displaystyle\sum_{i=1}^{n} X_i \sim b(n,p)$

---

### Distribución Geométrica

$X \sim Ge(p)$, donde $X =$ "Número de ensayos Bernoulli hasta obtener el primer éxito".

- $R_X = \{1, 2, 3, \dots\}$
- $P(X = k) = (1-p)^{k-1}\, p$
- $EX = \dfrac{1}{p}, \quad V(X) = \dfrac{1-p}{p^2}$

---

### Distribución de Poisson (Caos Homogéneo)

$X =$ "Número de sucesos en un intervalo $[0,t)$ de longitud fija, en un proceso de Poisson".

- $R_X = \{0, 1, 2, \dots\}$
- $p_X(x) = P(X = x) = e^{-\lambda t} \dfrac{(\lambda t)^x}{x!} \quad x = 0,1,2,\dots$
- $\lambda > 0$ es el número promedio de sucesos por unidad de tiempo
- $EX = \lambda t, \quad V(X) = \lambda t$

#### Hipótesis del proceso de Poisson

1. **Independencia:** el número de sucesos en un intervalo es independiente del número de sucesos en otro intervalo disjunto.
2. **Homogeneidad y proporcionalidad:** la probabilidad de que ocurra un suceso en $[t, t+h)$ es $\lambda h + o(h)$, donde $\lambda$ es constante independiente de $t$ y $o(h)/h \to 0$ cuando $h \to 0$.
3. **Regularidad:** la probabilidad de que en $[t, t+h)$ ocurran 2 o más sucesos es despreciable cuando $h$ es pequeña.

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Hipótesis</th>
        <th>Significado</th>
        <th>Ejemplo</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Independencia</strong></td>
        <td>Lo que ocurre en un intervalo no afecta lo que ocurre en otro intervalo disjunto.</td>
        <td>Que lleguen 20 clientes entre las 10:00 y 10:30 no influye en cuántos llegan entre las 11:00 y 11:30.</td>
      </tr>
      <tr>
        <td><strong>Homogeneidad y proporcionalidad</strong></td>
        <td>La tasa $\lambda$ es constante y la probabilidad de 1 evento en $[t, t+h)$ es $\lambda h + o(h)$.</td>
        <td>Si $\lambda = 10$ clientes/hora, en 30 min la probabilidad es proporcional a $10 \times 0.5 = 5$, independientemente de si es de mañana o de tarde.</td>
      </tr>
      <tr>
        <td><strong>Regularidad</strong></td>
        <td>La probabilidad de 2 o más eventos en un intervalo muy pequeño es despreciable.</td>
        <td>Es prácticamente imposible que 2 clientes lleguen exactamente en el mismo instante.</td>
      </tr>
    </tbody>
  </table>
</div>

---

### Distribución Normal

La v.a. $X$ tiene distribución normal si su función de densidad es:
$$f_X(x) = \frac{1}{\sqrt{2\pi}\,\sigma}\, e^{-\frac{1}{2\sigma^2}(x-\mu)^2} \qquad -\infty < x < \infty$$

donde $-\infty < \mu < \infty$ y $\sigma > 0$. Se puede demostrar que:

1. $f_X(x) > 0 \quad \forall x \in \mathbb{R}$
2. $\int_{-\infty}^{\infty} f_X(x)\,dx = 1$
3. $EX = \mu \quad$ y $\quad V(X) = \sigma^2$
4. Notación: $X \sim N(\mu, \sigma)$
5. $X \sim N(\mu, \sigma)$ es simétrica alrededor de $\mu$

#### Distribución normal estándar

Cuando $\mu = 0$ y $\sigma = 1$, $X \sim N(0,1)$ se denota por $Z$.

- Su f.d.a. se denota $\Phi$, es decir $\Phi(z) = P(Z \leq z)$
- Está tabulada
- Cualquier distribución normal puede transformarse a una normal estándar

**Resultado importante:** Si $X \sim N(\mu, \sigma)$ entonces $Z = \dfrac{X - \mu}{\sigma} \sim N(0,1)$

Se utiliza para el cálculo de probabilidades:
$$P(a < X \leq b) = \Phi\!\left(\frac{b-\mu}{\sigma}\right) - \Phi\!\left(\frac{a-\mu}{\sigma}\right)$$

---

### Distribución Exponencial

$$f_X(x) = \begin{cases} \lambda e^{-\lambda x} & x > 0 \\ 0 & \text{en otro caso} \end{cases} \qquad \lambda > 0$$

- $EX = \dfrac{1}{\lambda}, \quad V(X) = \dfrac{1}{\lambda^2}$

#### Relación entre la Exponencial y el proceso de Poisson

Sea $X \sim P(\lambda)$ "cantidad de sucesos en un tiempo $t$" y sea $T =$ "tiempo hasta la primera ocurrencia". $T$ es continua con $R_T = [0, \infty)$.

$$F_T(t) = P(T \leq t) = 1 - P(T > t) = 1 - P(\text{"no hay ocurrencias en } [0,t)\text{"})$$
$$= 1 - P(X = 0) = 1 - e^{-\lambda t}\frac{(\lambda t)^0}{0!} = 1 - e^{-\lambda t}$$

Entonces $F_T'(t) = \lambda e^{-\lambda t}$ para $t > 0$, que es la f.d.p. de la Exponencial, por lo tanto $T \sim Exp(\lambda)$.

---

### Distribución Uniforme

$$f_X(x) = \begin{cases} \dfrac{1}{b-a} & a \leq x \leq b \\ 0 & \text{en otro caso} \end{cases}$$

- $f_X(x) \geq 0 \quad \forall x \in [a,b]$
- $\int_a^b f_X(x)\,dx = 1$
- $EX = \dfrac{a+b}{2}, \quad V(X) = \dfrac{(b-a)^2}{12}$