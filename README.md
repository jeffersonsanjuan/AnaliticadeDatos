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
