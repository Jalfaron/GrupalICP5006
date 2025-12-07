GrupalICP5006 2025
# 🗳️🙋🏽‍♀️ Paridad de género en las elecciones parlamentarias
_Grupo: Javiera Alfaro, Bernardino Araya, Osvaldo Malfanti, Sara Vidal_

---

## 🔍 ¿Qué incluye este repositorio?

- 🧹 **Preprocesamiento de bases de datos**: Limpieza y etiquetado de base de datos por partidos políticos.
- Bases originales:
1. 2021_11_Diputados_Datos_Eleccion.xlsx
2. 2021_11_Senadores_Datos_Eleccion.xlsx
3. Candidaturas_2021
4. Estadistica por Rango Etario (2021 y 2025).xlsx
- Bases limpias:
1. base_diputados.rds
2. base_senadores.rds
3. candidatos_diputados_sexo.rds
4. candidatos_senador_sexo.rds
- 📋 **Análisis y creación de gráficos**: Análisis de los resultados electorales a través de proporciones
- Scripts de trabajo
1. 00-diputados.Rmd
2. 00-senadores.Rmd
3. 01-add_sexo_candidatos.Rmd
4. 02-militantes.Rmd
5. 03-graficos.Rmd
- 📊 **Visualizaciones**:
1. Proporción de militantes por partidos
2. Candidatas a diputadas por partidos
3. Candidatas a senadoras por partidos
4. Cantidad de mujeres electas como diputadas por partidos
5. Cantidad de mujeres electas como senadoras por partidos
6. Embudo de Participación y Representación por Partido en Barras
7. Embudo Promedio de Participación Femenina
8. Embudo de Participación Femenina por Cámara

---

# Introducción al tema de nuestro proyecto: PARIDAD
Este proyecto realiza un análisis transversal de los resultados electorales en Chile en las elecciones Parlamentarias del 2021, enfocándose en las diferencias de género de las candidaturas y de las afiliaciones al partido político.

# Objetivo
El objetivo es investigar la distribución de género por partido político con respecto a la proporción de género de sus afiliadas y afiliados. 
Nuestra pregunta guía: ¿Cuál es la distribución de género en las elecciones parlamentarias de 2021 en relación a la proporción de género de las personas afiliadas en los partidos políticos?

---

# Marco teórico
Según Naciones Unidas (2025), con el nivel de avance actual, la paridad de género en los cuerpos legislativos nacionales no se logrará antes de 2063. Por lo tanto hay un desafío global relacionado a la partidad, ya que solo el 27,2% de los escaños parlamentarios nacionales están ocupados por mujeres. 

Desde 2017, las candidaturas parlamentarias han estado reguladas por una cuota de género, que impide que ningún género supere el 60% de participación en la inscripción total de postulaciones al Congreso Nacional. Esta medida, establecida para las elecciones de 2017, 2021, 2025 y 2029, ha asegurado que al menos un 40% de las listas esté compuesto por mujeres. Sin embargo, la ley de cuotas no garantiza escaños, solo postulaciones. La distribución de los cupos, la competitividad dentro de los partidos y la cultura política siguen siendo factores que influyen en el acceso de las mujeres al poder legislativo (Nodo Electoral, 2025). Con las elecciones parlamentarias de 2025 en el horizonte, la duda es si la representación femenina seguirá creciendo y si el aumento de candidatas se traducirá en más mujeres electas, consolidando una presencia equitativa en el Congreso.

Tal como menciona Lefoulon (2025), Chile tuvo los órganos constituyentes más paritarios conocidos hasta el momento. Para la elección de la Cámara de 2017, sí encontraron brechas de género a favor de los hombres en todos los aportes, incluidos los aportes de partido.

Además, según el Ministerio de la Mujer y la Equidad de Género en Chile (2025) hay motivos estructurales porque las mujeres se postulan menos que los hombres a las candidaturas, uno de ellos es la violencia que reciben por redes sociales y su participación requiere mayor apoyo de los partidos y compromiso a nivel país, como relevar la paridad.

En consideración a estos antecedentes realizamos nuestro estudio.

---

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

---

# Estructura del proyecto
El proyecto estará dividido en tres etapas que estarán contenidas:

  1. Transformación y limpieza de bases de datos: _En esta primera etapa se busca preparar los datos para el análisis, garantizando consistencia y coherencia en formatos y en los tipos de elecciones (de diputados y de senadores). Dado que las fuentes oficiales —como el Servel y TRICEL— pueden tener estructuras diferentes, aquí se aplican técnicas de procesamiento de datos en R para depurar y unificar la información._
     
  2. Análisis y modelamiento de los datos: _En esta etapa se realiza el análisis transversal de patrones electorales en función del género de las candidaturas y de las personas afiliadas. Aquí se extraen estadísticas descriptivas y se identifican relaciones relevantes entre las variables._
     
  3. Visualización y comunicación de resultados: _En esta fase se presentan los resultados finales del análisis mediante gráficos, mapas y dashboards que faciliten la interpretación de tendencias y comparaciones entre partidos políticos._   

