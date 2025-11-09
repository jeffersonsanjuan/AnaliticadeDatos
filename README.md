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

![Duplicados](https://trello.com/1/cards/690c2c386cde4d38d46b5880/attachments/69102221e98ea47cced623e3/download/image.png)

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
