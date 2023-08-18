![HenryLogo](https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png)

# **Proyecto Integrador**

## **Introducción**

¡Bienvenidos a nuestro proyecto integrador! Durante estos días estarán poniendo en práctica sus habilidades en el campo del aprendizaje automático. Deberán entender la problemática y comprender los datos, realizar el análisis exploratorio de datos, preparar los datos, para luego experimentar con los modelos de machine learning en un contexto real. Finalmente, usarán las métricas correspondientes para medir el performance de los modelos y seleccionar el mejor. 

Vale la pena destacar, que puede realizarse por equipos y que este proyecto no será revisado. El objetivo es poner en práctica los conceptos que se van adelantando en el M6, previo a la etapa de Labs que están por comenzar. Por tanto, es un proyecto que podrán tener un su portafolio personal, pero no tiene calificación cuantitativa. 

Este proyecto constará de tres fases: `Análisis exploratorio de datos`, `Preparación de datos` y `Modelamiento y evaluación`.


### 1. Análisis exploratorio de datos

Machine Learning en Medicina: Al aplicar Machine Learning en Medicina se pueden usar las herramientas informáticas, con el fin de conseguir información a partir de los datos, por ejemplo, de historias clínicas o registros de prestadores de servicios de salud. De esta manera, se pueden emitir diagnósticos predicitivos, evaluar la efectividad de estrategias de intervención y anticipar comportamientos en escenarios relacionados con la atención. 

## **Planteamiento de la problemática**

Hemos sido contratados en el equipo de ciencia de datos en una consultora de renombre. Nos han asignado a un proyecto de estudio de atención en salud para un importante hospital. **Nuestro cliente desea saber las características más importantes que tienen los pacientes de cierto tipo de enfermedad que terminan en hospitalización.** Fue definido como caso aquel paciente que fue sometido a biopsia prostática y que en un periodo máximo de 30 días posteriores al procedimiento presentó fiebre, infección urinaria o sepsis; requiriendo manejo médico ambulatorio u hospitalizado para la resolución de la complicación y como control al paciente que fue sometido a biopsia prostática y que no presentó complicaciones infecciosas en el período de 30 días posteriores al procedimiento. Dado que tienen en su base de datos algunos datos referentes a los pacientes y resultados de exámenes diagnósticos, de pacientes hospitalizados y no hospitalizados, nos han entregado esta información.  

Para ello, nuestro departamento de datos ha recopilado `Antecedentes del paciente`, `Morbilidad asociada al paciente` y `Antecedentes relacionados con la toma de la biopsia`y `Complicaciones infecciosas`. En la siguiente tabla, se encuentra un diccionario de datos asociado:

![image](https://user-images.githubusercontent.com/118769777/220240501-8c21461d-2de5-495b-954e-10fb9bf38014.png)

El departamente de datos advierte que hay algunos problemas de calidad de datos en la información suministrada por lo que el primer reto del equipo es realizar un análisis exploratorio de los datos con el fin de transformar y preparar las datos adecuadamente. 


## **Formato de entrega**

Deben tener el código en un script .py o Jupyter Notebook .ipynb. Es muy importante explicar claramente cada paso realizado mediante comentarios en el script o textos formato markdown dentro del Notebook, pensar que cualquier persona debe entender de la mejor manera posible cada razonamiento y pasos aplicados.

Recuerden, además, que deben crear el repositorio que contenga el proyecto, por lo que es importante que le dediquen tiempo también a esta parte, dejando todo ordenado y con un README acorde, que sirva de introducción al contenido dentro de este. Recuerden que nuestro cliente desea saber las características más importantes que tienen los pacientes de cierto tipo de enfermedad que terminan en hospitalización y crear un modelo predictivo de clasificación para la variable objetivo: Hospitalización.