---

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
Índice de paridad por partido: Paridad = Candidatas mujeres / Cantidad militantes
Índice de representación efectiva: Representación = Electas mujeres / Cantidad candidatas

## 5. Visualización de Resultados
1. **Proporción de militantes por partidos**
Aunque la mayoría de los partidos supera el 45% de militantes mujeres, hay una gran variabilidad: algunos alcanzan casi 60%, mientras otros no superan el 30%. Sin embargo, en la mayoría de los casos es una representación muy real de como es la división demográfica de la población.
Los partidos de izquierda tienden a tener porcentajes altos de militantes mujeres (muchos sobre el 50%), mientras que en la derecha hay casos que bajan al 40% o menos. Esto sugiere una base femenina más fuerte en partidos progresistas.
<img width="1736" height="824" alt="Mujeres Militantes por Partido" src="https://github.com/user-attachments/assets/c237683c-f275-437b-8501-5411daeb6048" />

3. **Candidatas a diputadas por partidos**
Varios partidos logran paridad o incluso la superan, pero otros se quedan cerca del 40%. Esto muestra que la oferta electoral femenina depende fuertemente de la voluntad partidaria más que de la disponibilidad de militantes.
Partidos de izquierda como COMUNES y REVOLUCIÓN DEMOCRÁTICA lideran con más del 60%, superando la paridad. En contraste, partidos de derecha como UDI y Republicano se ubican cerca del 40%, mostrando menor compromiso en la postulación femenina.
<img width="1736" height="824" alt="Candidatas a Diputadas por partido" src="https://github.com/user-attachments/assets/66fb40d7-42ba-417d-b24f-554b95f14919" />

5. **Candidatas a senadoras por partidos**
La mayoría de los partidos presenta proporciones cercanas al 50%, lo que refleja cumplimiento formal de paridad en listas senatoriales, lo que se puede explicar por la Ley de Cuotas. Sin embargo, algunos partidos bajan a 33%, evidenciando brechas en cargos de mayor jerarquía.
Aunque la mayoría cumple con paridad formal (50%), partidos de izquierda mantienen consistencia, mientras que en la derecha aparecen valores más bajos (33%-40%), lo que indica brechas en cargos de mayor jerarquía.
<img width="1736" height="824" alt="Candidatas a Senadoras por partido" src="https://github.com/user-attachments/assets/a367983f-7f5e-4828-88e6-bbdf667f311e" />

7. **Cantidad de mujeres electas como diputadas por partidos**
La representación efectiva es muy desigual: algunos partidos alcanzan 100% o más del 80%, mientras otros no logran elegir ninguna mujer. Esto revela que la paridad en candidaturas no siempre se traduce en paridad en resultados.
La diferencia se amplía: partidos de izquierda logran porcentajes altos (COMUNES 83%, Comunista 75%), mientras que varios partidos de derecha no eligen ninguna mujer. Esto evidencia que la competitividad electoral favorece más a mujeres en bloques progresistas.
<img width="1736" height="824" alt="Diputadas Electas por Partido" src="https://github.com/user-attachments/assets/cd164a6d-d243-44c2-8fc4-f380139e55e3" />

9. **Cantidad de mujeres electas como senadoras por partidos**
Solo cuatro partidos logran elegir mujeres (40%-50%), mientras la mayoría queda en 0%. Esto confirma que el Senado es más restrictivo para la representación femenina, incluso con paridad en candidaturas.
Predominan partidos de centro-izquierda (Por la Democracia, Comunista). En la derecha, la mayoría queda en 0%, confirmando que los espacios de poder siguen siendo más restrictivos para mujeres en esos sectores.
<img width="1736" height="824" alt="Senadoras Electas por Partido" src="https://github.com/user-attachments/assets/d3c6e9af-75e7-46e2-90f2-31dab7856efa" />

11. **Embudo de Participación y Representación por Partido en Barras**
El embudo muestra caídas significativas entre militantes y electas, especialmente en el Senado. Algunos partidos con alta militancia femenina no logran convertir esa base en representación, lo que evidencia barreras internas y competitivas.
El embudo confirma que los partidos de izquierda no solo parten con una base femenina sólida, sino que también logran mejores tasas de conversión hacia candidaturas y electas, especialmente en la Cámara de Diputadas. En contraste, los partidos de derecha muestran caídas más pronunciadas y, en muchos casos, no alcanzan representación femenina en el Senado, lo que evidencia brechas ideológicas en la distribución del poder político.
<img width="1736" height="824" alt="Embudo de Participación y Representación por Partido en Barras" src="https://github.com/user-attachments/assets/2cc4d6b2-ce88-4db7-bfb6-7fcb43f41afc" />

