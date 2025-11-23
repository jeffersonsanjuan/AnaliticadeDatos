# AnaliticadeDatos

# Evidencia de Aprendizaje 1 — Análisis de Rentabilidad Empresarial en Colombia

## Introducción
Este documento corresponde al primer avance del proyecto de Analítica de Datos.  
En esta fase se define el problema de análisis, se describe la fuente de información y se establecen los objetivos, hipótesis y métricas que guiarán el estudio sobre la rentabilidad de las empresas más grandes de Colombia.

---

## Tema
**Análisis de rentabilidad empresarial en Colombia**

---

## Link Dataset
[https://www.datos.gov.co/Comercio-Industria-y-Turismo/Empresas-m-s-Grandes-del-Pa-s/yi6q-b4bn](https://www.datos.gov.co/Comercio-Industria-y-Turismo/Empresas-m-s-Grandes-del-Pa-s/yi6q-b4bn)

---

## Tamaño del dataset
- **Filas:** 14  
- **Columnas:** 40.000  

---

## Fuente
[https://www.datos.gov.co/](https://www.datos.gov.co/)

---

## Objetivo de análisis
**Analizar la relación entre el tamaño, la rentabilidad y la ubicación geográfica de las empresas más grandes de Colombia, identificando patrones que contribuyan a la toma de decisiones estratégicas en el ámbito empresarial.**

---

## Pregunta de investigación
**¿Cómo varía la rentabilidad de las empresas más grandes de Colombia según su tamaño y ubicación geográfica?**

---

## Hipótesis
- Las empresas ubicadas en Bogotá y Antioquia presentan mayores niveles de rentabilidad promedio debido a su concentración de capital y acceso a infraestructura.  
- Existe una relación positiva entre el tamaño de la empresa y su nivel de rentabilidad.

---

## Métricas de éxito
Para evaluar el éxito del análisis y la validez de la hipótesis, se tomarán en cuenta las siguientes métricas:

- Rentabilidad promedio por departamento.  
- Rentabilidad promedio según el tamaño de la empresa.  
- Correlación entre tamaño de empresa y rentabilidad.  
- Distribución geográfica de las empresas con mayores ingresos y utilidades.

---

## Qué datos tengo para lograr el objetivo
El dataset incluye datos económicos como ingresos operacionales, utilidad neta, activos y patrimonio, junto con información de localización y tamaño de las empresas, lo cual permite analizar patrones de rentabilidad empresarial en Colombia.

---

## ¿Cómo se llaman las columnas y qué significan? (Diccionario de datos)

| Columna | Descripción |
|----------|-------------|
| NIT | Número de Identificación Tributaria de la empresa. |
| RAZÓN SOCIAL | Nombre registrado legalmente de la empresa. |
| SUBSECTOR ECONÓMICO | Actividad económica a la que pertenece. |
| INGRESOS OPERACIONALES | Valor de los ingresos por actividades económicas. |
| UTILIDAD NETA | Ganancia o pérdida neta del periodo. |
| ACTIVOS TOTALES | Recursos económicos totales de la empresa. |
| PATRIMONIO | Valor neto contable. |
| DEPARTAMENTO | Ubicación geográfica principal. |
| TAMAÑO EMPRESA | Clasificación según ingresos o empleados. |

---

## Tipos de datos

| Variable | Tipo de dato |
|-----------|---------------|
| NIT | Texto |
| RAZÓN SOCIAL | Categórico |
| SUBSECTOR ECONÓMICO | Categórico |
| INGRESOS OPERACIONALES | Numérico |
| UTILIDAD NETA | Numérico |
| ACTIVOS TOTALES | Numérico |
| PATRIMONIO | Numérico |
| DEPARTAMENTO | Categórico |
| TAMAÑO EMPRESA | Categórico |

---

## ¿Estos datos me sirven para lograr el objetivo?
**Sí, los datos del dataset “10.000 Empresas más Grandes del País” permiten identificar relaciones entre tamaño, rentabilidad y ubicación de las empresas, por lo que son adecuados para el análisis propuesto.**

---
---
---

## Análisis del Dataset “10.000 Empresas más Grandes del País”

### Duplicados

0 registros duplicados

https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/69102221e98ea47cced623e3/download/image.png

Cada empresa tiene un registro único.

---

### Valores nulos

Se encuentran 2 valores nulos en la columna `RAZÓN SOCIAL`.

https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/691022879f0d20482256370b/download/image.png

Esos dos casos deben revisarse, ya que podrían corresponder a errores de digitación o registros sin razón social asignada.

---

### Tipos de Datos

Todas las columnas están actualmente como **texto** (`object`).  
Incluye tanto variables categóricas (como **REGIÓN**, **MACROSECTOR**, **CIUDAD**)  
como variables numéricas representadas como texto (**INGRESOS OPERACIONALES**, **GANANCIA (PÉRDIDA)**, **TOTAL ACTIVOS**, etc.).

https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/691023c057ef254664d3ea21/download/image.png

Antes de cualquier análisis numérico o cálculo, será necesario **convertir las columnas financieras a tipo numérico (`float` o `int`)**, eliminando símbolos como `$`, `,` o espacios.

---

### Distribuciones

Aunque todavía están en formato texto, se espera que:

- Las **variables financieras** (*INGRESOS OPERACIONALES*, *TOTAL ACTIVOS*, *PATRIMONIO*) muestren una **distribución fuertemente sesgada a la derecha**, con pocas empresas de muy alto valor y muchas de menor tamaño.  
- Las **variables categóricas** como *MACROSECTOR* o *REGIÓN* concentren gran parte de los registros en pocas categorías dominantes (por ejemplo, *Comercio* o *Bogotá D.C.*).

https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/6910245efb729c2b4f2f7b94/download/image.png

Se recomienda aplicar una **transformación logarítmica o escalamiento** después de convertirlas a numéricas para obtener análisis más estables.

---

### Correlaciones

Por ahora **no se pueden calcular correlaciones válidas**, ya que las columnas numéricas están en formato texto.  
Una vez convertidas, se espera encontrar:

- Alta **correlación positiva** entre *TOTAL ACTIVOS*, *TOTAL PASIVOS* y *PATRIMONIO*.  
- Posible **relación entre INGRESOS OPERACIONALES y GANANCIA (PÉRDIDA)*.*

https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/6910257b81555a3a74144e1f/download/image.png

Esto puede ayudar a identificar **indicadores financieros clave** o **redundancias entre variables**.

---

### Estadísticas descriptivas generales

Después de limpiar los datos numéricos, el análisis mostrará:

- **Valores máximos y mínimos extremos**, dada la gran diferencia entre empresas.  
- **Media mucho mayor que la mediana**, típica de distribuciones sesgadas.  
- **Desviaciones estándar altas**, reflejando la heterogeneidad del tamaño empresarial.

# I. Descripción de necesidades de limpieza

## Resumen

•	Filas: 40.000
•	Columnas: 14
•	Años de corte presentes (muestra): ['2,022', '2,021', '2,023', '2,024'] (formato con comas — problema de formato).
•	Columnas numéricas como texto: INGRESOS OPERACIONALES, GANANCIA (PÉRDIDA), TOTAL ACTIVOS, TOTAL PASIVOS, TOTAL PATRIMONIO.
•	Duplicados detectados (observados):
o	Duplicados por NIT: 26.024 (es decir, muchos NIT se repiten).
o	Duplicados por RAZÓN SOCIAL: 21.383.
o	Duplicados exactos sobre todas las columnas: 0 (no hay filas exactamente idénticas).
o	Observación: la presencia de varios años de corte sugiere que los NIT se repiten por año; por eso hay muchos NIT repetidos — esto es esperado si el dataset contiene múltiples registros por empresa en distintos años.
•	NIT: todas las filas contienen caracteres no-numéricos (como por ejemplo comas): contador 40.000 (se debe normalizar).

### 1) Duplicados

 bservación:
•	Hay muchos valores repetidos en NIT (26.024) y en RAZÓN SOCIAL (21.383). Pero no hay filas exactamente idénticas en todas las columnas (duplicados exactos = 0).
Interpretación:
•	El dataset contiene múltiples años de corte (2021–2024) es normal que un mismo NIT aparezca varias veces ya que sería un registro por empresa por año.
•	Por ello, no se deben eliminar en bloque las filas con NIT repetido sin primero considerar el año. Lo mejor es verificar duplicados por NIT y Año de Corte, y si es necesario por NIT, Año de Corte y CIIU.
Acción recomendada:
•	Comprobar duplicados por NIT, Año de Corte.
•	Si aparecen duplicados por NIT, Año de Corte entonces investigar qué columnas difieren (posibles errores de entrada, múltiples sedes o registros paralelos).
•	Consolidar registros por NIT, Año si la unidad de análisis es empresa–año o mantener todos los registros si representan unidades distintas (sucursales).

### 2) Valores nulos

Observación:
•	Solo RAZÓN SOCIAL presenta nulos: 2 registros (0.005% aprox.).
•	Las demás columnas no presentan nulos según la inspección inicial.
Interpretación:
•	La proporción de nulos es muy baja en RAZÓN SOCIAL. Esta es importante para reportes, verificaciones legales y presentación, por lo que conviene investigar esos 2 registros ya que podrían ser filas con NIT pero sin razón social.
Acción recomendada:
•	Revisar los 2 NIT con RAZÓN SOCIAL nula:
o	Si existe otro registro del mismo NIT con razón social en otro año rellenar la razón social correcta.
o	Si no existe intentar imputación mediante fuentes externas como registro tributario o marcar como missing y excluir de análisis que requieren nombre.
•	Mantener las filas si los demás campos están completos y el objetivo es un análisis cuantitativo, pero documentar la eliminación.
 
### 3) Inconsistencias en valores

Observaciones:
•	NIT: todos contienen caracteres no numéricos como comas(ejemplo: 899,999,068). Se deben normalizar (eliminar comas).
•	Año de Corte: valores con comas: 2,022, 2,021, etc. Deben convertirse a enteros 2022, 2021,....
•	CIIU: algunos códigos incluyen comas (ejemplo: 1,921) deben limpiarse a códigos numéricos sin separadores.
•	CIUDAD DOMICILIO: mezcla de formatos CIUDAD-DEPARTAMENTO (ejemplo: BOGOTÁ-BOGOTA D.C.), uso inconsistente de acentos y guiones y posible presencia de espacios adicionales.
•	MACROSECTOR / SUPERVISOR / DEPARTAMENTO: valores en mayúsculas y algunas abreviaturas; revisar consistencia (ejemplo: BOGOTA D.C. vs BOGOTÁ).
Interpretación:
•	Si no se normalizan, las agregaciones por ciudad/departamento o por CIIU estarán fragmentadas y darán resultados erróneos, por ejemplo, duplicación de categorías por pequeñas diferencias tipográficas.
Acción recomendada:
•	Normalizar:
o	NIT: quitar comas y convertir a int.
o	Año de Corte: quitar comas y convertir a int.
o	CIIU: quitar comas y ceros a la izquierda si es necesario para estandarizar longitud.
o	CIUDAD DOMICILIO y DEPARTAMENTO DOMICILIO: estandarizar por nombres iguales.
•	Estandarizar valores de MACROSECTOR y SUPERVISOR para evitar categorías duplicadas por sinónimos.

### 4) Tipos de datos

Observación:
•	Columnas financieras están en texto con símbolos $ y ,. También a Año de Corte, CIIU y NIT se les debe cambiar el formato.
Correcciones necesarias:
•	Convertir columnas financieras a float después de limpiar símbolo $, comas y espacios.
•	Convertir NIT a string sin separadores (o a entero pero mejor mantener como string para evitar pérdida de ceros) y usarlo como identificador.
•	Año de Corte: convertirlo a int.
•	CIIU: convertirlo a string.

 
### 5) Valores atípicos

Observaciones:
•	Las distribuciones de las variables financieras son extremadamente sesgadas (medianas muy bajas frente a máximos grandes: por ejemplo, Ingresos max ≈ 144.82 vs mediana ≈ 0.04).
•	Esto indica una cola larga: unas pocas empresas concentran gran parte del tamaño (esperado en datasets de “empresas más grandes”), lo que genera valores atípicos naturales.
•	GANANCIA (PÉRDIDA) tiene 1.733 valores negativos (pérdidas); TOTAL PATRIMONIO tiene 609 negativos (posible patrimonio negativo — alerta contable).
Interpretación:
•	Regresiones y medias se ven muy afectadas por estos valores atípicos; comparaciones por medias pueden ser engañosas.
•	Algunas observaciones negativas en patrimonio requieren verificación (errores de input o patrimonio contable negativo real).
Acción recomendada:
•	Antes de tratar estos valores atípicos, distinguir entre:
o	Valores reales por ejemplo Ecopetrol con ingresos muy altos — no eliminar, sino tratarlos con transformaciones (log, percentiles, regresiones robustas).
o	Errores de captura como valor absurdo o negativo en una columna que no debería ser negativa — corregir o remover si se confirma que es error.
•	Técnicas:
o	Usar transformación log(1+x) para análisis que requieran distribución menos sesgada.
o	Para análisis de medias, usar medianas o percentiles.
o	Revisar las empresas con valores negativos de patrimonio y pérdidas extremas: hacer verificación manual (top N empresas por magnitud).

### 6) Nivel de granularidad

Observación:
•	El dataset contiene al menos 4 años de corte (2021–2024); por tanto, el nivel de granularidad parece ser empresa × año.
•	No hay columnas de fecha más finas (mes, día), ni columnas temporales más detalladas.
Interpretación:
•	Si el análisis objetivo es comparaciones anuales o tendencias interanuales, la granularidad empresa–año es adecuada.
•	Si se necesita análisis mensual/trimestral NO hay granularidad suficiente; se tendría que integrar con otras fuentes o datos contables más desagregados.
Acción recomendada:
•	Decidir la unidad de análisis: empresa–año (recomendado si se quiere indicadores financieros anuales).
•	Si se necesitan datos agregados por región, departamento, CIIU por año entonces agrupar por Año de Corte, DEPARTAMENTO DOMICILIO, MACROSECTOR y usar medidas robustas como mediana y percentiles.

### Justificación general de por qué abordar cada aspecto

1.	Duplicados por NIT — si no se manejan correctamente como ignorando año, se pueden eliminar registros válidos de años distintos y perder información importante.
2.	Nulos en RAZÓN SOCIAL — aunque pocos, afectan reportes y la verificación entidad, deben resolverse por consistencia.
3.	Inconsistencias de formato (NIT, Año, CIIU, CIUDAD) — fragmentan categorías, generando agregaciones erróneas y conteos inflados.
4.	Tipos de datos incorrectos (texto en numéricos) — impiden cálculos, estadísticos y transformaciones; deben convertirse para obtener KPIs.
5.	Valores atípicos — afectan promedios, regresiones y modelos, se debe hacer un tratamiento estricto para evitar conclusiones sesgadas.
6.	Granularidad — definir unidad de análisis (empresa–año) evita interpretaciones incorrectas y orienta transformaciones (ejemplo: agregación o desagregación).
 
# II. Limpieza y Transformación de Datos

## 1. Eliminación de Duplicados

Revisa y elimina las filas duplicadas identificadas en el dataset. Esto ayudará a reducir sesgos y evitar resultados inflados en los análisis posteriores.
•	Usa el método drop_duplicates() de pandas y confirma que no queden duplicados en el dataset.

### Código

<img width="925" height="152" alt="image" src="https://github.com/user-attachments/assets/8a1b94d2-3858-4a82-98d2-301e5704b58c" />
 
### Resultado

Se aplicó correctamente el método drop_duplicates() sobre el dataset y se verificó el estado antes y después del proceso.

Resultados:
* Duplicados antes de limpiar: 0
* Duplicados después de limpiar: 0

Con esto podemos confirmar que no existen filas completamente duplicadas en el dataset, por lo tanto, no fue necesario eliminar registros, y la integridad de los datos se mantiene.
 
## 2. Tratamiento de Valores Nulos

Basado en la evaluación anterior de los valores nulos, implementa alguna de estrategias para manejar los datos faltantes según la relevancia de cada variable:

Imputación de datos numéricos críticos: Completa los valores nulos en columnas numéricas importantes (por ejemplo, con la media o mediana según la distribución).
Eliminación o imputación de variables categóricas con valores nulos: Usa la moda para variables categóricas o considera eliminar filas con valores nulos si el porcentaje es bajo y su eliminación no afecta los resultados.
Instrucción: Usa métodos como fillna() o dropna() según el caso.

### Código

<img width="925" height="384" alt="image" src="https://github.com/user-attachments/assets/b98d8610-a9d2-4094-a83a-695b32872d19" />

### Resultado

Se realizó la revisión y tratamiento de los valores nulos identificando los datos faltantes antes de aplicar las estrategias de limpieza.

Resultados:
* Valores nulos antes del tratamiento: 2
* Valores nulos después del tratamiento: 0

Los valores faltantes fueron corregidos mediante imputación, utilizando la moda para variables categóricas y la mediana para variables numéricas, según su relevancia. Con esto podemos confirmar que el dataset quedó libre de valores nulos, garantizando una mayor consistencia y confiabilidad para los análisis posteriores, sin comprometer la integridad de la información.
 
## 3. Ajuste de Tipos de Datos

Asegúrate de que cada columna tenga el tipo de dato adecuado según su contenido. Esto optimizará el manejo de memoria y mejorará la precisión de los análisis.

Revisa y convierte columnas que requieren un tipo específico, como convertir variables de fecha con pd.to_datetime() y valores categóricos a tipo category.

### Código

<img width="925" height="627" alt="image" src="https://github.com/user-attachments/assets/71842a47-3158-4ef9-af0a-9de16012b000" />

### Resultado

Se realizó la verificación y corrección de los tipos de datos del dataset, comparando su estado antes y después del ajuste.

Resultados:
* Tipos de datos antes del ajuste: Varias columnas se encontraban en formato object, incluyendo la columna Año de Corte, y las columnas financieras estaban almacenadas como texto con posibles símbolos monetarios y separadores, lo que impedía su correcto análisis numérico.
* Tipos de datos después del ajuste: La columna Año de Corte fue convertida correctamente a tipo datetime, las columnas financieras fueron limpiadas y transformadas a tipo numérico (float), eliminando caracteres no válidos, y las variables categóricas fueron optimizadas al tipo category.

Con estos cambios se logró una estructura de datos más adecuada y coherente, mejorando el rendimiento, la precisión de los cálculos y la confiabilidad de los análisis financieros, garantizando que el dataset esté listo para procesos estadísticos y visualizaciones sin errores.
 
## 4. Detección y Tratamiento de Valores Atípicos

Examina las variables numéricas para identificar valores atípicos que podrían distorsionar el análisis.
•	Utiliza boxplots para visualizar valores atípicos. Luego, evalúa si es adecuado eliminarlos o tratarlos con técnicas como el recorte (trimming) o winsorización.

### Código

<img width="925" height="305" alt="image" src="https://github.com/user-attachments/assets/a0c3694c-7e45-4214-9f07-d5c58c4970aa" />
<img width="925" height="550" alt="image" src="https://github.com/user-attachments/assets/64391f6c-851f-4e18-95ac-dc57a6fdcc06" />

### Resultado

•	El IQR marcó muchos valores como outliers porque el dataset es muy desigual pero es normal al tratarse de empresas grandes, medianas y pequeñas.
•	Estos valores NO deben eliminarse porque son reales y representan valores financieros de las empresas.
•	La distribución es fuertemente sesgada porque los valores altos reales son enormes comparados con la mayoría de empresas lo cual es normal en datos financieros.
•	Con este análisis decidimos que NO se debe aplicar trimming, winsorización ni log-transform, salvo para visualización. Esto se debe a que como ya se dijo representan valores reales de empresas.
 
## 5. Correcciones de Valores con replace, map y zip

Realiza correcciones en valores específicos en las columnas que contienen errores tipográficos o inconsistencias. Estas herramientas te permitirán reemplazar valores incorrectos de forma rápida y precisa.
•	Usa replace() para cambiar valores puntuales.
•	Usa map() para transformar columnas completas usando un diccionario de equivalencias.
•	Usa zip() si necesitas hacer ajustes combinados en varias columnas.
•	Por ejemplo, podrías usar un diccionario con map() para corregir nombres de ciudades o categorías.

### Código

<img width="925" height="646" alt="image" src="https://github.com/user-attachments/assets/2d4571b9-ede2-4fca-82ef-a1b199193b76" />

### Resultado

Se realizaron correcciones en valores de la columna CIUDAD DOMICILIO haciendo uso de map().

•	Se aplicó una función que estandariza la columna CIUDAD DOMICILIO (separando por “-”, limpiando espacios, normalizando mayúsculas y unificando el formato).
•	Se creó una columna de respaldo (CIUDAD_ORIGINAL) y luego se compararon valores únicos.
•	El resultado muestra que los valores únicos se redujeron, lo cual indica que muchas variaciones o inconsistencias fueron corregidas y ahora la columna está más homogénea y lista para análisis.
 
## 6. Agregación de Datos:

Realiza agregaciones en el conjunto de datos cuando su nivel de detalle sea mayor al necesario.
•	Usa groupby() para agrupar los datos según columnas clave que definan el nivel de agregación requerido.
•	Después de agrupar, aplica funciones de agregación como sum(), mean(), count() o median() según el análisis que desees realizar.
•	Por ejemplo, podrías agrupar por mes_pedido y Categoría para calcular el total de ventas por mes y categoría de producto.

### Código

<img width="925" height="977" alt="image" src="https://github.com/user-attachments/assets/c1ae4279-82a1-496b-b996-ad3d24f35313" />

### Resultado

El análisis muestra que capital, sector y patrimonio son los principales determinantes del desempeño financiero empresarial.

1.	Agregación por MACROSECTOR
•	Se agruparon las empresas por macrosector y se calcularon ingresos totales, ingresos promedio y cantidad de empresas.
•	Comercio y Servicios son los sectores con mayores ingresos totales; Minería tiene los ingresos promedio más altos por empresa.
 
2.	Rentabilidad en Antioquia y Bogotá
•	Se filtraron solo estas dos regiones y se calculó la rentabilidad promedio y número de empresas.
•	Antioquia presenta rentabilidad promedio positiva; Bogotá aparece sin datos válidos de ganancia en este dataset.

3.	Clasificación por tamaño (según patrimonio)
•	Se dividieron las empresas en Pequeña, Mediana y Grande usando percentiles del patrimonio total.
•	Se generaron tres grupos equilibrados según distribución real del patrimonio.

4.	Relación entre tamaño y rentabilidad
•	Se calculó la ganancia promedio, patrimonio promedio y número de empresas por cada categoría de tamaño.
•	Las empresas pequeñas tienen rentabilidad negativa; las medianas rentabilidad moderada; las grandes rentabilidad muy superior.

5.	Gráfico comparativo de rentabilidad
1.	Se creó un gráfico de barras mostrando la rentabilidad promedio por tamaño.
2.	El gráfico evidencia un aumento claro de rentabilidad a medida que crece el tamaño de la empresa.
 
# III. Validación

## 1.	Revisión de los objetivos de análisis definidos al inicio del proyecto

El objetivo principal definido es:

“Analizar la relación entre el tamaño, la rentabilidad y la ubicación geográfica de las empresas más grandes de Colombia, identificando patrones que contribuyan a la toma de decisiones estratégicas en el ámbito empresarial.”

El objetivo del análisis se mantiene intacto después del proceso de limpieza, ya que el dataset conserva toda la información necesaria sobre tamaño (patrimonio), rentabilidad (ganancia) y ubicación geográfica (región y ciudad), así se puede estudiar las relaciones entre estas variables sin pérdida de detalle o datos relevantes.

Coherencia con el objetivo
•	El objetivo busca entender cómo se relacionan el tamaño, la rentabilidad y la ubicación geográfica de las empresas.
•	Las tres dimensiones siguen presentes y utilizables en el dataset limpio.

Variables necesarias presentes
•	Tamaño - TOTAL PATRIMONIO
•	Rentabilidad - GANANCIA (PÉRDIDA)
•	Ubicación geográfica - REGIÓN, DEPARTAMENTO DOMICILIO, CIUDAD DOMICILIO
Todas estas columnas quedaron limpias, estandarizadas y sin valores nulos críticos.

Adecuación del dataset al objetivo
•	Las medidas financieras quedaron numéricas y comparables.
•	Las categorías geográficas fueron unificadas y así se evitan duplicaciones.
•	Con la estructura empresa–año se puede analizar patrones por región y por tamaño.

## 2.	Verificar si el dataset limpio contiene la información necesaria para abordar la pregunta.

La pregunta de investigación definida es:

¿Cómo varía la rentabilidad de las empresas más grandes de Colombia según su tamaño y ubicación geográfica?

Después del proceso de limpieza y transformación, el dataset conserva toda la información necesaria para responder la pregunta de investigación, ya que las columnas críticas quedaron completas y sin nulos, las variables relevantes se mantienen en formato correcto, y la granularidad empresa–año proporciona el nivel de detalle adecuado para analizar cómo varía la rentabilidad según el tamaño y la ubicación geográfica.

Completitud de los datos
•	Las columnas esenciales para la pregunta de investigación —GANANCIA (PÉRDIDA) (rentabilidad), TOTAL PATRIMONIO (tamaño), REGIÓN / CIUDAD / DEPARTAMENTO (ubicación)— quedaron sin valores nulos.
•	El proceso de limpieza no eliminó registros críticos; el número de filas permanece adecuado para el análisis.
•	Las agregaciones con groupby() no generaron pérdida de información, antes se usaron para obtener indicadores pero no para eliminar datos originales.

 
Relevancia de las variables
•	Rentabilidad: La columna GANANCIA (PÉRDIDA) fue limpiada y convertida a numérica, permitiendo análisis confiables.
•	Tamaño: TOTAL PATRIMONIO está correctamente organizado y permite clasificar empresas en pequeña, mediana, grande.
•	Ubicación geográfica: Las columnas REGIÓN, CIUDAD DOMICILIO, DEPARTAMENTO DOMICILIO fueron estandarizadas, evitando fragmentación por inconsistencias de texto.
•	Variables complementarias: MACROSECTOR, CIIU y Año de Corte permanecen disponibles para análisis adicionales.

Granularidad adecuada
•	El dataset tiene granularidad empresa-año y apenas es para comparar empresas según tamaño, rentabilidad y ubicación.
•	No es necesaria granularidad menor como mes o día ya que la pregunta se centra en rentabilidad general por tamaño y región.
•	La granularidad es consistente, homogénea y apropiada para detectar patrones entre grupos.

