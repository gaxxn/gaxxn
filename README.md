# Explicando el Algoritmo de TikTok

---

Esto forma parte de un proyecto a inicios del 2024 en el cual desmenuzaré y explicaré el algoritmo de TikTok ¿por qué es tan adictivo? y ¿cómo se hizo?

---
<img width="374" height="374" alt="539" src="https://github.com/user-attachments/assets/63287ab9-ceaf-4c76-8a5c-d11cf1220198" />

---
TikTok no funciona con un algoritmo estático ni mediante simples filtros por categorías. La plataforma utiliza un motor de inteligencia artificial de aprendizaje profundo llamado **Monolith**, diseñado para analizar, procesar y aprender de tu comportamiento en tiempo real a medida que interactúas con la aplicación.

# cada like, cada que cambias de video, cada comentario es aprendido por Monolith

<img width="1200" height="734" alt="540" src="https://github.com/user-attachments/assets/9ab87b10-5bf1-4621-a9ff-a6bfac9a55da" />

---
### Arquitectura de Monolith: ¿Cómo procesa los datos?

Para entender el esquema técnico de ByteDance, la arquitectura se divide en dos fases principales que trabajan en paralelo[span_0](start_span)[span_0](end_span):

#### 1. Entrenamiento por Lotes (Batch Training Stage)
Es el aprendizaje a largo plazo[span_1](start_span)[span_1](end_span).
- Procesa el historial antiguo de los usuarios (*Historical batch data*)[span_2](start_span)[span_2](end_span).
- Ajusta la base general del modelo con patrones globales de comportamiento[span_3](start_span)[span_3](end_span).
- Sirve para que el sistema mantenga una estructura sólida sobre gustos generales[span_4](start_span)[span_4](end_span).

#### 2. Entrenamiento en Tiempo Real (Online Training Stage)
Es el secreto de la inmediatez de TikTok[span_5](start_span)[span_5](end_span).
- **Captura en vivo:** Cada acción del usuario (*User Actions*) como deslizar, dar *like* o comentar se envía al sistema como un flujo de datos continuo (*Online streaming data*)[span_6](start_span)[span_6](end_span).
- **Sincronización de Parámetros:** En cuestión de milisegundos, los servidores de entrenamiento (*Training PS*) actualizan los datos y se los pasan a los servidores de recomendación (*Serving PS / Model Server*)[span_7](start_span)[span_7](end_span).
- **Resultado inmediato:** El servidor devuelve una lista de videos reordenada (*Ranking Result*) adaptada a lo que acabas de hacer hace apenas unos segundos[span_8](start_span)[span_8](end_span).
- 
