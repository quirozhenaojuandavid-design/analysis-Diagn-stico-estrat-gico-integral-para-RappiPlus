# 📊 Diagnóstico Estratégico Integral – RappiPlus

## 📌 Descripción del proyecto

Este proyecto corresponde al análisis integral de datos de **RappiPlus**, desarrollado como proyecto final de formación en análisis de datos.

El objetivo principal fue transformar diferentes fuentes de información en **insights de negocio** que permitieran evaluar el comportamiento de las ventas, los costos, la rentabilidad, el desempeño del marketing, el comportamiento de los clientes y el impacto de una modificación en el proceso de checkout.

El proyecto integra procesos de **limpieza y transformación de datos, análisis exploratorio, SQL, Python, análisis estadístico y visualización en Power BI**, con el propósito de construir una visión estratégica del desempeño del negocio.

---

## 🎯 Objetivos

### Objetivo general

Realizar un diagnóstico estratégico de RappiPlus mediante el análisis de datos de ventas, productos, marketing y comportamiento de los usuarios, identificando oportunidades y problemas relacionados con la rentabilidad y el desempeño comercial.

### Objetivos específicos

- Analizar la calidad y estructura de las bases de datos.
- Limpiar y preparar los datos para el análisis.
- Evaluar el comportamiento de las ventas y los ingresos.
- Analizar costos y rentabilidad por producto y categoría.
- Analizar el comportamiento del funnel de conversión.
- Evaluar la retención y comportamiento de los clientes.
- Analizar el desempeño de los canales de marketing.
- Evaluar mediante una prueba A/B el impacto de un cambio en el checkout.
- Construir un dashboard ejecutivo en Power BI.
- Generar conclusiones y recomendaciones orientadas a la toma de decisiones.

---

## 🗂️ Fuentes de datos

El proyecto utiliza diferentes conjuntos de datos relacionados con la operación de RappiPlus:

### `orders_clean`

Contiene información relacionada con los pedidos realizados por los clientes, incluyendo:

- Identificador del pedido.
- Fecha y hora del pedido.
- Producto.
- Categoría.
- Cantidad.
- Monto total.
- Información relacionada con la compra.

### `catalog_clean`

Contiene información del catálogo de productos, incluyendo:

- Nombre del producto.
- Categoría.
- Costo unitario.

Esta información fue utilizada principalmente para calcular los costos asociados a los pedidos y analizar la rentabilidad.

### `marketing_clean`

Contiene información relacionada con la inversión en marketing, incluyendo:

- Canal.
- Gasto de marketing.
- Fuente de referencia.

### `experiment_checkout_ui.csv`

Contiene los resultados del experimento A/B realizado para evaluar una modificación en la interfaz del proceso de checkout.

Las principales variables utilizadas fueron:

- Usuario.
- Variante.
- Conversión.
- Dispositivo.
- País.
- Duración de sesión.
- Timestamp.

---

# 🧹 1. Limpieza y preparación de datos

Como primera etapa se realizó un proceso de exploración y preparación de las bases de datos.

Se revisaron:

- Tipos de datos.
- Valores faltantes.
- Registros duplicados.
- Valores atípicos.
- Consistencia de las variables.
- Rangos de cantidades.
- Coherencia entre las diferentes tablas.

Posteriormente se realizaron transformaciones para obtener conjuntos de datos adecuados para el análisis.

En el caso de los pedidos se creó una versión filtrada denominada:

`orders_dashboard`

Esta tabla permitió trabajar con pedidos cuya cantidad de productos se encontraba dentro del rango definido para el análisis.

También se construyó una dimensión calendario:

`dim_fecha`

que permitió realizar análisis temporales en Power BI.

---

# 🐍 2. Análisis con Python

Python fue utilizado para realizar procesos de exploración, limpieza, transformación y análisis estadístico.

Entre las principales herramientas utilizadas se encuentran:

- `pandas`
- `numpy`
- `matplotlib`
- Análisis estadístico
- Manipulación de DataFrames
- Tratamiento de valores atípicos
- Percentiles
- Funciones estadísticas

Durante esta etapa se trabajó en:

- Limpieza de datos.
- Análisis descriptivo.
- Identificación de valores atípicos.
- Transformación de variables.
- Análisis de comportamiento de clientes.
- Análisis de conversión.
- Preparación de datos para visualización.

También se utilizaron técnicas como percentiles y funciones de `numpy`, incluyendo `np.clip()`, para el tratamiento de valores extremos cuando fue necesario.

---

# 🗄️ 3. Análisis con SQL

SQL fue utilizado para realizar consultas y análisis estructurados sobre los datos.

Se trabajó principalmente en:

- Filtrado de registros.
- Agrupaciones.
- Cálculos agregados.
- Conteos.
- Promedios.
- Análisis por categorías.
- Análisis de comportamiento de usuarios.
- Construcción de métricas para el análisis del negocio.

