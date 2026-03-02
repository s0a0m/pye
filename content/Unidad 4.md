### Distribución Bernoulli
Esta situación se modela con una Distribución de Bernoulli: $X \sim \beta(p)$ 
- Sea $X$ v.a. tal que $R_x = \{0,1\}$, $p_x(1) = p$; $p_x(0) = 1-p$ con $0 \leq p \leq 1$ 
- Lo que es lo mismo $p_x(x) = p^x(1-p)^{1-x}$ con $x = 0, 1$
- $EX = p$, $V(X) = p(1-p)$
#### hipótesis
1. El proceso consiste en un numero fijo de repeticiones de un experimento (ensayo).
2. En cada repetición hay dos resultados posibles, éxito y fracaso.
3. La probabilidad de éxito se mantiene constante de repetición en repetición.
4. Los ensayos son independientes entre sí. Es decir que la probabilidad de éxito es siempre la misma ante cualquier combinación de éxitos y fracasos observados hasta esa repetición.
### Distribución Binomial
En un proceso de Bernoulli la v.a. Binomial $X \sim b(n,p)$: 
- $R_X = \{0, 1, 2, \dots, n\}$ 
- $p(x=k) = \binom{n}{k} p^k (1-p)^{n-k}$ con $k = 0,1,2,\dots,n$ donde $0! = 1$ 
- $EX = np$, $V(X) = np(1-p)$ 
- **Observación:** $X_1, X_2, \dots X_n$ v.a. donde cada $X_i \sim \beta(p)$, entonces $\sum_{i=1}^{n} X_i \sim b(n,p)$

### Distribución Geométrica
Distribución Geométrica $X \sim Ge(p)$:

- $X$ = "Número de ensayos Bernoulli hasta obtener el primer éxito"
- $R_X = \{1, 2, 3, \dots\}$
- $P(X = k) = (1-p)^{k-1} p$
- $EX = \dfrac{1}{p}$, $V(X) = \dfrac{1-p}{p^2}$
### Distribución de Poisson o caos homogéneo
- $X$ = "Número de sucesos en un intervalo $[0,t)$ de longitud fija, en un proceso de Poisson" 
- $R_X = \{0, 1, 2, \dots\}$ - $p_x(x) = P(X = x) = e^{-\lambda t} \dfrac{(\lambda t)^x}{x!} \quad x = 0,1,2,\dots$ 
- donde $\lambda > 0$ es el número promedio de partículas emitidas por unidad de tiempo 
- $EX = \lambda t$, $V(X) = \lambda t$ 
- **Hipótesis:** 
1. **Independencia:** el número de partículas emitidas en un intervalo es independiente del número emitidas en otro intervalo disjunto. 
2. **Homogeneidad y proporcionalidad:** la probabilidad de emitir una partícula en $[t, t+h)$ es $\lambda h + o(h)$, donde $\lambda$ es constante independiente de $t$ y $o(h)/h \to 0$ cuando $h \to 0$. 
3. **Regularidad:** la probabilidad de que en $[t, t+h)$ sean emitidas 2 o más partículas es despreciable cuando $h$ es pequeña.

<div align="center">
  <table style="border-collapse: collapse; max-width: 650px;">
    <thead>
      <tr style="background-color:#f5ea59; color:white;">
        <th style="padding: 10px; border: 1px solid #5a0a3a;">Hipótesis</th>
        <th style="padding: 10px; border: 1px solid #5a0a3a;">Significado</th>
        <th style="padding: 10px; border: 1px solid #5a0a3a;">Ejemplo</th>
      </tr>
    </thead>
    <tbody>
      <tr style="background-color:#f5eaf0;">
        <td style="padding: 10px; border: 1px solid #ccc;"><strong>Independencia</strong></td>
        <td style="padding: 10px; border: 1px solid #ccc;">Lo que ocurre en un intervalo no afecta lo que ocurre en otro intervalo disjunto.</td>
        <td style="padding: 10px; border: 1px solid #ccc;">Que lleguen 20 clientes entre las 10:00 y 10:30 no influye en cuántos llegan entre las 11:00 y 11:30.</td>
      </tr>
      <tr style="background-color:#ede0ea;">
        <td style="padding: 10px; border: 1px solid #ccc;"><strong>Homogeneidad y proporcionalidad</strong></td>
        <td style="padding: 10px; border: 1px solid #ccc;">La tasa λ es constante en el tiempo y la probabilidad de 1 evento en [t, t+h) es λh + o(h), donde o(h)/h → 0.</td>
        <td style="padding: 10px; border: 1px solid #ccc;">Si λ = 10 clientes/hora, en 30 min la probabilidad es proporcional a 10 × 0.5 = 5, independientemente de si es de mañana o de tarde.</td>
      </tr>
      <tr style="background-color:#f5eaf0;">
        <td style="padding: 10px; border: 1px solid #ccc;"><strong>Regularidad</strong></td>
        <td style="padding: 10px; border: 1px solid #ccc;">La probabilidad de 2 o más eventos en un intervalo muy pequeño es despreciable.</td>
        <td style="padding: 10px; border: 1px solid #ccc;">Es prácticamente imposible que 2 clientes lleguen exactamente en el mismo instante por la misma puerta.</td>
      </tr>
    </tbody>
  </table>
