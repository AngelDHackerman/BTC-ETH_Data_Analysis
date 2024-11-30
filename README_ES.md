#### ⚠️ ¡Descargo de responsabilidad! ¡Esto NO es un consejo financiero! Más detalles [aquí](./Disclaimers/DISCLAIMER_ES.md). 👀

What to read it in English? [click here](/README.md).

Voulez-vous le lire en français? [Cliquez ici](./README_FR.md).

# Comprendiendo Bitcoin y el S&P 500: Un análisis comparativo basado en datos

<a id='main-questions'></a>

## ¿Qué preguntas buscamos responder con este proyecto?

Usando datos públicos, este proyecto intentará responder estas preguntas tan interesantes, además de analizar el comportamiento del Bitcoin y del S&P 500 a lo largo del tiempo: 

0. [Análisis temporal de Bitcoin (BTC) y S&P 500 en los últimos 10 años. **(Semanal, Mensual, Anual)**](#temporal-analysis)
1. [La correlación entre Bitcoin y el S&P 500 es mayor en períodos de crisis económica, ¿es esto cierto?](#correlation-analysis)
2. [Bitcoin muestra una alta volatilidad en comparación con el S&P 500, pero ¿qué tan volátil es BTC en comparación con el S&P 500?](#volatility-analysis)
3. [¿Qué ofrece mejores retornos: la volatilidad del Bitcoin o la consistencia del S&P 500?](#Returns-Time)
4. [**¡Bonus!** Puntos clave para los interesados](#takeaways)

Utilizando diferentes técnicas como:

  * Estadísticas 
  * Análisis
  * Finanzas 
  * Narrativa
  * Pensamiento crítico

Con herramientas como: 

  * __Python__
  * __Numpy__
  * __Pandas__
  * __Matplotlib__
  * __Seaborn__

¡Responderé estas preguntas tan interesantes, disfrútalo!

## **Conjuntos de Datos**
### Resumen

Los conjuntos de datos incluyen precios diarios de Bitcoin y del S&P 500 desde **septiembre de 2014 hasta mayo de 2024**.

### Principales Pasos de Preprocesamiento:

1. **Manejo de Valores Faltantes**:
   - Se eliminaron los valores faltantes para garantizar la integridad de los datos, ya que representaban menos del 1% del conjunto de datos.
2. **Eliminación de Datos de Fin de Semana**:
   - Se alinearon los datos de Bitcoin con los del S&P 500, que solo opera en días hábiles.
3. **Limpieza de Datos**:
   - Se eliminaron duplicados y se garantizó la alineación temporal entre los conjuntos de datos.

## **Flujo de Trabajo del Proyecto**

### Paso 1 y 2: Investigación Inicial
- Se realizó un análisis exploratorio utilizando `.head()`, `.info()` y `.describe()` para comprender los conjuntos de datos.
- Se combinaron archivos relevantes para crear conjuntos de datos unificados para Bitcoin y el índice S&P 500.
- Se aseguró una alta calidad de datos eliminando filas nulas y duplicadas.
- Se cambió el tipo de datos en columnas como 'Date' a `datetime64` para un mejor manejo de los conjuntos de datos.
- Usando el método del Rango Intercuartílico (IQR), se encontraron algunos valores atípicos en ambos conjuntos de datos; estos se mantuvieron para observar los comportamientos del mercado durante eventos extremos.
- Los datos se exportaron en un archivo para BTC y S&P500.

Consulta los detalles adicionales en los notebooks para estos pasos: 
* [Exploración Inicial S&P 500](./1_Inital_Exploration_SP_500.ipynb)
* [Exploración Inicial BTC](./1_Initial_Exploraion_BTC.ipynb)
* [Comparación BTC y S&P 500](./2_BTC_SP500_Comparation.ipynb)

### Paso 3: Evaluación de Calidad

- Se verificó la integridad de los datos comprobando **valores faltantes**, **duplicados** y **rangos de valores lógicos**.
- Los conjuntos de datos están temporalmente alineados, asegurando que ambos tengan intervalos de fechas idénticos.
- Los datos están limpios, consistentes y son confiables en ambos conjuntos de datos.

Consulta las **observaciones** y **conclusiones** adicionales en el notebook:
* [Evaluación de Calidad para BTC y S&P 500](./3_Quality_Evaluation_BTC_SP500.ipynb)

<a id='temporal-analysis'></a>

# Análisis temporal de Bitcoin (BTC) y S&P 500 en los últimos 10 años. **(Semanal, Mensual, Anual)** [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)

- **Objetivo**: Identificar tendencias de precios en intervalos semanales, mensuales, trimestrales y anuales.

- **Resultados**:
  - **Tendencias de Precios**:
    - Bitcoin muestra alta variabilidad a corto plazo, mientras que el S&P 500 presenta un crecimiento estable y consistente. **(Ver [Figura 1](#figure-1))**
    - Las tendencias a largo plazo destacan el crecimiento exponencial y la volatilidad de Bitcoin. **(Ver [Figura 2](#figure-2))**
  - **Tendencias de Volumen**:
    - El volumen de transacciones de Bitcoin se correlaciona con períodos de alta volatilidad de precios, a menudo aumentando durante repuntes o caídas del mercado.
    - El volumen de transacciones del S&P 500 se mantiene relativamente estable, alineándose con su crecimiento consistente.
    - Los aumentos significativos de volumen en Bitcoin a menudo preceden a reversiones de precios, lo que sugiere una fuerte relación entre el sentimiento del mercado y la actividad comercial. **(Ver [Figura 3](#figure-3) y [Figura 4](#figure-4))**
  - **Perspectivas Comparativas**:
    - El volumen de Bitcoin responde altamente a noticias del mercado y eventos macroeconómicos, amplificando su volatilidad.
    - El volumen de operaciones del S&P 500 muestra resiliencia y menor sensibilidad a noticias a corto plazo, indicando una estructura de mercado madura y estable.
    - En ambos casos, en enero de 2018, el precio y volumen de Bitcoin superaron los del S&P 500 y han mantenido esa tendencia desde entonces, por el momento... **(Ver Figuras 1 y 3)** 

---

## **En Palabras Simples**:
  - Bitcoin 🪙 muestra una alta volatilidad y un crecimiento exponencial a largo plazo 📈, con volúmenes de transacciones que aumentan significativamente durante eventos de mercado 📊, mientras que el S&P 500 se mantiene estable y menos sensible a los cambios a corto plazo 🛠️📉. **Desde 2018, Bitcoin ha superado consistentemente al S&P 500 tanto en precio 💸 como en volumen 🔥**.

Consulta las **observaciones** y **conclusiones** adicionales en el notebook:
* [Análisis Temporal para Bitcoin e Índice S&P 500](/4_Temporal_Analysis.ipynb)

<a id="figure-1"></a>
**Figura 1.** Precios Semanales Promedio de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Semanales Promedio de BTC y S&P 500 (USD)](./images/Fig1_weekly_prices_BTC_SP500.png)

<a id="figure-3"></a>
**Figura 3.** Volumen de Transacciones Semanales de BTC y S&P 500 (por cada 1 millón de unidades). [⬆️ Volver](#temporal-analysis)

![Volumen de Transacciones Semanales de BTC y S&P 500](/images/Fig3_weekly_volume_BTC_SP500.png)

**Promedios Mensuales.** Precios Mensuales Promedio de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Mensuales Promedio de BTC y S&P 500 (USD)](/images/monthly_average_price.png)

**Volumen Mensual.** Volumen Mensual de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Volumen Mensual de BTC y S&P 500 (USD)](/images/monthly_total_volume.png)

<a id="figure-2"></a>
**Figura 2.** Precios Anuales Promedio de BTC y S&P 500 (USD). [⬆️ Volver](#temporal-analysis)

![Precios Anuales Promedio de BTC y S&P 500 (USD)](/images/Fig2_annual_prices_BTC_SP500.png)

<a id="figure-4"></a>
**Figura 4.** Volumen Anual de Transacciones de BTC y S&P 500 (por cada 1 millón de unidades). [⬆️ Volver](#temporal-analysis)

![Volumen Anual de Transacciones de BTC y S&P 500](/images/Fig4_annual_volume_BTC_SP500.png)

<a id="correlation-analysis"></a>

# La correlación entre Bitcoin y el S&P 500 es mayor en períodos de crisis económica, ¿es esto cierto? [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)

### Análisis de Perspectivas (Paso 5.1):

- **Objetivo**: El objetivo de este análisis fue explorar la correlación entre Bitcoin (BTC) y el Índice S&P 500 durante la crisis del COVID-19 (marzo 2020 a diciembre 2021), la crisis energética y de suministros (2021-2022), y la crisis financiera (2023-2024).

- **Específicamente, el análisis se centra en**:
  - Comprender el comportamiento de BTC y el S&P 500 durante períodos económicos clave.
  - Comparar tendencias de precios y volúmenes, así como sus correlaciones, para identificar patrones o anomalías potenciales.
  - Resaltar perspectivas que podrían informar estrategias de inversión o gestión de riesgos.

#### Comprendiendo las Correlaciones

  1. **Correlación Positiva**:
    - Si la correlación está más cerca de **1**, indica una **correlación positiva directa**, lo que significa que cuando una variable aumenta, la otra también aumenta.

  2. **Correlación Negativa**:
    - Si la correlación está más cerca de **-1**, indica una **correlación inversa directa**, lo que significa que cuando una variable aumenta, la otra disminuye.

  3. **Sin Correlación**:
    - Cuanto más cerca esté la correlación de **0**, más débil será la relación, indicando **poca o ninguna correlación** entre las dos variables.

### Observaciones y Conclusiones

1. **Tendencias Generales**:
   - BTC y el S&P 500 muestran comportamientos distintos, con BTC mostrando mayor volatilidad en comparación con el movimiento estable del S&P 500.
   - Ambos activos presentan movimientos de precios significativos durante períodos económicos importantes, como la crisis del COVID-19.

<a id='covid-19_correlation'></a>

2. **Análisis del Período COVID-19 (2020–2021)**:
   - Durante la pandemia, BTC experimentó un fuerte aumento de precios **a partir de finales de 2020, coincidiendo con las medidas de estímulo fiscal.** **(Ver [Figura 5, sección superior](#figure-5))**
   - El S&P 500 también se recuperó durante este período, reflejando tendencias similares de recuperación en los mercados tradicionales y de criptomonedas.
   - **Perspectiva de Correlación**: BTC y el S&P 500 demostraron una **correlación moderada a fuerte (0.87)** positiva durante este período, indicando una mayor alineación de los movimientos del mercado. **(Ver [Figura 5, sección inferior](#figure-5))**

<a id='supply_energy_correlation'></a>

3. **Crisis de Energía y Suministros 2021–2022 (Persistencia del COVID y Guerra Ucrania-Rusia)**:
   - El precio y volumen de BTC mostraron alta volatilidad, con caídas significativas durante la escasez global de energía y las interrupciones en la cadena de suministro, junto con la prohibición de Bitcoin en China (sep 2021). **(Ver [Figura 6, sección superior](#figure-6))**
   - El S&P 500 mostró tendencias relativamente estables, destacando resiliencia frente a la alta sensibilidad de BTC a las condiciones del mercado global.
   - **Perspectiva de Correlación**: La correlación entre BTC y el S&P 500 **se debilitó ligeramente (0.60)** durante este período, pero permaneció positiva, lo que sugiere una alineación parcial del mercado en medio de choques externos. **(Ver [Figura 6, sección inferior](#figure-6))**

<a id='Economic-crisis'></a>

4. **Crisis Económica (2023–2024)**:
   - BTC mostró un crecimiento significativo y mantuvo una trayectoria de precios más alta, reflejando un mayor interés de los inversores especulativos que buscan activos alternativos. **(Ver [Figura 7, sección superior](#figure-7))**
   - El S&P 500 presentó tendencias estables con una recuperación gradual, **reforzando su papel como indicador de estabilidad económica.**
   - **Perspectiva de Correlación**: La correlación **se fortaleció (0.90)** durante este período, indicando una **mayor interdependencia entre BTC y los mercados tradicionales** a medida que BTC se integra más en las finanzas globales. **(Ver [Figura 7, sección inferior](#figure-7))**

<a id='volumen-analysis'></a>

5. **Análisis de Volumen**:
   - El volumen de operaciones de BTC aumentó durante períodos de alta volatilidad de precios, mostrando sensibilidad a los eventos del mercado.
   - Los volúmenes del S&P 500, aunque menos volátiles, también aumentaron durante la incertidumbre del mercado.
   - En general, parece que la correlación "volumen-precio" entre Bitcoin y el S&P 500 es **no muy fuerte** y apenas están correlacionados. **(Ver [Figura 8](#figure-8))**

### La "Sombra Roja" en los Gráficos de Correlación

La **sombra roja** en los gráficos de correlación representa el **intervalo de confianza** para la línea de regresión lineal. Este intervalo indica el rango dentro del cual es probable que caiga la verdadera línea de regresión con un cierto nivel de confianza (típicamente 95%). **Una sombra roja más estrecha** sugiere **mayor confianza** y menor variabilidad en los datos, mientras que una **sombra más ancha** indica **mayor incertidumbre y variabilidad** en la relación entre los precios de BTC y el S&P 500.

Estas observaciones y perspectivas gráficas destacan colectivamente cómo BTC y el S&P 500 responden bajo diversas condiciones económicas, demostrando comportamientos distintos y correlaciones en evolución a lo largo del tiempo.

---

## **En Palabras Simples**:
- **📊 Entonces, ¿la correlación entre Bitcoin y el S&P 500 es mayor durante períodos de crisis económica?**
  - ✅ ¡Sí! Parece que la correlación entre Bitcoin 🪙 y el S&P 500 💰 es alta 📈, especialmente durante tiempos de crisis económica 🔥🌎📉.

Consulta las **observaciones** y **conclusiones** adicionales en el notebook:
* [Análisis de Diferentes Crisis y Correlaciones](/5.1_Insights_Analysis_Crisis_And_Correlations.ipynb)

<a id="figure-5"></a>
**Figura 5.** Precios de Bitcoin y S&P Durante la Crisis del COVID-19 (Precio USD). [⬆️ Volver](#covid-19_correlation)

![Precios de Bitcoin y S&P Durante la Crisis del COVID-19](/images/Fig5_BTC_SP500_price_correlations_Covid-19.png)

<a id="figure-6"></a>
**Figura 6.** Precios de Bitcoin y S&P Durante la Crisis de Energía y Suministros (Precio USD). [⬆️ Volver](#supply_energy_correlation)

![Precios de Bitcoin y S&P Durante la Crisis de Energía y Suministros](/images/Fig6_BTC_SP500_Price_Correlations_Supply_Crisis.png)

<a id="figure-7"></a>
**Figura 7.** Crisis Económica 2023-2024 (Precio USD). [⬆️ Volver](#Economic-crisis)

![Crisis Económica 2023-2024](/images/Fig7_BTC_SP500_Price_Correlation_Economic_crisis.png)

<a id="figure-8"></a>
**Figura 8.** Correlación Volumen-Precio BTC vs S&P 500. [⬆️ Volver](#volumen-analysis)

![Correlación Volumen-Precio BTC vs S&P 500](/images/Fig8_BTC_SP500_Volume_Price_correlation.png)

---

<a id="volatility-analysis"></a>

# Bitcoin muestra alta volatilidad en comparación con el S&P 500, pero ¿qué tan volátil es BTC en comparación con el S&P 500? [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)
## Análisis de Volatilidad en Escalas Mensuales y Anuales

### Análisis de Perspectivas (Paso 5.2)

- **Objetivos:**
  - Evaluar y comparar la **volatilidad** de Bitcoin (BTC) y del Índice S&P 500 en diferentes escalas de tiempo: **mensuales** y **anuales**.
  - Analizar y destacar:
    - **Volatilidad Promedio**: Identificar las fluctuaciones típicas del mercado.
    - **Pico de Volatilidad**: Evaluar los movimientos extremos del mercado.
    - **Diferencias significativas** y **patrones** de volatilidad entre BTC y el S&P 500 a lo largo del tiempo.
  - Identificar eventos clave que influyen en la volatilidad de ambos activos.
  - Proporcionar una comprensión integral del comportamiento del mercado y los riesgos asociados.

### Observaciones y Conclusiones:

<a id="volatility-monthly"></a>

#### Observaciones Clave:
1. **Mayor Volatilidad en Bitcoin**:
  - La volatilidad mensual promedio de Bitcoin es aproximadamente **4.26 veces mayor** **(Ver [Figura 9](#figure-9))** que la del S&P 500.
  - **En su pico**, Bitcoin fue **1.74 veces** más volátil que el pico de volatilidad mensual del S&P 500, lo que indica que incluso durante condiciones extremas del mercado, Bitcoin exhibe mayor riesgo.
  - Bitcoin es **4.23 veces** más volátil que el S&P 500 en promedio **(anualmente)**. **(Ver [Figura 10](#figure-10))**
  - **En su pico**, Bitcoin fue **2.68 veces** más volátil que el S&P 500 **(anualmente)**.

2. **Patrones Consistentes de Volatilidad**:
   - Bitcoin muestra consistentemente una volatilidad significativamente mayor en los análisis mensuales y anuales.
   - **(Ver [Figura 11](#figure-11) y [Figura 12](#figure-12))**

3. **Eventos Clave que Influyen en la Volatilidad**: **(Ver [Figura 11](#figure-11))**
   - **Crisis del COVID-19 (2020)**: Aumentos abruptos en la volatilidad de Bitcoin.
   - **Adopción Institucional (finales de 2020)**: Se observa la volatilidad máxima.
   - **Cambios Regulatorios (2023)**: Nuevas fluctuaciones, aunque reducidas en comparación con años anteriores.

#### Conclusiones:

1. **Bitcoin como Activo de Alto Riesgo**:
   - La volatilidad de Bitcoin supera significativamente a la del S&P 500, reafirmando su estatus como un activo de alto riesgo.

2. **Sensibilidad del Mercado a Eventos Externos**:
   - Tanto Bitcoin como el S&P 500 muestran sensibilidad a eventos macroeconómicos y regulatorios, pero las respuestas de Bitcoin son más pronunciadas.

3. **Potencial de Diversificación**:
   - A pesar de su volatilidad, Bitcoin podría ofrecer beneficios de diversificación en carteras, particularmente para estrategias de alto riesgo y alta recompensa.

4. **Implicaciones Futuras**:
   - A medida que la adopción institucional y la regulación evolucionen, la volatilidad de Bitcoin podría estabilizarse con el tiempo, aunque es probable que permanezca más alta que la de índices tradicionales como el S&P 500.

---

## **En Palabras Simples**
- **¿Qué tan volátil es Bitcoin en comparación con el S&P 500?**
  - 🪙 Bitcoin muestra una volatilidad significativamente mayor 📈 que el S&P 500 en casi todas las métricas evaluadas. Esto es especialmente cierto durante eventos extremos, confirmando su naturaleza especulativa y perfil de alto riesgo.
  - Con un promedio **mensual** aproximadamente **4 veces mayor** que el S&P 500 y prácticamente **la misma volatilidad anual**.

Consulta las **observaciones** y **conclusiones** adicionales en el notebook:
* [Análisis de Volatilidad](/5.2_Insights_Volatility_Monthly_Yearly.ipynb)

<a id="figure-9"></a>
**Figura 9.** Volatilidad Mensual Promedio BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Volatilidad Mensual Promedio BTC vs S&P 500](/images/Fig9_BTC_SP500_Volatility.png)

<a id="figure-10"></a>
**Figura 10.** Volatilidad Anual Promedio BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Volatilidad Anual Promedio BTC vs S&P 500](/images/Fig_10_BTC_SP500_Volatility.png)

<a id="figure-11"></a>
**Figura 11.** Comparación Mensual de Volatilidad BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Comparación Mensual de Volatilidad BTC vs S&P 500](/images/Fig_11_BTC_SP500_Patern_Month.png)

<a id="figure-12"></a>
**Figura 12.** Comparación Anual de Volatilidad BTC vs S&P 500. [⬆️ Volver](#volatility-monthly)

![Comparación Anual de Volatilidad BTC vs S&P 500](/images/Fig_12_BTC_SP500_Patern_Yearly.png)

---

<a id="Returns-Time"></a>

# ¿Qué Ofrece Mejores Retornos: La Volatilidad de Bitcoin o la Consistencia del S&P 500? [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)

### Observaciones Clave
1. **Retornos en Diferentes Períodos de Tiempo**:
   - Bitcoin mostró retornos anuales, trimestrales, mensuales y semanales significativamente más altos en comparación con el S&P 500, aunque con mayor volatilidad. **(Ver [Figura 13](#figure-13), [Figura 14](#figure-14), [Figura 15](#figure-15), [Figura 16](#figure-16))**
   - Por ejemplo:
     - En 2017, el retorno anual de Bitcoin fue aproximadamente del 1300%, destacando su crecimiento explosivo durante los mercados alcistas.

2. **Promedios de Ganancias**:
   - Otro hallazgo interesante son los retornos promedio para **BTC** y **S&P 500**:
   - **Promedio Semanal**: Bitcoin 0.62% vs. S&P 500 0.23%
   - **Promedio Mensual**: Bitcoin 6.42% vs. S&P 500 0.83%
   - **Promedio Trimestral**: Bitcoin 28.45% vs. S&P 500 3.03%
   - **Promedio Anual**: Bitcoin 224.01% vs. S&P 500 11.85%

   > **Nota**: El año 2017 es un caso atípico notable que afecta significativamente los retornos anuales promedio de Bitcoin.

3. **Compensación Riesgo-Recompensa**:
   - A pesar de su volatilidad, Bitcoin superó constantemente al S&P 500 en la mayoría de las métricas, haciéndolo una **opción atractiva para inversores tolerantes al riesgo**.

### Observaciones y Conclusiones
1. **Análisis de Rendimiento**:
   - Los retornos de Bitcoin son extraordinarios en los mercados alcistas, mientras que el S&P 500 proporciona retornos constantes a lo largo del tiempo.
   - El riesgo asociado a la volatilidad de Bitcoin se compensa con su alto potencial de ganancias sustanciales.

2. **Oportunidades de Diversificación**:
   - Incorporar ambos activos en una cartera permite equilibrar los altos retornos de Bitcoin con la estabilidad del S&P 500.

3. **Perspectivas para los Interesados**:
   - Los inversores que buscan estabilidad a largo plazo pueden preferir el S&P 500.
   - Los inversores de alto riesgo que buscan retornos exponenciales podrían beneficiarse de Bitcoin.

---

## En Palabras Simples
- Bitcoin 📈 ofrece un enorme potencial de ganancias, pero es volátil 💥 y arriesgado.
- El S&P 500 📊 es una opción confiable para quienes prefieren un crecimiento estable y constante 💼.
- Combinar ambos podría ofrecer una estrategia de inversión equilibrada: altos retornos con estabilidad 🌎.

<a id="figure-13"></a>
**Figura 13.** Retornos Anuales a lo Largo del Tiempo. [⬆️ Volver](#Returns-Time)

![Retornos Anuales a lo Largo del Tiempo](/images/Annual_Returns.png)

#### Por ejemplo: Si invirtieras X cantidad en enero de 2017 y luego retiraras tu dinero a finales de diciembre de 2017, habrías tenido una ganancia del 1300%.

<a id="figure-14"></a>
**Figura 14.** Retornos Trimestrales a lo Largo del Tiempo. [⬆️ Volver](#Returns-Time)

![Retornos Trimestrales a lo Largo del Tiempo](/images/Quarterly_Returns.png)

#### Por ejemplo: Si invirtieras X cantidad en enero de 2017 y luego retiraras tu dinero en marzo de 2017, habrías tenido una ganancia de ~120%.

<a id="figure-15"></a>
**Figura 15.** Retornos Mensuales a lo Largo del Tiempo. [⬆️ Volver](#Returns-Time)

![Retornos Mensuales a lo Largo del Tiempo](/images/Monthly_Returns.png)

#### Por ejemplo: Si invirtieras X cantidad el 3 de enero de 2017 y luego retiraras tu dinero el 31 de enero de 2017, habrías tenido una ganancia de ~20%.

<a id="figure-16"></a>
**Figura 16.** Retornos Semanales a lo Largo del Tiempo. [⬆️ Volver](#Returns-Time)

![Retornos Semanales a lo Largo del Tiempo](/images/Weekly_Returns.png)

#### Aquí se muestra básicamente que habrías perdido dinero en la primera semana de 2017 (en realidad, ~10% de pérdida).

Consulta las **observaciones** y **conclusiones** adicionales en el notebook:
* [Análisis de Retornos](/5.3_Inshights_Cumulative_Returns.ipynb)

--- 

<a id="takeaways"></a>

# **¡Bonus!** Puntos clave para los interesados [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)

1. **Correlaciones Durante Períodos de Crisis**  
   - Bitcoin y el S&P 500 muestran correlaciones más fuertes durante períodos de crisis económica, como la pandemia de COVID-19 y la crisis financiera de 2023, con una correlación máxima de **0.90**. Esto sugiere una mayor alineación de Bitcoin con los mercados tradicionales bajo el estrés económico global.

2. **Volatilidad y Riesgo**  
   - La volatilidad promedio de Bitcoin es **4.26 veces mayor** que la del S&P 500 mensual y **4.23 veces mayor** anual, lo que lo convierte en un activo de alto riesgo. Sin embargo, esta volatilidad también crea oportunidades de retornos significativos en mercados alcistas.

3. **Retornos Superiores**  
   - Bitcoin supera consistentemente al S&P 500 en todos los períodos de tiempo (semanal, mensual, trimestral y anual). Por ejemplo, el retorno promedio anual de Bitcoin es del **224%**, en comparación con el **11.85%** del S&P 500.

4. **Sensibilidad del Mercado**  
   - Bitcoin es altamente reactivo a eventos globales y cambios regulatorios, con picos en los volúmenes de transacciones durante choques del mercado. Esto contrasta con el comportamiento más estable del S&P 500, destacando la naturaleza especulativa de Bitcoin.

5. **Estrategias de Inversión**  
   - Combinar el alto potencial de crecimiento de Bitcoin con la estabilidad del S&P 500 puede equilibrar el riesgo y la recompensa en las carteras. Mientras que Bitcoin se adapta a inversores de alto riesgo, el S&P 500 sigue siendo ideal para aquellos que buscan un crecimiento constante y estable.

---

Hecho con amor 💚 por Angel Hackerman 🥷🏻💻 y varias máquinas de IA 🤖. ¡Gracias por tu tiempo! 🤗

