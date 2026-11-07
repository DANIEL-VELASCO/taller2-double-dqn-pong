# Taller 2 — Aprendizaje profundo por refuerzo: Double DQN en Pong

**Curso:** Aprendizaje Profundo, Maestría en Inteligencia Artificial, Pontificia Universidad Javeriana
**Estudiante:** Daniel Sebastian Velasco Munar

Agente Double DQN (TensorFlow/Keras) entrenado sobre `ALE/Pong-v5` con preprocesamiento estándar de Atari (84×84 en escala de grises, 4 cuadros apilados, *frame skip* de 4).

## Contenido

| Ruta | Descripción |
|---|---|
| `Taller_2_Aprendizaje_profundo__202630.ipynb` | Notebook con el código, los experimentos y su análisis |
| `requirements.txt` | Dependencias |
| `resultados/` | Figuras y métricas exportadas de la ejecución |
| `informe/` | Informe en formato IEEE Transactions on Artificial Intelligence |

## Experimentos

| Corrida | Qué cambia | Pasos |
|---|---|---|
| `base` | Red original (Mnih et al., 2015), ε de 1.0 a 0.02 en 100 000 pasos | 600 000 |
| `eps_rapido` | ε de 1.0 a 0.02 en 20 000 pasos | 250 000 |
| `eps_lento` | ε de 1.0 a 0.10 en 250 000 pasos | 250 000 |
| `dueling` | Cabeza Dueling (Wang et al., 2016) con el mismo número de parámetros | 250 000 |

La evaluación final compara los agentes entrenados con un agente aleatorio y con el agente heurístico que sigue la pelota.

## Cómo ejecutarlo

1. Abrir el notebook en Google Colab con GPU (Entorno de ejecución → Cambiar tipo de entorno → T4 GPU).
2. Ejecutar las celdas en orden. La sección 6.1 monta Google Drive; pesos y métricas se guardan en `MyDrive/taller2_pong/`.
3. Si Colab se desconecta durante un entrenamiento, ejecutar de nuevo las celdas hasta la 6.3 y luego la celda de la corrida: continúa desde el último guardado.