</div>
### Distribución normal
La v.a. $X$ tiene distribución normal si su función de densidad es:

$$f_x(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{1}{2\sigma^2}(x-\mu)^2} \quad -\infty < x < \infty$$
donde $\mu, \sigma$ son constantes tales que $-\infty < \mu < \infty$ y $\sigma > 0$.

Se puede demostrar que:

1. $f_X(x) > 0 \quad -\infty < x < \infty$
2. $\int_{-\infty}^{\infty} f_X(x) \, dx = 1$
3. $EX = \mu$ y $Var(X) = \sigma^2$
4. Notación: $X \sim N(\mu, \sigma)$
5. $X \sim N(\mu, \sigma)$ es simétrica alrededor de $\mu$
#### Distribución normal estándar
Cuando $\mu = 0$ y $\sigma = 1$, $X \sim N(0,1)$ se denota por $Z$.

- Su función de distribución acumulada se denota por $\phi$, es decir $\phi(Z) = P(Z \leq z)$
- Está tabulada
- Cualquier distribución normal puede ser transformada a una normal estándar.

**Resultado importante:** Si $X \sim N(\mu, \sigma)$ entonces la v.a.
$$Z = \frac{X - \mu}{\sigma} \sim N(0,1)$$
Se utiliza para el cálculo de probabilidades:
$$P(a < X \leq b) = P(a - \mu < X - \mu \leq b - \mu) = P\left(\frac{a-\mu}{\sigma} < \frac{X-\mu}{\sigma} \leq \frac{b-\mu}{\sigma}\right)$$
$$= \phi\left(\frac{b-\mu}{\sigma}\right) - \phi\left(\frac{a-\mu}{\sigma}\right)$$
### Distribución Exponencial 
$$f(x) = \begin{cases} \lambda e^{-\lambda x} & x > 0 \\ 0 & \text{en otro caso} \end{cases} \quad \text{donde } \lambda > 0$$
- $EX = \dfrac{1}{\lambda}$, $V(X) = \dfrac{1}{\lambda^2}$

#### Relación entre la exponencial y el proceso de Poisson
Sea $X \sim P(\lambda)$ "cantidad de sucesos en un tiempo $t$" y sea $T$ = "tiempo que transcurre hasta la primera ocurrencia". $T$ es continua y $R_T = [0, \infty)$. Sea $t \in [0, \infty)$: $$F_T(t) = P(T \leq t) = 1 - P(T > t) = 1 - P(\text{"no hay ocurrencias en } [0,t)\text{"})$$$$= 1 - P(X = 0) = 1 - e^{-\lambda t} \frac{(\lambda t)^0}{0!} = 1 - e^{-\lambda t}$$ Entonces: $$F_T'(t) = \lambda e^{-\lambda t} \quad t > 0$$ que es la función de densidad de la v.a. Exponencial, por lo tanto $T \sim Exp(\lambda)$.
### Distribución uniforme
$$f_x(x) = \begin{cases} \dfrac{1}{b-a} & a \leq x \leq b \\ 0 & \text{en otro caso} \end{cases}$$
- $f_X(x) \geq 0 \quad a \leq x \leq b$ 
- $\int_a^b f_X(x) \, dx = 1$ 
- $EX = \dfrac{a+b}{2}$, $V(X) = \dfrac{(b-a)^2}{12}$
