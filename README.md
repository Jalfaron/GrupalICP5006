# GrupalICP5006
# Paridad de género en las elecciones parlamentarias

_Grupo: Javiera Alfaro, Bernardino Araya, Osvaldo Malfanti, Sara Vidal_

# Introducción al tema de nuestro proyecto: PARIDAD
Este proyecto realiza un análisis transversal de los resultados electorales en Chile en las elecciones Parlamentarias del 2021, enfocándose en las diferencias de género de las candidaturas y de las afiliaciones al partido político.

# Objetivo
El objetivo es investigar la distribución de género por partido político con respecto a la proporción de género de sus afiliadas y afiliados. 

# Marco teórico
_Desde 2017, las candidaturas parlamentarias han estado reguladas por una cuota de género, que impide que ningún género supere el 60% de participación en la inscripción total de postulaciones al Congreso Nacional. Esta medida, establecida para las elecciones de 2017, 2021, 2025 y 2029, ha asegurado que al menos un 40% de las listas esté compuesto por mujeres_

_Sin embargo, la ley de cuotas no garantiza escaños, solo postulaciones. La distribución de los cupos, la competitividad dentro de los partidos y la cultura política siguen siendo factores que influyen en el acceso de las mujeres al poder legislativo_. Nodo Electoral, 2025.

# Fuentes de Datos
Para el desarrollo de este proyecto se priorizarás las siguientes fuentes de información:
1. Cantidad de militantes de cada partido político:
   _SERVEL, Estadísticas de afiliados de cada partido político desglosadas por sexo, tramos de edad y región, al 30 de septiembre de 2025._

2. Lista de candidaturas parlamentarias:
  _TRICEL, Sentencia de proclamación y calificación de elección de Diputadas y Diputados en el año 2021._
  _TRICEL, Sentencia de proclamación y calificación de elección de Senadoras y Senadores en el año 2021._

3. Lista de parlamentarias electas y electos de cada partido político:
  _SERVEL, Resultados Electorales de Diputadas y Diputados en el año 2021.
  SERVEL, Resultados Electorales de Senadoras y Senadores en el año 2021._

# Estructura del proyecto
El proyecto estará dividido en tres etapas que estarán contenidas:

  1. Transformación y limpieza de bases de datos: _En esta primera etapa se busca preparar los datos para el análisis, garantizando consistencia y coherencia en formatos y en los tipos de elecciones (de diputados y de senadores). Dado que las fuentes oficiales —como el Servel y TRICEL— pueden tener estructuras diferentes, aquí se aplican técnicas de procesamiento de datos en R para depurar y unificar la información._
     
  2. Análisis y modelamiento de los datos: _En esta etapa se realiza el análisis transversal de patrones electorales en función del género de las candidaturas y de las personas afiliadas. Aquí se extraen estadísticas descriptivas y se identifican relaciones relevantes entre las variables._
     
  3. Visualización y comunicación de resultados: _En esta fase se presentan los resultados finales del análisis mediante gráficos, mapas y dashboards que faciliten la interpretación de tendencias y comparaciones entre partidos políticos._


# Plan de Análisis 
## 1. Definición del Problema y Preguntas de Investigación
¿Existe coherencia entre la proporción de militantes mujeres en los partidos y la proporción de candidatas presentadas?
¿Qué partidos presentan mayor o menor paridad en sus candidaturas?
¿La cuota de género ha tenido impacto en los resultados electorales (es decir, en la cantidad de mujeres electas)?
¿Hay diferencias entre elecciones de diputados y senadores en cuanto a paridad?

## 2. Preparación de Datos
_a. Fuentes_
SERVEL: Militancia por sexo, edad, región.
SERVEL: Resultados electorales y candidaturas oficiales por género y partido.

_b. Procesos_
Unificación de formatos (nombres de partidos, regiones).
Normalización de variables (género, tipo de elección, etc.).
Creación de variables derivadas.

_c. Definición de variables_
Variable independiente: Género de las personas militantes de los partidos políticos (mujer, hombre, no binario)
Variable dependiente: Género de candidatas y candidatos en las listas electorales de los partidos políticos (mujer, hombre, no binario)
Variables de control: Partido político al que pertenecen candidatos y militantes, nivel al que se postulan (senadores, diputados) y año o período electoral

## 3. Análisis Descriptivo
_a. Distribución de Militancia_
Por partido político.
Por género.
Por región y edad (a revisar si es relevante).

_b. Distribución de Candidaturas_
Por partido y género.
Comparación con militancia (¿los partidos postulan proporcionalmente a sus militantes mujeres?).

_c. Resultados Electorales_
Por género y partido.
Tasa de éxito por género (candidatas electas / candidatas totales).

## 4. Análisis Comparativo y Modelamiento
_a. Indicadores Clave_
Índice de paridad por partido: Paridad=Candidatas mujeresTotal de candidaturas\text{Paridad} = \frac{\text{Candidatas mujeres}}{\text{Total de candidaturas}}Paridad=Total de candidaturasCandidatas mujeres​
Índice de representación efectiva: Representacioˊn=Electas mujeresTotal electos\text{Representación} = \frac{\text{Electas mujeres}}{\text{Total electos}}Representacioˊn=Total electosElectas mujeres​

_b. Modelos Estadísticos (opcional)_
Regresiones logísticas para ver si el género influye en la probabilidad de ser electo/a.
Análisis de correlación entre proporción de militantes mujeres y candidatas mujeres.

## 5. Visualización de Resultados
Gráficos de barras comparativos por partido.
Mapas de calor por región.
Dashboards interactivos (si usas Shiny en R, por ejemplo).

## 6. Conclusiones y Recomendaciones
¿Qué partidos tienen mayor coherencia entre militancia y candidaturas?
¿La cuota de género está logrando su objetivo?
¿Qué barreras persisten para la representación femenina?

## 7. Proyecciones
Comparar con elecciones de 2017 y proyectar hacia 2025.
Incluir variables como edad, región o trayectoria política.


_Este proyecto es realizado en el marco del curso ICP5006 "Medición y análisis dimensional de datos políticos"._
