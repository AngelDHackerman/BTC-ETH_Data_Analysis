#### ⚠️ ¡Descargo de responsabilidad! ¡Esto NO es un consejo financiero! Más detalles [aquí](./disclaimers/DISCLAIMER.md). 👀

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

# ¿Es cierto que la correlación entre Bitcoin y el S&P 500 es mayor en períodos de crisis económica? [⬆️ Volver a las Preguntas Principales 🤓](#main-questions)

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