El uso de SQL permitió realizar consultas directamente sobre los datos y obtener información relevante para las etapas posteriores del análisis.

---

# 📈 4. Análisis de ventas y rentabilidad

Uno de los principales componentes del proyecto fue evaluar el desempeño comercial de RappiPlus.

Se analizaron indicadores como:

- Ingresos totales.
- Costos totales.
- Profit.
- Margen.
- Ticket promedio.
- Cantidad promedio de productos por pedido.
- Ingresos por categoría.
- Profit por categoría.
- Cantidad vendida por producto.

### Principales resultados

El dashboard permitió identificar ingresos aproximados de:

**863 millones**

Sin embargo, los costos calculados superan ampliamente los ingresos, generando un resultado negativo de aproximadamente:

**-3.000 millones**

El ticket promedio se ubicó alrededor de:

**35,11 mil**

Mientras que el promedio de productos por pedido fue aproximadamente:

**15 productos.**

El margen calculado presentó un resultado negativo cercano al:

**-329 %**

Estos resultados muestran que el principal desafío del negocio no está únicamente relacionado con la generación de ventas, sino con la **estructura de costos y la rentabilidad de las operaciones**.

---

# 🛒 5. Análisis por categoría

Se analizaron los ingresos y el profit de las diferentes categorías de productos.

Entre las categorías analizadas se encuentran:

- Electrónica.
- Hogar.
- Moda.

Los ingresos presentan comportamientos relativamente similares entre las categorías.

Sin embargo, el análisis de rentabilidad muestra resultados negativos en las categorías analizadas.

La categoría de **Electrónica** presenta el resultado negativo más significativo en términos de profit.

Esto evidencia que un alto nivel de ingresos no necesariamente significa una operación rentable.

---

# 📣 6. Análisis de marketing

Se analizó el gasto de marketing por canal.

Los canales considerados fueron:

- Social.
- Organic.
- Paid Search.

El gasto total de marketing observado en el dashboard fue aproximadamente:

**247 millones.**

La distribución de la inversión entre los diferentes canales es relativamente equilibrada.

Sin embargo, para tomar decisiones de reasignación presupuestal sería necesario complementar este análisis con indicadores de desempeño como:

- ROI.
- ROAS.
- Conversión por canal.
- Ingresos generados por canal.
- Costo de adquisición de clientes.

Por lo tanto, el análisis permite identificar cuánto se está invirtiendo, pero se recomienda profundizar en la relación entre inversión y resultados obtenidos.

---

# 👥 7. Análisis del funnel y comportamiento de clientes

Se realizó un análisis del proceso de conversión para identificar el comportamiento de los usuarios a través del funnel.

Este análisis permitió evaluar las diferentes etapas del proceso y detectar posibles puntos de pérdida de usuarios.

También se trabajó sobre el comportamiento de los clientes y la retención mediante análisis de cohortes.

El análisis de cohortes permite comparar grupos de usuarios según su fecha de adquisición y observar su comportamiento a lo largo del tiempo.

Estas herramientas permiten complementar el análisis financiero con una perspectiva centrada en el comportamiento del cliente.

---

# 🧪 8. Prueba A/B – Checkout

Se realizó una prueba A/B para evaluar una modificación en la interfaz del proceso de checkout.

Se compararon dos grupos:

- **Control**
- **Treatment**

### Resultados

| Grupo | Usuarios | Conversión |
|---|---:|---:|
| Control | 4.965 | 15,69 % |
| Treatment | 5.035 | 16,29 % |

La diferencia observada fue de aproximadamente:

**+0,60 puntos porcentuales**

Aunque el grupo Treatment presentó una conversión ligeramente superior, se realizó una prueba estadística para determinar si esta diferencia era significativa.

### Resultado estadístico

- Estadístico Z: **-0,8133**
- p-value: **0,4161**
- Nivel de significancia: **0,05**

Dado que:

**p-value > 0,05**

no existe evidencia estadísticamente significativa suficiente para rechazar la hipótesis nula.

### Conclusión del experimento

La modificación realizada en el checkout **no demuestra una mejora estadísticamente significativa en la conversión**.

Por lo tanto, con los datos disponibles, no se recomienda afirmar que el nuevo diseño haya generado una mejora real en la conversión.

---

# 📊 9. Dashboard en Power BI

Se construyó un dashboard interactivo en Power BI compuesto por dos vistas principales.

## Dashboard 1 – Overview Ejecutivo

El objetivo de esta vista es proporcionar una visión general del desempeño del negocio.

### KPIs

Se incorporaron los siguientes indicadores:

- Revenue Total.
- Costo Total.
- Profit Total.
- Gasto de Marketing.
- Ticket Promedio.
- Margen %.

### Visualizaciones

El dashboard incluye:

- Evolución mensual de ingresos y costos.
- Ingresos por categoría.
- Profit por categoría.
- Gasto de marketing por canal.
- Filtro por periodo.
- Filtro por categoría.