13. **Embudo Promedio de Participación Femenina**
La Cámara de Diputadas presenta mejor conversión que el Senado, pero en ambos casos la caída entre candidatas y electas es marcada. Esto sugiere que las reglas de paridad son más efectivas en distritos proporcionales que en circunscripciones pequeñas.
<img width="1736" height="824" alt="Embudo Promedio de Participación Femenina" src="https://github.com/user-attachments/assets/60c6b7f8-6b6d-46fa-b1ed-455e371ff77c" />

15. **Embudo de Participación Femenina por Cámara**
En promedio, solo el 47.6% de las candidaturas son femeninas, y la conversión a electas es del 32.6% en Diputadas y 21.1% en Senadoras. Esto refleja que la paridad en listas no garantiza paridad en resultados, especialmente en cargos de mayor poder.
<img width="1736" height="824" alt="Embudo de Participación Femenina por Cámara" src="https://github.com/user-attachments/assets/7bc0ccf1-b5d0-4289-8244-4436482ff831" />


---

# 6. Conclusiones
¿Qué partidos tienen mayor coherencia entre militancia y candidaturas?
¿La cuota de género está logrando su objetivo?
¿Qué barreras persisten para la representación femenina?

## a. El Fenómeno del "Embudo" (La Base es Femenina, la Cúpula es Masculina)
Según el gráfico de Militantes, la participación femenina es altísima. En casi todos los partidos (salvo Republicanos y Evópoli), las mujeres son más del 50% de la base (se puede ver en el de Ecologista Verde o el PRO).
En cuanto a Candidatas la proporción baja un poco, pero se mantiene fuerte (cercana al 40-50%) debido a la Ley de Cuotas.
En las candidatas electas está el problema. En los gráficos de Electas (especialmente Diputadas), las barras se desploman para los partidos tradicionales.

Las mujeres son la fuerza base de los partidos, pero a medida que se sube en la jerarquía de poder (de militante -> candidata -> electa), los hombres ocupan más espacio.

## b. La Ley de Cuotas funciona en el "Papel" pero no en el "Resultado"
Al mirar los gráficos de Candidatas (Senadoras y Diputadas), ves que casi ningún partido baja del 40%. Esto es porque la ley los obliga a llevar al menos un 40% de candidatas. Sin embargo, al mirar los gráficos de Electas, muchos partidos caen drásticamente (mira la UDI o RN en diputadas, que bajan al ~20-25%).

Los partidos cumplen con llevar mujeres, pero probablemente las ponen en distritos donde saben que van a perder, o les dan menos financiamiento/visibilidad que a los hombres. Cumplen la cuota, pero no aseguran la elegibilidad.

## c. La Brecha Ideológica (Izquierda vs. Derecha)
Existe una diferencia visible en la efectividad de elección entre bloques políticos en la Cámara de Diputados:

Partidos de Izquierda/Centro-Izquierda: (PC, Comunes, Convergencia Social, RD) tienden a tener una consistencia mayor entre candidatas y electas. De hecho, el PC y Comunes tienen porcentajes de diputadas electas muy altos (sobre el 60%), superando incluso su base de militantes.

Partidos de Derecha: (UDI, RN, Republicanos, Evópoli) aunque tienen una base de militantes y candidatas aceptable, su porcentaje de mujeres electas como diputadas es notoriamente más bajo (rondando el 15-25%).

## d. El Senado es una barrera más difícil (Muchos ceros)
El gráfico de Senadoras Electas muestra muchas barras vacías o muy bajas (Evópoli, PPD, Radicales, DC, Comunes, RD aparecen con 0% o muy bajo). 
A diferencia de la Cámara de Diputados, el Senado renueva menos cupos y las campañas son más caras y difíciles. Esto confirma que los espacios de "alto poder" siguen siendo más difíciles de acceder para las mujeres en comparación con la Cámara de Diputados.

**En general, Nuestros datos demuestran que no hay falta de interés político de las mujeres (son la mayoría en la militancia), sino que existen barreras estructurales dentro de los partidos que impiden que esa gran base militante se transforme en autoridades electas, especialmente en los partidos de derecha y en la elección senatorial.**

--- 

## 7. Proyecciones
Comparar con elecciones de 2017 y proyectar hacia 2025.
Incluir variables como edad, región o trayectoria política.

---
_Este proyecto es realizado en el marco del curso ICP5006 "Medición y análisis dimensional de datos políticos"._
