TALLER 2 - APRENDIZAJE PROFUNDO POR REFUERZO: DOUBLE DQN EN PONG
Aprendizaje Profundo - Maestria en Inteligencia Artificial
Pontificia Universidad Javeriana - Periodo 2026-30

INTEGRANTES
-----------
- Daniel Sebastian Velasco Munar (trabajo individual)


ENTREGABLES
-----------
1. informe/
   Reporte escrito en formato IEEE Transactions on Artificial Intelligence
   (PDF y fuente LaTeX). Responde las cinco actividades del taller:
   ciclo de entrenamiento, exploracion epsilon-greedy, analisis de valores Q
   y error TD, revision de la arquitectura y evaluacion de la politica.

2. Taller_2_Aprendizaje_profundo__202630.ipynb
   Codigo fuente en un notebook de Jupyter/Colab (TensorFlow/Keras), con las
   salidas de la ejecucion. Contiene:
   - Secciones 1 a 5: material base del taller (entorno, agente heuristico,
     preprocesamiento, red y agente iniciales).
   - Seccion 6.1: configuracion e hiperparametros.
   - Seccion 6.2: revision del codigo entregado, replay buffer, red Dueling
     y agente Double DQN con registro de metricas.
   - Seccion 6.3: ciclo de entrenamiento con guardado periodico.
   - Seccion 6.4: corrida principal (base, 600 000 pasos).
   - Seccion 6.5: experimentos con la estrategia epsilon-greedy.
   - Seccion 6.6: valores Q, objetivos TD y error TD.
   - Seccion 6.7: revision de la arquitectura y variante Dueling.
   - Seccion 6.8: evaluacion frente a un agente aleatorio y el heuristico.
   - Seccion 7: conclusiones.

3. resultados/
   Figuras y tablas de metricas exportadas de la ejecucion (las que se usan
   en el informe).

4. requirements.txt
   Dependencias de Python.

5. README.txt
   Este archivo.

No se incluyen ejecutables, archivos compilados ni pesos de los modelos.


EXPERIMENTOS
------------
Corrida      Que cambia                                         Pasos
base         Red original (Mnih et al., 2015), epsilon de 1.0     600 000
             a 0.02 en 100 000 pasos
eps_rapido   epsilon de 1.0 a 0.02 en 20 000 pasos                250 000
eps_lento    epsilon de 1.0 a 0.10 en 250 000 pasos               250 000
dueling      Cabeza Dueling (Wang et al., 2016) con el mismo      250 000
             numero de parametros

Las comparaciones se hacen sobre los primeros 250 000 pasos de cada corrida,
con la misma semilla y los mismos pesos iniciales.


COMO EJECUTAR
-------------
1. Abrir el notebook en Google Colab con GPU (Entorno de ejecucion >
   Cambiar tipo de entorno de ejecucion > T4 GPU).
2. Ejecutar las celdas en orden. La seccion 6.1 monta Google Drive; los pesos
   y las metricas se guardan en MyDrive/taller2_pong/.
3. Si Colab se desconecta durante un entrenamiento, ejecutar de nuevo las
   celdas hasta la 6.3 y luego la celda de la corrida: continua desde el
   ultimo guardado.