La visualización permite identificar rápidamente la relación entre ingresos, costos y rentabilidad.

---

## Dashboard 2 – Detalle de pedidos y rentabilidad

Esta vista permite realizar un análisis más detallado de los pedidos y productos.

La tabla incluye:

- ID del pedido.
- Fecha.
- Producto.
- Categoría.
- Cantidad.
- Monto total.
- Costo total.
- Profit total.

También se incorporó formato condicional para identificar visualmente resultados positivos y negativos de profit.

Adicionalmente, se construyó un gráfico de barras con la:

**Cantidad vendida por producto**

Entre los productos con mayor volumen de unidades se identificaron:

- Vacuum-Pro-Black.
- Blender-XL-Red.
- Jacket-Winter-M.
- Sneakers-Urban-42.
- Laptop-Gaming-16GB.
- Tablet-Standard-64GB.
- Phone-Pro-128GB.

Este análisis permitió observar que los productos con mayor volumen de ventas no necesariamente son los productos con mayor rentabilidad.

---

# 💡 10. Principales Insights

### 1. El principal problema identificado es la rentabilidad

Aunque RappiPlus presenta un volumen importante de ingresos, los costos calculados superan ampliamente los ingresos.

Esto genera un resultado negativo y evidencia la necesidad de revisar la estructura de costos y precios.

### 2. Las ventas no garantizan rentabilidad

Las categorías presentan niveles de ingresos importantes, pero sus resultados de profit son negativos.

Por lo tanto, la estrategia comercial debe considerar no solamente el volumen de ventas, sino también el margen generado por cada producto.

### 3. Electrónica requiere especial atención

La categoría de Electrónica presenta uno de los resultados negativos más importantes en términos de profit.

Se recomienda revisar:

- Costos de adquisición.
- Precios.
- Descuentos.
- Margen por producto.
- Productos de baja rentabilidad.

### 4. El volumen de ventas debe analizarse junto con el margen

Los productos con mayor cantidad de unidades vendidas no necesariamente representan los mayores aportes económicos.

Por esta razón, la toma de decisiones debe combinar:

**Volumen + ingresos + costos + profit.**

### 5. La inversión en marketing requiere análisis de eficiencia

La inversión en marketing representa aproximadamente 247 millones.

Aunque la distribución por canal es relativamente equilibrada, es necesario relacionar el gasto con los resultados obtenidos para determinar qué canales generan mayor retorno.

### 6. El cambio en checkout no mostró impacto significativo

La prueba A/B mostró una diferencia positiva de 0,60 puntos porcentuales en conversión a favor del tratamiento.

Sin embargo, el p-value de 0,4161 indica que esta diferencia no es estadísticamente significativa.

Por lo tanto, no existe evidencia suficiente para afirmar que el nuevo checkout haya mejorado la conversión.

---

# 🎯 11. Recomendaciones estratégicas

A partir de los resultados obtenidos se plantean las siguientes recomendaciones:

### Rentabilidad

- Revisar la estructura de costos de los productos.
- Identificar productos con margen negativo.
- Evaluar estrategias de precios.
- Priorizar productos con mejor contribución al profit.
- Analizar costos de adquisición y operación.

### Productos

- Clasificar los productos según volumen, ingresos y rentabilidad.
- Identificar productos de alta demanda pero bajo margen.
- Evaluar estrategias diferenciadas para productos de alta y baja rentabilidad.

### Marketing

- Medir ROI y ROAS por canal.
- Relacionar inversión con conversiones e ingresos.
- Optimizar la distribución del presupuesto según desempeño.
- Profundizar en el costo de adquisición de clientes.

### Conversión

- Continuar realizando experimentos A/B.
- Probar nuevas modificaciones del checkout.
- Aumentar el tamaño de muestra cuando sea necesario.
- Evaluar diferentes segmentos de usuarios y dispositivos.

### Toma de decisiones

Se recomienda utilizar el dashboard como herramienta de seguimiento periódico para monitorear:

**Ingresos → Costos → Profit → Marketing → Conversión**

Esto permitiría pasar de un análisis descriptivo a un sistema de seguimiento continuo del desempeño del negocio.

---

# 🛠️ Herramientas utilizadas

- **Python**
  - Pandas
  - NumPy
  - Matplotlib
- **SQL**
- **Power BI**
  - DAX
  - Modelado de datos
  - Relaciones entre tablas
  - Medidas
  - KPIs
  - Visualizaciones interactivas
- **Jupyter Notebook**
- **GitHub**

---

# 📂 Estructura del proyecto

```text
analisis-estrategico-integral-rappiplus/
│
├── README.md
│
├── Proyecto_Final_RappiPlus.ipynb
│
├── data/
│   ├── orders_clean.csv
│   ├── catalog_clean.csv
│   ├── marketing_clean.csv
│   └── experiment_checkout_ui.csv
│
└── powerbi/
    └── Dashboard_RappiPlus.pbix
