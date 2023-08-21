# **Machine Learning en Medicina**

## **Introducción**


**Un Hospital desea saber las características más importantes que tienen los pacientes de cierto tipo de enfermedad que terminan en hospitalización.**

- Caso de estudio:

Fue definido como 'caso' aquel paciente que fue sometido a biopsia prostática y que en un periodo máximo de 30 días posteriores al procedimiento presentó fiebre, infección urinaria o sepsis, requiriendo manejo médico ambulatorio u hospitalizado para la resolución de la complicación; y fue definido como 'control' aquel paciente que fue sometido a biopsia prostática y que no presentó complicaciones infecciosas en el período de 30 días posteriores al procedimiento.

Nuestro departamento de datos ha recopilado:
- `Antecedentes del paciente`
- `Morbilidad asociada al paciente`
- `Antecedentes relacionados con la toma de la biopsia`
- `Complicaciones infecciosas`

y ha creado una tabla (Hospital_BBDD.xlsx) que nos servirá de Base de Datos para el siguiente estudio.


## **Objetivos**

- Nos proponemos brindar al hospital un modelo que pueda predecir en base a datos del paciente, si este tendrá complicaciones infecciosas o no luego de ser sometido a biopsia prostática.

- Nos proponemos determinar y comunicar cómo influyen las distintas características del paciente en la variable objetivo 'complicación infecciosa'.

- Para un futuro nos proponemos brindar al hospital un modelo interactivo que le permita cargar distintos datos asociados a pacientes y obtener un resultado que indique si presentará o no complicación infecciosa luego de un procedimiento de biopsia prostática.


## **Aclaraciones importantes**

- Al hospital le interesa predecir en base a los datos del paciente, qué ocurrirá con este luego del procedimiento. Es decir, si presentará complicaciones infecciosas y por ende tendrá que ser hospitalizado/atendido de manera ambulatoria o no.


## **Análisis de los datos**

Luego de una primera visualización podemos decir:

- De 568 procedimientos registrados, consta que únicamente 24 requirieron hospitalización.

- De 568 procedimientos registrados, consta que únicamente 26 pacientes presentaron complicaciones infecciosas luego del procedimiento. De estos 26, 24 las presentaron durante la primera semana y se requirió hospitalización, los otros 2 presentaron complicaciones después de la primera semana.

- De los 544 casos que no requirieron hospitalización tenemos:
a) 2 casos que presentaron complicaciones luego de la primera semana y se decidió atención ambulatoria sin hospitalización.
b) 3 casos sin información sobre su hospitalización.
c) 539 casos que consta que no presentaron complicaciones y no requirieron hospitalización.

Conclusión: La correlación entre los casos de hospitalización y la ocurrencia de complicaciones infecciosas en la primera semana, es del 100%. La correlación entre los casos de hospitalización y la ocurrencia de complicaciones infecciosas en los 30 días posteriores al procedimiento es del 96%.

Sabemos entonces que un modelo que prediga con la mayor certeza posible si el paciente requerirá hospitalización luego del procedimiento tendrá que tener como variable objetivo la hospitalización, y un buen modelo predictivo que nos informe si el paciente presentará infecciones y entonces requerirá u hospitalización o atención ambulatoria, deberá tener como variable objetivo los datos referidos a complicaciones infecciosas post biopsia.


## **Arquitectura del proyecto**

1) En el primer archivo EDA_Hospital.ipynb se puede observar el detalle del Análisis Exploratorio de Datos, que consiste en renombrar columnas, contabilizar y visualizar registros totales, registros nulos, valores únicos y tipo de dato de cada columna. Además, se hace una primera limpieza que busca corregir los notorios errores de tipeo encontrados.

2) En el segundo archivo PREP_Hospital.ipynb se puede observar la preparación de los datos, que incluye la imputación y/o anulación de valores nulos y outliers, con la respectiva consideración y fundamentación de cada acción llevada a cabo. También el preprocesamiento de datos, preparándolos para el modelado

3) En el tercer archivo MOD_Hospital.ipynb se puede observar los procedimientos de Machine Learning utilizados, la evaluación de los mejores modelos predictivos, la evaluación de las distintas disposiciones de datos que mejor se adaptan a los modelos y a las necesidades del hospital.

4) En el cuarto archivo VIS_Hospital.ipynb se pueden cargar los datos, hacer estimaciones estadísticas, visualizaciones que ayudan a entender las predicciones y las conclusiones, y entender las características más importantes que llevan a un paciente a presentar complicaciones infecciosas luego del procedimiento.

5) En los archivos:

- Hospital_BBDD.xlsx se encuentra la base de datos recibida por el equipo.

- Hospital_EDA.xlsx se encuentra la base de datos ya analizada, limpia, y lista para su preprocesamiento

- Hospital_PREP.csv se encuentra la base de datos preprocesada y lista para trabajar en distintos modelos de 
Machine Learning. Las variables categóricas del conjunto X en este caso fueron trabajadas bajo un enfoque binario, desarrollado y explicado en el archivo ipynb correspondiente. Las variables numéricas no fueron normalizadas, porque eso se hará en el proceso de modelado, para evaluar distinas métricas según distintos criterios de normalización. 

- Hospital_PREP_multi.csv se encuentra la base de datos preprocesada y lista para trabajar en distintos modelos de Machine Learning. Las variables categóricas de marcada naturaleza binaria fueron trabajadas de manera binaria, y aquellas de posible categoría multiple fueron trabajadas con un enfoque de categorías múltiples con dummies.

- Hospital_MOD.csv en encuentra la base de datos preparada de manera más óptima (binaria, balanceada, con eliminación de nulos) para utilizar en el modelo de árbol más óptimo encontrado.



NOTA: Luego de evaluar los distintos modelos con sus distintas posibilidades de hiperparámetros, se llega a la conlusión que la mejor disposición de datos para entrenar los modelos es aquella cuyas variables categóricas fueron tratadas con un enfoque binario, y cuyas variables numéricas no se han normalizado.


## **Conclusiones generales**

De acuerdo a lo observado en el modelo predictivo, podemos afirmar que las tres características que más influyen en la presentación o no de complicaciones infecciosas luego de un procedimiento de biopsia prostática son **el valor de PSA, la EDAD, y la cantidad de MUESTRAS TOMADAS**, siendo determinantes en estas proporciones:

- PSA: 46,9% (Los pacientes con PSA más alto son más propensos a complicaciones infecciosas post biopsia)
- EDAD: 31,8% (Los pacientes de mayor EDAD son más propensos a complicaciones infecciosas post biopsia)
- MUESTRAS TOMADAS: 10,3% (Los pacientes a quienes se le tomaron más muestras son más propensos a complicaciones infecciosas post biopsia).

Luego, el paciente que haya tenido detección de enfermedad en la biopsia tendrá más propensión a complicaciones infecciosas post biopsia; esta variable incide en tan solo un 6,8%.

Las variables como existencia de biopsias previas incide en 2,3%; volumen porstático y EPOC tienen una incidencia en la variable objetivo menor al 1%

Las demás variables (cup, hospitalización en el último mes, diabetes) tienen incidencia 0.

NOTA: Estamos en condiciones de desarrollar un modelo interactivo que permite cargar las características de pacientes ficticios y obtener una predicción del 99,9% sobre la posibilidad de presentar complicaciones infecciosas luego de un procedimiento de biopsia prostática.