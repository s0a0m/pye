Un **lote de datos** es una serie de mediciones de una o mas variables (características de interés)
### Variables cualitativas
Describen atributos y **no toman valores numéricos**. Hay de dos tipos:
1. **Escala ordinal**: tienen un orden natural como tamaño (pequeño, mediano, grande).
2. **Escala nominal**: No tienen un orden natural como nacionalidad.
### Variables cuantitativas
**Toman valores numéricos**. Hay de dos tipos:
1. **Discretas**: puede tomar número finito de valores o infinito numerable.  
2. **Continuas**: Pueden tomar valores en todo un intervalo.

### Distribuciones de frecuencia
Es una tabla donde se representa información resumida (columnas o categorías | cantidad). De cada dato solo se conoce a la clase a la que pertenece. Hay algunos tipos de casos:
1. Datos de variables cualitativas (nominal u ordinal). 

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Zona del daño</th>
        <th>Accidentes (fi)</th>
        <th>Porcentaje (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>Ojos</td><td>5</td><td>31%</td></tr>
      <tr><td>Manos</td><td>4</td><td>25%</td></tr>
      <tr><td>Brazos</td><td>3</td><td>19%</td></tr>
      <tr><td>Piernas</td><td>2</td><td>13%</td></tr>
      <tr><td>Pie</td><td>2</td><td>13%</td></tr>
      <tr><td><strong>Total</strong></td><td><strong>16</strong></td><td><strong>100%</strong></td></tr>
    </tbody>
  </table>
</div>

2. Datos de variables cuantitativas (discreta con pocos valores).

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Nº de Accidentes</th>
        <th>Cantidad de Intersecciones (fi)</th>
        <th>Porcentaje (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>0</td><td>3</td><td>30%</td></tr>
      <tr><td>1</td><td>2</td><td>20%</td></tr>
      <tr><td>2</td><td>2</td><td>20%</td></tr>
      <tr><td>3</td><td>2</td><td>20%</td></tr>
      <tr><td>4</td><td>1</td><td>10%</td></tr>
      <tr><td><strong>Total</strong></td><td><strong>10</strong></td><td><strong>100%</strong></td></tr>
    </tbody>
  </table>
</div>

3. Datos de variables cuantitativas (continua o discreta con muchos valores): Hay que construir clases subdividiendo el rango de datos en **subintervalos semiabiertos y disjuntos**. Para hacerlo con un **tamaño muestral** de n primero se saca el numero de clases con $1.75 \sqrt[3]{n}$ y la amplitud de cada clase será de $\frac{max - min}{num\ de\ clases}$. En lo posible elegir intervalos enteros y múltiplos de 5. Elegir los límites de los intervalos de manera que no haya clases vacías. *Ejemplo en la pagina 12 de unidad 1 pdf 1*.

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Tiempos en seg.</th>
        <th>Cantidad de Solicitudes (fi)</th>
        <th>Porcentaje (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>[10,15)</td><td>3</td><td>15%</td></tr>
      <tr><td>[15,20)</td><td>4</td><td>20%</td></tr>
      <tr><td>[20,25)</td><td>6</td><td>30%</td></tr>
      <tr><td>[25,30)</td><td>6</td><td>30%</td></tr>
      <tr><td>[30,35)</td><td>1</td><td>5%</td></tr>
      <tr><td><strong>Total</strong></td><td><strong>20</strong></td><td><strong>100%</strong></td></tr>
    </tbody>
  </table>
</div>

## Representación gráfica de datos
#### Diagrama de barras
- Datos de variables cualitativas.
- Datos de variables cuantitativas discretas con pocos valores.
- Se pueden graficar frecuencias absolutas, frecuencias relativas o porcentajes.

<p align="center"><strong>Accidentes mes de Noviembre 2000. Zonas del daño.</strong></p>
<div align="center">
<svg width="420" height="210" xmlns="http://www.w3.org/2000/svg">
  <line x1="60" y1="10" x2="60" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="170" x2="400" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="144" x2="400" y2="144" stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="118" x2="400" y2="118" stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="92"  x2="400" y2="92"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="66"  x2="400" y2="66"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="40"  x2="400" y2="40"  stroke="#ddd" stroke-width="0.8"/>
  <!-- Manos=4, Ojos=5, Brazos=3, Piernas=2, Pie=2. escala: 1 unidad = 26px -->
  <rect x="75"  y="66"  width="45" height="104" fill="#7bafd4"/>
  <rect x="135" y="40"  width="45" height="130" fill="#7bafd4"/>
  <rect x="195" y="92"  width="45" height="78"  fill="#7bafd4"/>
  <rect x="255" y="118" width="45" height="52"  fill="#7bafd4"/>
  <rect x="315" y="118" width="45" height="52"  fill="#7bafd4"/>
  <text x="97"  y="61"  text-anchor="middle" font-size="12">4</text>
  <text x="157" y="35"  text-anchor="middle" font-size="12">5</text>
  <text x="217" y="87"  text-anchor="middle" font-size="12">3</text>
  <text x="277" y="113" text-anchor="middle" font-size="12">2</text>
  <text x="337" y="113" text-anchor="middle" font-size="12">2</text>
  <text x="97"  y="186" text-anchor="middle" font-size="11">Manos</text>
  <text x="157" y="186" text-anchor="middle" font-size="11">Ojos</text>
  <text x="217" y="186" text-anchor="middle" font-size="11">Brazos</text>
  <text x="277" y="186" text-anchor="middle" font-size="11">Piernas</text>
  <text x="337" y="186" text-anchor="middle" font-size="11">Pie</text>
  <text x="52" y="170" text-anchor="end" font-size="10">0</text>
  <text x="52" y="144" text-anchor="end" font-size="10">1</text>
  <text x="52" y="118" text-anchor="end" font-size="10">2</text>
  <text x="52" y="92"  text-anchor="end" font-size="10">3</text>
  <text x="52" y="66"  text-anchor="end" font-size="10">4</text>
  <text x="52" y="40"  text-anchor="end" font-size="10">5</text>
  <text x="230" y="205" text-anchor="middle" font-size="11" font-weight="bold">Zona del Daño</text>
  <text x="18" y="95" font-size="11" transform="rotate(-90,18,95)" text-anchor="middle">f</text>
</svg>
</div>

<p align="center"><strong>Accidentes mes de Noviembre 2000. Zonas del daño. (%)</strong></p>
<div align="center">
<svg width="420" height="210" xmlns="http://www.w3.org/2000/svg">
  <line x1="60" y1="10" x2="60" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="170" x2="400" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="125" x2="400" y2="125" stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="80"  x2="400" y2="80"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="35"  x2="400" y2="35"  stroke="#ddd" stroke-width="0.8"/>
  <!-- Ojos=31%, Manos=25%, Brazos=19%, Piernas=13%, Pie=13%. escala: 10%=45px -->
  <rect x="75"  y="30"  width="45" height="140" fill="#7bafd4"/>
  <rect x="135" y="57"  width="45" height="113" fill="#7bafd4"/>
  <rect x="195" y="84"  width="45" height="86"  fill="#7bafd4"/>
  <rect x="255" y="111" width="45" height="59"  fill="#7bafd4"/>
  <rect x="315" y="111" width="45" height="59"  fill="#7bafd4"/>
  <text x="97"  y="25"  text-anchor="middle" font-size="12">31%</text>
  <text x="157" y="52"  text-anchor="middle" font-size="12">25%</text>
  <text x="217" y="79"  text-anchor="middle" font-size="12">19%</text>
  <text x="277" y="106" text-anchor="middle" font-size="12">13%</text>
  <text x="337" y="106" text-anchor="middle" font-size="12">13%</text>
  <text x="97"  y="186" text-anchor="middle" font-size="11">Ojos</text>
  <text x="157" y="186" text-anchor="middle" font-size="11">Manos</text>
  <text x="217" y="186" text-anchor="middle" font-size="11">Brazos</text>
  <text x="277" y="186" text-anchor="middle" font-size="11">Piernas</text>
  <text x="337" y="186" text-anchor="middle" font-size="11">Pie</text>
  <text x="52" y="170" text-anchor="end" font-size="10">0%</text>
  <text x="52" y="125" text-anchor="end" font-size="10">10%</text>
  <text x="52" y="80"  text-anchor="end" font-size="10">20%</text>
  <text x="52" y="35"  text-anchor="end" font-size="10">30%</text>
  <text x="230" y="205" text-anchor="middle" font-size="11" font-weight="bold">Zona del Daño</text>
  <text x="18" y="95" font-size="11" transform="rotate(-90,18,95)" text-anchor="middle">%</text>
</svg>
</div>

#### Diagrama de puntos
- Datos de variables cuantitativas.
- Se utilizan cuando tenemos menos de 20 datos.
- Consiste en un eje horizontal sobre el cual se marcan las observaciones con puntos.
- Se puede utilizar para comparar dos muestras en una misma escala.

<p align="center"><strong>Tiempos de procesamiento de solicitudes. Computadora A y B. Febrero 2001.</strong></p>

<div align="center">
<svg width="550" height="110" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrow" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="black"/>
    </marker>
  </defs>
  <line x1="50" y1="70" x2="490" y2="70" stroke="black" stroke-width="2" marker-end="url(#arrow)"/>
  <text x="50"  y="90" text-anchor="middle" font-size="13">10</text>
  <text x="155" y="90" text-anchor="middle" font-size="13">15</text>
  <text x="260" y="90" text-anchor="middle" font-size="13">20</text>
  <text x="365" y="90" text-anchor="middle" font-size="13">25</text>
  <text x="460" y="90" text-anchor="middle" font-size="13">30</text>
  <text x="500" y="73" font-size="13">s</text>
  <circle cx="155" cy="55" r="5" fill="black"/>
  <circle cx="250" cy="55" r="5" fill="black"/>
  <circle cx="270" cy="55" r="5" fill="black"/>
  <circle cx="344" cy="55" r="5" fill="black"/>
  <circle cx="360" cy="55" r="5" fill="black"/>
  <circle cx="365" cy="37" r="5" fill="black"/>
  <circle cx="376" cy="55" r="5" fill="black"/>
  <circle cx="438" cy="55" r="5" fill="black"/>
  <circle cx="460" cy="55" r="5" fill="black"/>
</svg>
</div>

#### Histograma
- Datos de variables cuantitativas (muchos valores).
- Las barras son **contiguas** (sin espacio entre ellas), a diferencia del diagrama de barras.

<p align="center"><strong>Tiempos de procesamiento por computadora, en segundos, de solicitudes. Computadora A y B en forma conjunta. Tipo XX. Febrero de 2001.</strong></p>
<div align="center">
<svg width="420" height="210" xmlns="http://www.w3.org/2000/svg">
  <line x1="60" y1="10" x2="60" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="170" x2="390" y2="170" stroke="black" stroke-width="1.5"/>
  <line x1="60" y1="144" x2="390" y2="144" stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="118" x2="390" y2="118" stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="92"  x2="390" y2="92"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="66"  x2="390" y2="66"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="40"  x2="390" y2="40"  stroke="#ddd" stroke-width="0.8"/>
  <line x1="60" y1="14"  x2="390" y2="14"  stroke="#ddd" stroke-width="0.8"/>
  <!-- barras: 3,4,6,6,1. Max=6, 1 unidad=26px, ancho=66px sin espacios -->
  <rect x="60"  y="92"  width="66" height="78"  fill="#7bafd4"/>
  <rect x="126" y="66"  width="66" height="104" fill="#7bafd4"/>
  <rect x="192" y="14"  width="66" height="156" fill="#7bafd4"/>
  <rect x="258" y="14"  width="66" height="156" fill="#7bafd4"/>
  <rect x="324" y="144" width="66" height="26"  fill="#7bafd4"/>
  <!-- bordes internos blancos para separar visualmente -->
  <line x1="126" y1="14" x2="126" y2="170" stroke="white" stroke-width="1.5"/>
  <line x1="192" y1="14" x2="192" y2="170" stroke="white" stroke-width="1.5"/>
  <line x1="258" y1="14" x2="258" y2="170" stroke="white" stroke-width="1.5"/>
  <line x1="324" y1="14" x2="324" y2="170" stroke="white" stroke-width="1.5"/>
  <text x="93"  y="87"  text-anchor="middle" font-size="12">3</text>
  <text x="159" y="61"  text-anchor="middle" font-size="12">4</text>
  <text x="225" y="9"   text-anchor="middle" font-size="12">6</text>
  <text x="291" y="9"   text-anchor="middle" font-size="12">6</text>
  <text x="357" y="139" text-anchor="middle" font-size="12">1</text>
  <text x="93"  y="186" text-anchor="middle" font-size="10">[10,15)</text>
  <text x="159" y="186" text-anchor="middle" font-size="10">[15,20)</text>
  <text x="225" y="186" text-anchor="middle" font-size="10">[20,25)</text>
  <text x="291" y="186" text-anchor="middle" font-size="10">[25,30)</text>
  <text x="357" y="186" text-anchor="middle" font-size="10">[30,35)</text>
  <text x="52" y="170" text-anchor="end" font-size="10">0</text>
  <text x="52" y="144" text-anchor="end" font-size="10">1</text>
  <text x="52" y="118" text-anchor="end" font-size="10">2</text>
  <text x="52" y="92"  text-anchor="end" font-size="10">3</text>
  <text x="52" y="66"  text-anchor="end" font-size="10">4</text>
  <text x="52" y="40"  text-anchor="end" font-size="10">5</text>
  <text x="52" y="14"  text-anchor="end" font-size="10">6</text>
  <text x="18" y="95" font-size="11" transform="rotate(-90,18,95)" text-anchor="middle">Frecuencia</text>
</svg>
</div>

## Medidas de posición

Es un resumen de la información de la muestra. Primero se desarrollaran las que son de tendencia central (media, mediana y moda).
### Media
Si contamos con los **datos**:
$$\bar{x} = \frac{x_1 + x_2 + \dots + x_n}{n} \quad siendo \: x_1,x_2,...,x_n\; datos\,muestrales$$
Si contamos con la **distribución de frecuencias**:
$$\bar{x} = \sum_{i=1}^{k} x_i \, f_r(x_i)$$
Donde $x_i$ es el centro de cada subintervalo, $k$ la cantidad de clases y $f_r(x_i)$ la frecuencia relativa $= \frac{frecuencia\,absoluta}{n}$ de la clase con centro en $x_i$.

<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 10px; display: inline-block;">
    <p>Si contamos con los datos, <strong>siempre</strong> es mejor calcular la media a partir de ellos.</p>
  </div>
</div>

### Mediana
Es el valor central (si n es par entonces la media de ambos valores del centro) de la muestra **ordenada**.
La posición de la mediana es:
$$\text{pos } \tilde{x} = \frac{n+1}{2}$$
<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 10px; display: inline-block;">
    <p>No se ve afectada por valores alejados ni asimetría.</p>
  </div>
</div>

Para una distribución de frecuencias calcular frecuencia acumulada y la posición de la mediana y ubicar la mediana. Por convención siempre se la marca.

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Clase</th>
        <th>Frecuencias</th>
        <th>Frec. acumulada</th>
        <th>Centro</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>(1300, 1800]</td><td>1</td><td>1</td><td>1550</td></tr>
      <tr><td>(1800, 2300]</td><td>3</td><td>4</td><td>2050</td></tr>
      <tr><td>(2300, 2800]</td><td>11</td><td>15</td><td>2550</td></tr>
      <tr style="background-color: #b8d4f0;"><td><strong>(2800, 3300]</strong></td><td><strong>30</strong></td><td><strong>45</strong></td><td><strong>3050</strong></td></tr>
      <tr><td>(3300, 3800]</td><td>23</td><td>68</td><td>3550</td></tr>
      <tr><td>(3800, 4300]</td><td>11</td><td>79</td><td>4050</td></tr>
      <tr><td>(4300, 4800]</td><td>1</td><td>80</td><td>4550</td></tr>
      <tr><td><strong>Total</strong></td><td><strong>80</strong></td><td></td><td></td></tr>
    </tbody>
  </table>
</div>

### Cuartiles
Divide el lote de datos ordenados en cuatro partes iguales. Se calcula el centro y luego la mediana de nuevo para el Q1 y luego se cuenta desde adelante para sacar Q3.
$$\text{pos } Q_1 = \frac{\left[\text{pos } \tilde{x}\right]+1}{2}$$
Donde $\left[\text{pos } \tilde{x}\right]$ es la **parte entera** de la posición de la mediana.
### Moda
Es el dato mas frecuente (en el lote de datos 7,7,8,8 no hay moda). Se puede indicar en variables cualitativas.

## Medidas de dispersión 
Mide cuán alejados están los datos del centro de distribución (media o mediana).
### Medidas de dispersión asociadas a la media
Si el lote de datos es simétrico y no tiene valores alejados usaremos la media y la desviación estándar o $s$ para describir el lote de datos.
#### Varianza muestral
$$\hat{\sigma}^2 = \frac{(x_1 - \bar{x})^2 + \dots + (x_n - \bar{x})^2}{n}$$
Con datos agrupados:
$$\hat{\sigma}^2 = \sum_{i=1}^{k} (x_i - \bar{x})^2 f_r(x_i)$$
#### Desviación estándar
Cuánto se alejan los datos de la media en promedio.
$$\hat{\sigma} = \sqrt{\frac{(x_1 - \bar{x})^2 + \dots + (x_n - \bar{x})^2}{n}}$$
Con datos agrupados:
$$\hat{\sigma} = \sqrt{\sum_{i=1}^{k} (x_i - \bar{x})^2 f_r(x_i)}$$
#### s (corrección de Bessel)
$$s = \sqrt{\frac{(x_1 - \bar{x})^2 + \dots + (x_n - \bar{x})^2}{n-1}}$$
#### Coeficiente de variación
Medida de la magnitud de la dispersión en relación a la media.
$$CV = \frac{\hat{\sigma}}{\bar{x}}$$
- Lo recomendable es que sea **a lo sumo 0.1**, por ejemplo, si la media es 100 entonces en promedio los datos se alejan 10 unidades de la media.
- Si es 2, significa que el desvío estándar es dos veces el promedio por lo que la información de la media es muy pobre.
#### Desigualdad de Chebychev
Demuestra que en el intervalo $(\bar{x} - 2\hat{\sigma}, \ \bar{x} + 2\hat{\sigma})$ se encuentra como mínimo el $75\%$ de los datos. Los casos son: 
1. 75% = dispersión esperada.
2. Más del 75% = datos muy concentrados o poco dispersos.
### Medidas de dispersión asociadas a la mediana
#### Rango intercuartil
$$RI=Q_3-Q_1$$
#### Meda
$$\text{Meda} = \text{mediana}\{|x_i - \tilde{x}|\}$$
$|x_i - \tilde{x}|$ *es un desvío.*

En el intervalo $(\tilde{x} - meda, \ \tilde{x} + meda)$ se encuentran aproximadamente el $50\%$ de los datos. Los casos son:
1. 50% = dispersión esperada.
2. Más del 50% = el lote tiene poca dispersión.

### Análisis de la simetría
#### Coeficiente de simetría 
$$\left|\frac{\bar{x} - \tilde{x}}{\hat{\sigma}}\right| \times 100\%$$
1. Menor que $10\%$ = muestra simétrica.
2. Mayor que $20\%$ = muestra asimétrica.
3. Entre $10\%$ y $20\%$ = se decide gráficamente.

#### Gráficamente

<p align="center">Asimetría positiva</p>
<div align="center">
<svg width="380" height="150" xmlns="http://www.w3.org/2000/svg">
  <line x1="30" y1="10" x2="30" y2="125" stroke="black" stroke-width="1.5"/>
  <line x1="30" y1="125" x2="370" y2="125" stroke="black" stroke-width="1.5"/>
  <!-- datos: 5,6,12,10,8,6,3,3,2. Max=12, 1u=9px, ancho=36px -->
  <rect x="30"  y="80"  width="36" height="45" fill="#7bafd4"/>
  <rect x="66"  y="71"  width="36" height="54" fill="#7bafd4"/>
  <rect x="102" y="17"  width="36" height="108" fill="#7bafd4"/>
  <rect x="138" y="35"  width="36" height="90" fill="#7bafd4"/>
  <rect x="174" y="53"  width="36" height="72" fill="#7bafd4"/>
  <rect x="210" y="71"  width="36" height="54" fill="#7bafd4"/>
  <rect x="246" y="98"  width="36" height="27" fill="#7bafd4"/>
  <rect x="282" y="98"  width="36" height="27" fill="#7bafd4"/>
  <rect x="318" y="107" width="36" height="18" fill="#7bafd4"/>
  <line x1="66"  y1="10" x2="66"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="102" y1="10" x2="102" y2="125" stroke="white" stroke-width="1"/>
  <line x1="138" y1="10" x2="138" y2="125" stroke="white" stroke-width="1"/>
  <line x1="174" y1="10" x2="174" y2="125" stroke="white" stroke-width="1"/>
  <line x1="210" y1="10" x2="210" y2="125" stroke="white" stroke-width="1"/>
  <line x1="246" y1="10" x2="246" y2="125" stroke="white" stroke-width="1"/>
  <line x1="282" y1="10" x2="282" y2="125" stroke="white" stroke-width="1"/>
  <line x1="318" y1="10" x2="318" y2="125" stroke="white" stroke-width="1"/>
</svg>
</div>

<p align="center">Asimetría negativa</p>
<div align="center">
<svg width="380" height="150" xmlns="http://www.w3.org/2000/svg">
  <line x1="30" y1="10" x2="30" y2="125" stroke="black" stroke-width="1.5"/>
  <line x1="30" y1="125" x2="370" y2="125" stroke="black" stroke-width="1.5"/>
  <!-- datos: 1,1,2,3,3,4,6,7,12. Max=12, 1u=9px -->
  <rect x="30"  y="116" width="36" height="9"   fill="#7bafd4"/>
  <rect x="66"  y="116" width="36" height="9"   fill="#7bafd4"/>
  <rect x="102" y="107" width="36" height="18"  fill="#7bafd4"/>
  <rect x="138" y="98"  width="36" height="27"  fill="#7bafd4"/>
  <rect x="174" y="98"  width="36" height="27"  fill="#7bafd4"/>
  <rect x="210" y="89"  width="36" height="36"  fill="#7bafd4"/>
  <rect x="246" y="71"  width="36" height="54"  fill="#7bafd4"/>
  <rect x="282" y="62"  width="36" height="63"  fill="#7bafd4"/>
  <rect x="318" y="17"  width="36" height="108" fill="#7bafd4"/>
  <line x1="66"  y1="10" x2="66"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="102" y1="10" x2="102" y2="125" stroke="white" stroke-width="1"/>
  <line x1="138" y1="10" x2="138" y2="125" stroke="white" stroke-width="1"/>
  <line x1="174" y1="10" x2="174" y2="125" stroke="white" stroke-width="1"/>
  <line x1="210" y1="10" x2="210" y2="125" stroke="white" stroke-width="1"/>
  <line x1="246" y1="10" x2="246" y2="125" stroke="white" stroke-width="1"/>
  <line x1="282" y1="10" x2="282" y2="125" stroke="white" stroke-width="1"/>
  <line x1="318" y1="10" x2="318" y2="125" stroke="white" stroke-width="1"/>
</svg>
</div>

<p align="center">Simétrica</p>
<div align="center">
<svg width="400" height="150" xmlns="http://www.w3.org/2000/svg">
  <line x1="20" y1="10" x2="20" y2="125" stroke="black" stroke-width="1.5"/>
  <line x1="20" y1="125" x2="380" y2="125" stroke="black" stroke-width="1.5"/>
  <!-- datos: 3,4,6,6,10,7,5,5,3,2. Max=10, 1u=10px, ancho=36px -->
  <rect x="20"  y="95"  width="36" height="30"  fill="#7bafd4"/>
  <rect x="56"  y="85"  width="36" height="40"  fill="#7bafd4"/>
  <rect x="92"  y="65"  width="36" height="60"  fill="#7bafd4"/>
  <rect x="128" y="65"  width="36" height="60"  fill="#7bafd4"/>
  <rect x="164" y="25"  width="36" height="100" fill="#7bafd4"/>
  <rect x="200" y="55"  width="36" height="70"  fill="#7bafd4"/>
  <rect x="236" y="75"  width="36" height="50"  fill="#7bafd4"/>
  <rect x="272" y="75"  width="36" height="50"  fill="#7bafd4"/>
  <rect x="308" y="95"  width="36" height="30"  fill="#7bafd4"/>
  <rect x="344" y="105" width="36" height="20"  fill="#7bafd4"/>
  <line x1="56"  y1="10" x2="56"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="92"  y1="10" x2="92"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="128" y1="10" x2="128" y2="125" stroke="white" stroke-width="1"/>
  <line x1="164" y1="10" x2="164" y2="125" stroke="white" stroke-width="1"/>
  <line x1="200" y1="10" x2="200" y2="125" stroke="white" stroke-width="1"/>
  <line x1="236" y1="10" x2="236" y2="125" stroke="white" stroke-width="1"/>
  <line x1="272" y1="10" x2="272" y2="125" stroke="white" stroke-width="1"/>
  <line x1="308" y1="10" x2="308" y2="125" stroke="white" stroke-width="1"/>
  <line x1="344" y1="10" x2="344" y2="125" stroke="white" stroke-width="1"/>
</svg>
</div>

<p align="center">Extra: bimodal</p>
<div align="center">
<svg width="420" height="150" xmlns="http://www.w3.org/2000/svg">
  <line x1="20" y1="10" x2="20" y2="125" stroke="black" stroke-width="1.5"/>
  <line x1="20" y1="125" x2="404" y2="125" stroke="black" stroke-width="1.5"/>
  <!-- datos: 2,3,3,4,3,2,3,3,4,5,3,2. Max=5, 1u=20px, ancho=32px -->
  <rect x="20"  y="85"  width="32" height="40"  fill="#7bafd4"/>
  <rect x="52"  y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="84"  y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="116" y="45"  width="32" height="80"  fill="#7bafd4"/>
  <rect x="148" y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="180" y="85"  width="32" height="40"  fill="#7bafd4"/>
  <rect x="212" y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="244" y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="276" y="45"  width="32" height="80"  fill="#7bafd4"/>
  <rect x="308" y="25"  width="32" height="100" fill="#7bafd4"/>
  <rect x="340" y="65"  width="32" height="60"  fill="#7bafd4"/>
  <rect x="372" y="85"  width="32" height="40"  fill="#7bafd4"/>
  <line x1="52"  y1="10" x2="52"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="84"  y1="10" x2="84"  y2="125" stroke="white" stroke-width="1"/>
  <line x1="116" y1="10" x2="116" y2="125" stroke="white" stroke-width="1"/>
  <line x1="148" y1="10" x2="148" y2="125" stroke="white" stroke-width="1"/>
  <line x1="180" y1="10" x2="180" y2="125" stroke="white" stroke-width="1"/>
  <line x1="212" y1="10" x2="212" y2="125" stroke="white" stroke-width="1"/>
  <line x1="244" y1="10" x2="244" y2="125" stroke="white" stroke-width="1"/>
  <line x1="276" y1="10" x2="276" y2="125" stroke="white" stroke-width="1"/>
  <line x1="308" y1="10" x2="308" y2="125" stroke="white" stroke-width="1"/>
  <line x1="340" y1="10" x2="340" y2="125" stroke="white" stroke-width="1"/>
  <line x1="372" y1="10" x2="372" y2="125" stroke="white" stroke-width="1"/>
</svg>
</div>

### Valores alejados

Valores observados que se apartan demasiado del resto de la muestra.

1. Alejado por defecto: si $x_i < Q_1 - 1.5(Q_3 - Q_1)$
2. Alejado por exceso: si $x_i > Q_3 + 1.5(Q_3 - Q_1)$

*No se descarta este dato, se lo estudia con medidas que no son afectadas por valores alejados.*

<div align="center">
  <div style="border: 1px solid #a0a0a0; padding: 15px; display: inline-block; text-align: left; max-width: 500px;">
    <p>Si el conjunto de datos es <strong>simétrico y no tiene valores alejados</strong>, se recomienda utilizar la <strong>media</strong> como medida de posición con la <strong>desviación estándar</strong> como medida de dispersión.</p>
    <p>Si el conjunto de datos es <strong>asimétrico y/o tiene valores alejados</strong>, se recomienda utilizar la <strong>mediana</strong> como medida de posición con el <strong>rango intercuartil o meda</strong> como medida de dispersión.</p>
  </div>
</div>

## Diagrama tipo caja (Box Plot)
- Datos de variable cuantitativa. 
- Mediana, mínimo, máximo, valores alejados y cuartiles.
- Se visualiza rango, posición, dispersión, valores alejados, forma y distribución de datos.
- Comparar dos set de datos.

<p align="center"><strong>Peso de neonatos en Hospital XXX<br>Agosto 2009</strong></p>
<div align="center">
<svg width="400" height="350" xmlns="http://www.w3.org/2000/svg">
  <rect x="60" y="20" width="300" height="290" fill="white" stroke="black" stroke-width="1.5"/>
  <text x="45" y="290" text-anchor="end" font-size="13">1500</text>
  <text x="45" y="218" text-anchor="end" font-size="13">2500</text>
  <text x="45" y="145" text-anchor="end" font-size="13">3500</text>
  <text x="45" y="72"  text-anchor="end" font-size="13">4500</text>
  <line x1="60" y1="290" x2="360" y2="290" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="218" x2="360" y2="218" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="145" x2="360" y2="145" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="72"  x2="360" y2="72"  stroke="#ddd" stroke-width="1"/>
  <line x1="210" y1="100" x2="210" y2="145" stroke="black" stroke-width="1.5"/>
  <line x1="185" y1="100" x2="235" y2="100" stroke="black" stroke-width="1.5"/>
  <rect x="135" y="145" width="150" height="80" fill="white" stroke="black" stroke-width="1.5"/>
  <line x1="135" y1="195" x2="285" y2="195" stroke="black" stroke-width="2"/>
  <line x1="210" y1="225" x2="210" y2="258" stroke="black" stroke-width="1.5"/>
  <line x1="185" y1="258" x2="235" y2="258" stroke="black" stroke-width="1.5"/>
  <text x="210" y="88"  font-size="14" text-anchor="middle">*</text>
  <text x="210" y="275" font-size="14" text-anchor="middle">*</text>
  <text x="210" y="298" font-size="14" text-anchor="middle">*</text>
</svg>
</div>

<p align="center"><strong>Título fuente Fecha (TFF)</strong></p>
<div align="center">
<svg width="400" height="350" xmlns="http://www.w3.org/2000/svg">
  <rect x="60" y="20" width="320" height="300" fill="white" stroke="black" stroke-width="1.5"/>
  <text x="50" y="315" text-anchor="end" font-size="13">0</text>
  <text x="50" y="230" text-anchor="end" font-size="13">8</text>
  <text x="50" y="165" text-anchor="end" font-size="13">17</text>
  <text x="50" y="100" text-anchor="end" font-size="13">26</text>
  <text x="50" y="35"  text-anchor="end" font-size="13">35</text>
  <line x1="60" y1="315" x2="380" y2="315" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="230" x2="380" y2="230" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="165" x2="380" y2="165" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="100" x2="380" y2="100" stroke="#ddd" stroke-width="1"/>
  <line x1="60" y1="35"  x2="380" y2="35"  stroke="#ddd" stroke-width="1"/>
  <line x1="160" y1="55"  x2="160" y2="100" stroke="black" stroke-width="1.5"/>
  <line x1="135" y1="55"  x2="185" y2="55"  stroke="black" stroke-width="1.5"/>
  <rect x="110" y="100" width="100" height="130" fill="#aaa" stroke="black" stroke-width="1.5"/>
  <rect x="110" y="165" width="100" height="65" fill="#555" stroke="black" stroke-width="1.5"/>
  <line x1="160" y1="230" x2="160" y2="270" stroke="black" stroke-width="1.5"/>
  <line x1="135" y1="270" x2="185" y2="270" stroke="black" stroke-width="1.5"/>
  <line x1="300" y1="100" x2="300" y2="130" stroke="black" stroke-width="1.5"/>
  <line x1="275" y1="100" x2="325" y2="100" stroke="black" stroke-width="1.5"/>
  <rect x="250" y="130" width="100" height="100" fill="#aaa" stroke="black" stroke-width="1.5"/>
  <rect x="250" y="220" width="100" height="10"  fill="#555" stroke="black" stroke-width="1.5"/>
  <line x1="300" y1="230" x2="300" y2="270" stroke="black" stroke-width="1.5"/>
  <line x1="275" y1="270" x2="325" y2="270" stroke="black" stroke-width="1.5"/>
</svg>
</div>

## Informe
Debe incluir oraciones referidas a:
1. Posición.
2. Dispersión.
3. Forma del lote de datos.
4. Valores alejados, si es que hay.

Requisitos para realizarlo:
5. Distribución de frecuencias.
6. Representación gráfica de los datos.
7. Medidas de dispersión y posición.
8. Estudiar simetría y valores alejados.

*Ejemplo en la unidad 1 pdf 5 pagina 10*

## Análisis descriptivo bidimensional 
Es el análisis multivariado de las variables para el caso de dos.
- Lote de datos: $(x_1, y_1) , (x_2, y_2) , \dots, (x_N, y_N)$
### Distribución de frecuencias conjuntas
$$\sum_{i=1}^{m} \sum_{j=1}^{n} n_{ij} = N$$
Ejemplo:
<div align="center">
  <table>
    <thead>
      <tr>
        <th>Lote \ Nro. de def.</th>
        <th>0</th><th>1</th><th>2</th><th>3</th><th></th>
      </tr>
    </thead>
    <tbody>
      <tr><td><strong>A</strong></td><td>7</td><td>15</td><td>5</td><td>3</td><td></td></tr>
      <tr><td><strong>B</strong></td><td>5</td><td>20</td><td>15</td><td>10</td><td></td></tr>
      <tr><td></td><td></td><td></td><td></td><td></td><td>80</td></tr>
    </tbody>
  </table>
</div>

*También se puede realizar con frecuencias relativas y la suma daría 1.*

### Distribución de frecuencias marginales
En un análisis descriptivo bidimensional hay dos, una por cada variable. 
- Si se tratan variables categóricas se denomina **tabla de contingencia**.
- Datos categóricos y cuantitativos (pocos valores o en clases).

$$f_i = \sum_{j=0}^{3} n_{ij} = n_{i.} \qquad f_j = \sum_{i=1}^{2} n_{ij} = n_{.j}$$

<div align="center">
  <table>
    <thead>
      <tr>
        <th>Lote \ Nro. de def.</th>
        <th>0</th><th>1</th><th>2</th><th>3</th><th></th>
      </tr>
    </thead>
    <tbody>
      <tr><td><strong>A</strong></td><td>7</td><td>15</td><td>5</td><td>3</td><td style="background-color:#b8d4f0;">30</td></tr>
      <tr><td><strong>B</strong></td><td>5</td><td>20</td><td>15</td><td>10</td><td style="background-color:#b8d4f0;">50</td></tr>
      <tr><td></td><td style="background-color:#b8e0b8;">12</td><td style="background-color:#b8e0b8;">35</td><td style="background-color:#b8e0b8;">20</td><td style="background-color:#b8e0b8;">13</td><td style="background-color:#b8d4f0;">80</td></tr>
    </tbody>
  </table>
</div>

<p align="center"><strong>Distribución de Frecuencias Marginales</strong></p>

<div align="center" style="display: flex; justify-content: center; gap: 40px;">
  <table>
    <thead>
      <tr>
        <th style="background-color:#b8d4f0;">Lote</th>
        <th style="background-color:#b8d4f0;">f</th>
      </tr>
    </thead>
    <tbody>
      <tr><td style="background-color:#daeaf5;">A</td><td style="background-color:#daeaf5;">30</td></tr>
      <tr><td style="background-color:#daeaf5;">B</td><td style="background-color:#daeaf5;">50</td></tr>
      <tr><td style="background-color:#daeaf5;"><strong>Total</strong></td><td style="background-color:#daeaf5;"><strong>80</strong></td></tr>
    </tbody>
  </table>
  <table>
    <thead>
      <tr>
        <th style="background-color:#b8e0b8;">Nro. de defectos</th>
        <th style="background-color:#b8e0b8;">f</th>
      </tr>
    </thead>
    <tbody>
      <tr><td style="background-color:#daf5da;">0</td><td style="background-color:#daf5da;">12</td></tr>
      <tr><td style="background-color:#daf5da;">1</td><td style="background-color:#daf5da;">35</td></tr>
      <tr><td style="background-color:#daf5da;">2</td><td style="background-color:#daf5da;">20</td></tr>
      <tr><td style="background-color:#daf5da;">3</td><td style="background-color:#daf5da;">13</td></tr>
      <tr><td style="background-color:#daf5da;"><strong>Total</strong></td><td style="background-color:#daf5da;"><strong>80</strong></td></tr>
    </tbody>
  </table>
</div>

### Asociación entre dos variables

Para estudiar si hay o no asociación se pueden calcular porcentajes sobre el total de filas o total de columnas, según qué influencia se quiera estudiar.

En este ejemplo la primera distribución de porcentajes no muestra ningún orden ni correlación aparente.

<div align="center">
  <table>
    <thead>
      <tr><th>Lote \ Nro. de def.</th><th>0</th><th>1</th><th>2</th><th>3</th><th></th></tr>
    </thead>
    <tbody>
      <tr><td><strong>A</strong></td><td>7</td><td>15</td><td>5</td><td>3</td><td>30</td></tr>
      <tr><td><strong>B</strong></td><td>5</td><td>20</td><td>15</td><td>10</td><td>50</td></tr>
      <tr><td></td><td>12</td><td>35</td><td>20</td><td>13</td><td>80</td></tr>
    </tbody>
  </table>
</div>

<div align="center">
  <table>
    <thead>
      <tr style="background-color:#1a6fa8; color:white;"><th>Lote \ Nro. de def.</th><th>0</th><th>1</th><th>2</th><th>3</th><th></th></tr>
    </thead>
    <tbody>
      <tr style="background-color:#daeaf5;"><td><strong>A</strong></td><td>23%</td><td>50%</td><td>17%</td><td>10%</td><td>100% (30)</td></tr>
      <tr style="background-color:#eaf4fb;"><td><strong>B</strong></td><td>10%</td><td>40%</td><td>30%</td><td>20%</td><td>100% (50)</td></tr>
    </tbody>
  </table>
</div>

En este ejemplo hay correlación: en las categorías 0 y 1 el lote M tiene mucho mayor porcentaje que en 2 y 3, y lo mismo ocurre inversamente con T.

<div align="center">
  <table>
    <thead>
      <tr><th>Lote \ Nro. de def.</th><th>0</th><th>1</th><th>2</th><th>3</th><th></th></tr>
    </thead>
    <tbody>
      <tr><td><strong>M</strong></td><td>20</td><td>8</td><td>1</td><td>1</td><td>30</td></tr>
      <tr><td><strong>T</strong></td><td>5</td><td>10</td><td>15</td><td>20</td><td>50</td></tr>
      <tr><td></td><td>25</td><td>18</td><td>17</td><td>20</td><td>80</td></tr>
    </tbody>
  </table>
</div>

<div align="center">
  <table>
    <thead>
      <tr style="background-color:#1a6fa8; color:white;"><th>Lote \ Nro. de def.</th><th>0</th><th>1</th><th>2</th><th>3</th><th></th></tr>
    </thead>
    <tbody>
      <tr style="background-color:#daeaf5;"><td><strong>M</strong></td><td>67%</td><td>27%</td><td>3%</td><td>3%</td><td>100% (30)</td></tr>
      <tr style="background-color:#eaf4fb;"><td><strong>T</strong></td><td>10%</td><td>20%</td><td>30%</td><td>40%</td><td>100% (50)</td></tr>
    </tbody>
  </table>
</div>
