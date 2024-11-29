#### ⚠️ ¡Aviso legal! ¡Esto NO es un consejo financiero! Más detalles [aquí](./disclaimers/DISCLAIMER_SPANISH.md). 👀

# Entendiendo Bitcoin y el S&P 500: Un Análisis Comparativo Basado en Datos

<a id='main-questions'></a>

## ¿Qué preguntas buscamos responder con este proyecto?

Utilizando datos públicos, este proyecto intentará responder estas preguntas muy interesantes, así como analizar el comportamiento de Bitcoin y el S&P 500 a lo largo del tiempo:

0. [Análisis temporal de Bitcoin (BTC) y S&P 500 durante los últimos 10 años. **(Semanal, Mensual, Anual)**](#temporal-analysis)
1. [¿La correlación entre Bitcoin y el S&P 500 es mayor en períodos de crisis económica? ¿Es esto cierto?](#correlation-analysis)
2. [¿Qué ofrece mejores retornos: la volatilidad de Bitcoin o la consistencia del S&P 500?](#volatility-analysis)
3. [Bitcoin muestra una alta volatilidad en comparación con el S&P 500, pero ¿qué tan volátil es BTC en comparación con el S&P 500?](#Returns-Time)
4. [**¡Bonus!** Conclusiones clave para las partes interesadas](#takeaways)

Para responder estas preguntas, se utilizarán diferentes técnicas como:

  * Estadísticas
  * Análisis
  * Finanzas
  * Narración de historias
  * Pensamiento crítico

Con herramientas como:

  * __Python__
  * __Numpy__
  * __Pandas__
  * __Matplotlib__
  * __Seaborn__

¡Responderé estas preguntas tan interesantes, disfruten!

## **Conjuntos de datos**
### Descripción general

Los conjuntos de datos incluyen precios diarios de Bitcoin y el S&P 500 desde **septiembre de 2014 hasta mayo de 2024**.

### Pasos clave de preprocesamiento:

1. **Manejo de valores faltantes**:
   - Se eliminaron valores faltantes para garantizar la integridad de los datos, ya que representaban menos del 1% del conjunto de datos.
2. **Eliminación de datos de fin de semana**:
   - Se alinearon los datos de Bitcoin con el S&P 500, que solo opera en días hábiles.
3. **Limpieza de datos**:
   - Se eliminaron duplicados y se garantizó la alineación temporal entre los conjuntos de datos.

## **Flujo de trabajo del proyecto**

### Paso 1 y 2: Investigación inicial
- Se realizó un análisis exploratorio utilizando `.head()`, `.info()` y `.describe()` para comprender los conjuntos de datos.
- Se combinaron archivos relevantes para crear conjuntos de datos unificados para Bitcoin y el índice S&P 500.
- Se garantizó una alta calidad de datos eliminando filas nulas y duplicadas.
- Se cambió el tipo de datos en columnas como 'Date' a `datetime64` para un mejor manejo de los conjuntos de datos.
- Utilizando el método de rango intercuartílico (IQR), se encontraron algunos valores atípicos en ambos conjuntos de datos, los cuales se mantuvieron para observar comportamientos del mercado durante eventos extremos.
- Los datos se exportaron en un archivo para BTC y otro para el S&P 500.

Ver más detalles en los notebooks para estos pasos:
* [Exploración Inicial S&P 500](./1_Inital_Exploration_SP_500.ipynb)
* [Exploración Inicial BTC](./1_Initial_Exploraion_BTC.ipynb)
* [Comparación BTC y S&P 500](./2_BTC_SP500_Comparation.ipynb)

### Paso 3: Evaluación de calidad

- Se verificó la integridad de los datos comprobando **valores faltantes**, **duplicados** y **rangos de valores lógicos**.
- Los conjuntos de datos están temporalmente alineados, asegurando que ambos tuvieran rangos de fechas idénticos.
- Los datos están limpios y son consistentes y confiables en ambos conjuntos.

Ver más **observaciones** y **conclusiones** en el notebook:
* [Evaluación de Calidad para BTC y S&P 500](./3_Quality_Evaluation_BTC_SP500.ipynb)

<a id='temporal-analysis'></a>

# Paso 4: Análisis temporal [⬆️ Volver a las preguntas principales 🤓](#main-questions)

- **Objetivo**: Identificar tendencias de precios en intervalos semanales, mensuales, trimestrales y anuales.

- **Hallazgos**:
  - **Tendencias de precios**:
    - Bitcoin muestra una alta variabilidad a corto plazo, mientras que el S&P 500 tiene un crecimiento estable y consistente. **(Ver [Figura 1](#figure-1))**
    - Las tendencias a largo plazo destacan el crecimiento exponencial y la volatilidad de Bitcoin. **(Ver [Figura 2](#figure-2))**
  - **Tendencias de volumen**:
    - El volumen de transacciones de Bitcoin se correlaciona con períodos de alta volatilidad de precios, a menudo aumentando durante rallies o caídas del mercado.
    - El volumen de transacciones del S&P 500 permanece relativamente estable, alineándose con su crecimiento consistente.
    - Aumentos significativos en el volumen de Bitcoin a menudo preceden reversiones de precios, sugiriendo una fuerte relación entre el sentimiento del mercado y la actividad comercial. **(Ver [Figura 3](#figure-3) y [Figura 4](#figure-4))**
  - **Ideas comparativas**:
    - El volumen de Bitcoin responde altamente a noticias del mercado y eventos macroeconómicos, amplificando su volatilidad.
    - El volumen comercial del S&P 500 muestra resiliencia y menor sensibilidad a noticias a corto plazo, indicando una estructura de mercado madura y estable.
    - En ambos casos, en enero de 2018, el precio y el volumen de Bitcoin superaron las métricas del S&P y se han mantenido así desde entonces, por ahora... **(Ver Figura 1 y 3)**

---

## **En palabras simples**:
  - Bitcoin 🪙 exhibe alta volatilidad y un crecimiento exponencial a largo plazo 📈, con picos significativos en el volumen de transacciones durante eventos del mercado 📊, mientras que el S&P 500 permanece estable y menos sensible a cambios a corto plazo 🛠️📉. **Desde 2018, Bitcoin ha superado consistentemente al S&P 500 en precio 💸 y volumen 🔥**.

Ver más **observaciones** y **conclusiones** en el notebook:
* [Análisis Temporal para Bitcoin y el Índice S&P 500](/4_Temporal_Analysis.ipynb)

<a id="figure-1"></a>
**Figura 1.** Precios Promedio Semanales de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Promedio Semanales de BTC y S&P 500 (USD)](./images/Fig1_weekly_prices_BTC_SP500.png)

<a id="figure-3"></a>
**Figura 3.** Volumen de Transacciones Semanales de BTC y S&P 500 (por 1 millón de unidades). [⬆️ Volver](#temporal-analysis)

![Volumen de Transacciones Semanales de BTC y S&P 500](/images/Fig3_weekly_volume_BTC_SP500.png)

**Promedios Mensuales.** Precios Promedio Mensuales de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Promedio Mensuales de BTC y S&P 500 (USD)](/images/monthly_average_price.png)

**Volumen Mensual.** Volumen de Precios Mensuales de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Volumen de Precios Mensuales de BTC y S&P 500 (USD)](/images/monthly_total_volume.png)

<a id="figure-2"></a>
**Figura 2.** Precios Promedio Anuales de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Promedio Anuales de BTC y S&P 500 (USD)](/images/Fig2_annual_prices_BTC_SP500.png)

<a id="figure-4"></a>
**Figura 4.** Volumen de Transacciones Anuales de BTC y S&P 500 (por 1 millón de unidades). [⬆️ Volver](#temporal-analysis)

![Volumen de Transacciones Anuales de BTC y S&P 500](/images/Fig4_annual_volume_BTC_SP500.png)

<a id="correlation-analysis"></a>

# ¿La correlación entre Bitcoin y el S&P 500 es mayor en períodos de crisis económica? ¿Es esto cierto? [⬆️ Volver a las preguntas principales 🤓](#main-questions)

### Análisis de perspectivas (Paso 5.1):

- **Objetivo**: El objetivo de este análisis fue explorar la correlación entre Bitcoin (BTC) y el índice S&P 500 durante la crisis del COVID-19 (marzo 2020 a diciembre 2021), la crisis de energía y suministros (2021-2022), y la crisis financiera (2023-2024).

- **Específicamente, el análisis se enfoca en**:
  - Comprender el comportamiento de BTC y el S&P 500 durante períodos económicos clave.
  - Comparar tendencias de precios y volúmenes y correlaciones para identificar posibles patrones o anomalías.
  - Destacar ideas que puedan informar estrategias de inversión o gestión de riesgos.

#### Entendiendo las correlaciones

  1. **Correlación positiva**:
    - Si la correlación se acerca a **1**, indica una **correlación positiva directa**, lo que significa que, a medida que una variable aumenta, la otra también aumenta.

  2. **Correlación negativa**:
    - Si la correlación se acerca a **-1**, indica una **correlación inversa directa**, lo que significa que, a medida que una variable aumenta, la otra disminuye.

  3. **Sin correlación**:
    - Cuanto más cerca esté la correlación de **0**, más débil será la relación, indicando **poca o ninguna correlación** entre las dos variables.

### Observaciones y Conclusiones

1. **Tendencias generales**:
   - BTC y el S&P 500 exhiben comportamientos distintos, siendo BTC más volátil en comparación con el movimiento estable del S&P 500.
   - Ambos activos muestran movimientos de precios significativos durante períodos económicos importantes, como la crisis del COVID-19.

<a id='covid-19_correlation'></a>

2. **Análisis del período COVID-19 (2020–2021)**:
   - Durante la pandemia, BTC experimentó un fuerte aumento de precios **a partir de finales de 2020, coincidiendo con medidas de estímulo fiscal.** **(Ver [Figura 5, sección superior](#figure-5))**
   - El S&P 500 también se recuperó durante este período, reflejando tendencias de recuperación similares en los mercados tradicionales y de criptomonedas.
   - **Perspectiva de correlación**: BTC y S&P 500 demostraron una **correlación positiva moderada a fuerte (0.87)** durante este período, indicando una alineación más estrecha de los movimientos del mercado. **(Ver [Figura 5, sección inferior](#figure-5))**

<a id='supply_energy_correlation'></a>

3. **Crisis de suministro y energía 2021–2022 (Aún con temas de COVID y la guerra Ucrania-Rusia)**:
   - El precio y volumen de BTC exhibieron alta volatilidad, con caídas significativas durante las crisis globales de energía y las interrupciones en la cadena de suministro, junto con la prohibición de Bitcoin en China (sep. 2021). **(Ver [Figura 6, sección superior](#figure-6))** 
   - El S&P 500 mostró tendencias relativamente estables, destacando resiliencia en comparación con la alta sensibilidad de BTC a las condiciones del mercado global.
   - **Perspectiva de correlación**: La correlación entre BTC y el S&P 500 **se debilitó ligeramente (0.60)** durante este período, pero permaneció positiva, sugiriendo una alineación parcial del mercado en medio de choques externos. **(Ver [Figura 6, sección inferior](#figure-6))**

<a id='Economic-crisis'></a>

4. **Crisis Económica (2023–2024)**:
   - BTC mostró un crecimiento significativo y mantuvo una trayectoria de precios más alta, reflejando un mayor interés por parte de inversionistas especulativos que buscan activos alternativos. **(Ver [Figura 7, sección superior](#figure-7))**
   - El S&P 500 mostró tendencias estables con una recuperación gradual, **reforzando su papel como indicador de estabilidad económica.**
   - **Perspectiva de correlación**: La correlación **se fortaleció (0.90)** durante este período, indicando una **dependencia creciente entre BTC y los mercados tradicionales** a medida que BTC se integra más en las finanzas globales. **(Ver [Figura 7, sección inferior](#figure-7))**

<a id='volumen-analysis'></a>

5. **Análisis de Volumen**:
   - El volumen de negociación de BTC aumentó durante períodos de alta volatilidad de precios, mostrando sensibilidad a los eventos del mercado.
   - Los volúmenes del S&P 500, aunque menos volátiles, también aumentaron durante la incertidumbre del mercado.
   - En general, parece que la correlación "volumen de negociación-precio" entre Bitcoin y el S&P 500 **no es muy fuerte** y apenas están correlacionados. **(Ver [Figura 8](#figure-8))**

### La "Sombra Roja" en los Gráficos de Correlación

La **sombra roja** en los gráficos de correlación representa el **intervalo de confianza** para la línea de regresión lineal. Este intervalo indica el rango dentro del cual es probable que caiga la verdadera línea de regresión con un cierto nivel de confianza (típicamente 95%). **Una sombra roja más estrecha** sugiere **mayor confianza** y menos variabilidad en los datos, mientras que una **sombra más amplia** indica **mayor incertidumbre y variabilidad** en la relación entre los precios de BTC y el S&P 500.

Estas observaciones y perspectivas gráficas destacan colectivamente cómo BTC y el S&P 500 responden bajo diversas condiciones económicas, demostrando comportamientos distintos y correlaciones que evolucionan con el tiempo.

---

## **En palabras simples**:
- **📊 Entonces, ¿es mayor la correlación entre Bitcoin y el S&P 500 durante períodos de crisis económica?**
  - ✅ ¡Sí! Parece que la correlación entre Bitcoin 🪙 y el S&P 500 💰 es alta 📈, especialmente durante tiempos de crisis económica 🔥🌎📉.

Ver más **observaciones** y **conclusiones** en el notebook:
* [Análisis de Diferentes Crisis y Correlaciones](/5.1_Insights_Analysis_Crisis_And_Correlations.ipynb)

<a id="figure-5"></a>
**Figura 5.** Precios de Bitcoin y S&P durante la crisis del COVID-19 (Precio en USD). [⬆️ Volver](#covid-19_correlation)

![Precios de Bitcoin y S&P durante la crisis del COVID-19](/images/Fig5_BTC_SP500_price_correlations_Covid-19.png)

<a id="figure-6"></a>
**Figura 6.** Precios de Bitcoin y S&P durante la crisis de suministro y energía (Precio en USD). [⬆️ Volver](#supply_energy_correlation)

![Precios de Bitcoin y S&P durante la crisis de suministro y energía](/images/Fig6_BTC_SP500_Price_Correlations_Supply_Crisis.png)

<a id="figure-7"></a>
**Figura 7.** Crisis Económica 2023-2024 (Precio en USD). [⬆️ Volver](#Economic-crisis)

![Crisis Económica 2023-2024](/images/Fig7_BTC_SP500_Price_Correlation_Economic_crisis.png)

<a id="figure-8"></a>
**Figura 8.** Correlación Volumen-Precio BTC vs S&P 500. [⬆️ Volver](#volumen-analysis)

![Correlación Volumen-Precio BTC vs S&P 500](/images/Fig8_BTC_SP500_Volume_Price_correlation.png)

---

<a id="volatility-analysis"></a>

# Bitcoin muestra alta volatilidad en comparación con el S&P 500, pero ¿qué tan volátil es BTC comparado con el S&P 500? [⬆️ Volver a las preguntas principales 🤓](#main-questions)
## Analizando la Volatilidad en Escalas Mensuales y Anuales

### Análisis de Perspectivas (Paso 5.2)

- **Objetivos:**
  - Evaluar y comparar la **volatilidad** de Bitcoin (BTC) y el índice S&P 500 en diferentes escalas de tiempo: **mensual** y **anual**.
  - Analizar y destacar:
    - **Volatilidad Promedio**: Identificar fluctuaciones típicas del mercado.
    - **Pico de Volatilidad**: Evaluar movimientos extremos del mercado.
    - **Diferencias significativas** y **patrones** en la volatilidad entre BTC y el S&P 500 a lo largo del tiempo.
  - Identificar eventos clave que influyen en la volatilidad de ambos activos.
  - Proporcionar una comprensión integral del comportamiento del mercado y los riesgos asociados.

### Observaciones y Conclusiones:

<a id="volatility-monthly"></a>

#### Observaciones clave:
1. **Mayor Volatilidad en Bitcoin**:
  - La volatilidad mensual promedio de Bitcoin es aproximadamente **4.26 veces mayor** **(Ver [Figura 9](#figure-9))** que la del S&P 500.
  - **En su punto máximo**, Bitcoin fue **1.74 veces** más volátil que el pico de volatilidad mensual del S&P 500, indicando que incluso en condiciones extremas del mercado, Bitcoin exhibe un mayor riesgo.
  - Bitcoin es **4.23 veces** más volátil que el S&P 500 en promedio **(anualmente)**. **(Ver [Figura 10](#figure-10))**
  - **En su punto máximo**, Bitcoin fue **2.68 veces** más volátil que el S&P 500 **(anualmente)**.

2. **Patrones de Volatilidad Consistentes**:
   - Bitcoin exhibe consistentemente una volatilidad significativamente mayor en los análisis tanto mensuales como anuales.
   - **(Ver [Figura 11](#figure-11) y [Figura 12](#figure-12))**

3. **Eventos Clave que Influyen en la Volatilidad**: **(Ver [Figura 11](#figure-11))**
   - **Colapso del COVID-19 (2020)**: Aumentos bruscos en la volatilidad de Bitcoin.
   - **Adopción Institucional (finales de 2020)**: Máxima volatilidad observada.
   - **Cambios Regulatorios (2023)**: Nuevas fluctuaciones, aunque menores en comparación con años anteriores.

#### Conclusiones:

1. **Bitcoin como un Activo de Alto Riesgo**:
   - La volatilidad de Bitcoin supera significativamente la del S&P 500, reafirmando su condición como un activo de alto riesgo.

2. **Sensibilidad del Mercado a Eventos Externos**:
   - Tanto Bitcoin como el S&P 500 exhiben sensibilidad a eventos macroeconómicos y regulatorios, pero las respuestas de Bitcoin son más pronunciadas.

3. **Potencial de Diversificación**:
   - A pesar de su volatilidad, Bitcoin podría proporcionar beneficios de diversificación en carteras, particularmente para estrategias de alto riesgo y alta recompensa.

4. **Implicaciones Futuras**:
   - A medida que evoluciona la adopción institucional y la regulación, la volatilidad de Bitcoin podría estabilizarse con el tiempo, aunque es probable que permanezca más alta que la de índices tradicionales como el S&P 500.

---

## **En palabras simples**
- **¿Qué tan volátil es Bitcoin comparado con el S&P 500?**
  - 🪙 ¡Bitcoin exhibe una volatilidad significativamente mayor 📈 que el S&P 500 en casi todas las métricas evaluadas! Esto es especialmente cierto durante eventos extremos, confirmando su naturaleza especulativa y su perfil de alto riesgo.
  - Con un promedio **mensual** aproximadamente **4 veces mayor** que el S&P 500 y prácticamente **la misma tendencia anual**.

Ver más **observaciones** y **conclusiones** en el notebook:
* [Análisis de Volatilidad](/5.2_Insights_Volatility_Monthly_Yearly.ipynb)

<a id="figure-9"></a>
**Figura 9.** Volatilidad Mensual Promedio BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Volatilidad Mensual Promedio BTC vs S&P 500](/images/Fig9_BTC_SP500_Volatility.png)

<a id="figure-10"></a>
**Figura 10.** Volatilidad Anual Promedio BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Volatilidad Anual Promedio BTC vs S&P 500](/images/Fig_10_BTC_SP500_Volatility.png)

<a id="figure-11"></a>
**Figura 11.** Comparación de Volatilidad Mensual BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Comparación de Volatilidad Mensual BTC vs S&P 500](/images/Fig_11_BTC_SP500_Patern_Month.png)

<a id="figure-12"></a>
**Figura 12.** Comparación de Volatilidad Anual BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Comparación de Volatilidad Anual BTC vs S&P 500](/images/Fig_12_BTC_SP500_Patern_Yearly.png)

---

<a id="Returns-Time"></a>

# ¿Qué ofrece mejores retornos: la volatilidad de Bitcoin o la consistencia del S&P 500? [⬆️ Volver a las preguntas principales 🤓](#main-questions)

### Observaciones clave
1. **Retornos en diferentes marcos temporales**:
   - Bitcoin demostró retornos significativamente mayores anuales, trimestrales, mensuales y semanales en comparación con el S&P 500, aunque con mayor volatilidad. **(Ver [Figura 13](#figure-13), [Figura 14](#figure-14), [Figura 15](#figure-15), [Figura 16](#figure-16))**
   - Por ejemplo:
     - En 2017, el retorno anual de Bitcoin fue aproximadamente del 1300%, destacando su crecimiento explosivo durante mercados alcistas.

2. **Ganancias promedio**:
   - Este es otro hallazgo interesante, los retornos promedio para **BTC** y **S&P 500** son:
   - **Promedio semanal**: Bitcoin 0.62% vs. S&P 500 0.23%
   - **Promedio mensual**: Bitcoin 6.42% vs. S&P 500 0.83%
   - **Promedio trimestral**: Bitcoin 28.45% vs. S&P 500 3.03%
   - **Promedio anual**: Bitcoin 224.01% vs. S&P 500 11.85%

   > **Nota**: El año 2017 es un caso atípico notable que afecta significativamente las ganancias promedio anuales de Bitcoin.

3. **Compensación riesgo-recompensa**:
   - A pesar de su volatilidad, Bitcoin superó consistentemente al S&P 500 en la mayoría de las métricas, convirtiéndolo en una **opción atractiva para inversionistas tolerantes al riesgo**.

### Observaciones y Conclusiones
1. **Análisis de rendimiento**:
   - Los retornos de Bitcoin son extraordinarios en mercados alcistas, mientras que el S&P 500 ofrece retornos constantes a lo largo del tiempo.
   - El riesgo asociado con la volatilidad de Bitcoin se compensa con su alto potencial de ganancias sustanciales.

2. **Oportunidades de diversificación**:
   - Incorporar ambos activos en una cartera permite equilibrar los altos retornos de Bitcoin con la estabilidad del S&P 500.

3. **Perspectivas para las partes interesadas**:
   - Los inversores que buscan estabilidad a largo plazo pueden preferir el S&P 500.
   - Los inversores de alto riesgo que buscan retornos exponenciales podrían beneficiarse de Bitcoin.

---

## En palabras simples
- Bitcoin 📈 ofrece un enorme potencial de ganancias, pero es volátil 💥 y riesgoso.
- El S&P 500 📊 es una opción confiable para quienes prefieren un crecimiento constante y estable 💼.
- Combinar estos dos podría ofrecer una estrategia de inversión equilibrada: altos retornos con estabilidad 🌎.

<a id="figure-13"></a>
**Figura 13.** Retornos anuales a lo largo del tiempo. [⬆️ Volver](#Returns-Time)

![Retornos anuales a lo largo del tiempo](/images/Annual_Returns.png)

#### Por ejemplo: Si invertiste una cantidad X en enero de 2017 y luego retiraste tu dinero a finales de diciembre de 2017, habrías obtenido una ganancia del 1300%.

<a id="figure-14"></a>
**Figura 14.** Retornos trimestrales a lo largo del tiempo. [⬆️ Volver](#Returns-Time)

![Retornos trimestrales a lo largo del tiempo](/images/Quarterly_Returns.png)

#### Por ejemplo: Si invertiste una cantidad X en enero de 2017 y luego retiraste tu dinero en marzo de 2017, habrías obtenido una ganancia de ~120%.

<a id="figure-15"></a>
**Figura 15.** Retornos mensuales a lo largo del tiempo. [⬆️ Volver](#Returns-Time)

![Retornos mensuales a lo largo del tiempo](/images/Monthly_Returns.png)

#### Por ejemplo: Si invertiste una cantidad X el 3 de enero de 2017 y luego retiraste tu dinero el 31 de enero de 2017, habrías obtenido una ganancia de ~20%.

<a id="figure-16"></a>
**Figura 16.** Retornos semanales a lo largo del tiempo. [⬆️ Volver](#Returns-Time)

![Retornos semanales a lo largo del tiempo](/images/Weekly_Returns.png)

#### Aquí se muestra básicamente que habrías perdido dinero en la primera semana de 2017 (de hecho, ~10% de pérdida).

Ver más **observaciones** y **conclusiones** en el notebook:
* [Análisis de Retornos](/5.3_Inshights_Cumulative_Returns.ipynb)

--- 

<a id="takeaways"></a>

# Conclusiones clave para las partes interesadas [⬆️ Volver a las preguntas principales 🤓](#main-questions)

1. **Correlaciones en períodos de crisis**  
   - Bitcoin y el S&P 500 muestran correlaciones más fuertes durante períodos de crisis económica, como la pandemia de COVID-19 y la crisis financiera de 2023, con una correlación máxima de **0.90**. Esto sugiere un aumento en la alineación de Bitcoin con los mercados tradicionales bajo el estrés económico global.

2. **Volatilidad y riesgo**  
   - La volatilidad promedio de Bitcoin es **4.26 veces mayor** que la del S&P 500 mensualmente y **4.23 veces mayor** anualmente, convirtiéndolo en un activo de alto riesgo. Sin embargo, esta volatilidad también crea oportunidades para retornos significativos en mercados alcistas.

3. **Retornos superiores**  
   - Bitcoin supera consistentemente al S&P 500 en todos los marcos temporales (semanal, mensual, trimestral y anual). Por ejemplo, el retorno anual promedio de Bitcoin es **224%**, comparado con **11.85%** del S&P 500.

4. **Sensibilidad del mercado**  
   - Bitcoin es altamente reactivo a eventos globales y cambios regulatorios, con picos en los volúmenes de transacciones durante choques del mercado. Esto contrasta con el comportamiento de negociación más estable del S&P 500, destacando la naturaleza especulativa de Bitcoin.

5. **Estrategias de inversión**  
   - Combinar el alto potencial de crecimiento de Bitcoin con la estabilidad del S&P 500 puede equilibrar el riesgo y la recompensa en carteras. Mientras que Bitcoin es adecuado para inversionistas de alto riesgo, el S&P 500 sigue siendo ideal para aquellos que buscan un crecimiento constante y estable.

---

Hecho con amor 💚 por Angel Hackerman 🥷🏻💻 y varias máquinas de IA 🤖. Gracias por tu tiempo 🤗