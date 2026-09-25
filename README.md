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

Si te fijas en la parte superior del diagrama, cada color representa una pieza clave del sistema[span_0](start_span)[span_0](end_span):

### ¿Cómo entender el esquema usando los colores?

Para leer la imagen sin complicarse, solo sigue el código de colores:

* **Bloques azules:** Son tus datos. El azul oscuro guarda lo que has visto antes; el azul claro atrapa lo que haces justo en este segundo.
* **Bloques verdes:** Son las máquinas de ByteDance procesando la información y ajustando lo que te gusta en tiempo real.
* **Bloque amarillo:** Eres tú con el teléfono en la mano.
* **Líneas amarillas:** Es el viaje de ida y vuelta. Cada que mueves un dedo, tu teléfono manda una señal y la app te devuelve al instante los siguientes videos.
  
