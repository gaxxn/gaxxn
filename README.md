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

Si te fijas en la parte superior del diagrama, cada color representa una pieza clave del sistema

### ¿Cómo entender el esquema usando los colores?

Para leer la imagen sin complicarse, solo sigue el código de colores:

* **Bloques azules:** Son tus datos. El azul oscuro guarda lo que has visto antes; el azul claro atrapa lo que haces justo en este segundo.

<p align="center">
  <span style="background-color: #d0e1f9; color: #1e3a8a; padding: 4px 10px; border-radius: 6px; font-weight: bold; font-size: 12px; margin-right: 4px;">Data (Batch Training)</span>
  <span style="background-color: #d0e1f9; color: #1e3a8a; padding: 4px 10px; border-radius: 6px; font-weight: bold; font-size: 12px;">Data (Online Training)</span>
</p>

* **Bloques verdes:** Son las máquinas de ByteDance procesando la información y ajustando lo que te gusta en tiempo real.

<p align="center">
  <span style="background-color: #d1fae5; color: #065f46; padding: 4px 8px; border-radius: 6px; font-weight: bold; font-size: 11px; margin-right: 2px;">Training Worker</span>
  <span style="background-color: #d1fae5; color: #065f46; padding: 4px 8px; border-radius: 6px; font-weight: bold; font-size: 11px; margin-right: 2px;">Training PS</span>
  <span style="background-color: #d1fae5; color: #065f46; padding: 4px 8px; border-radius: 6px; font-weight: bold; font-size: 11px; margin-right: 2px;">Serving PS</span>
  <span style="background-color: #d1fae5; color: #065f46; padding: 4px 8px; border-radius: 6px; font-weight: bold; font-size: 11px;">Model Server</span>
</p>

* **Bloque amarillo:** Eres tú con el teléfono en la mano.

<p align="center">
  <span style="background-color: #fef3c7; color: #92400e; padding: 4px 12px; border-radius: 6px; font-weight: bold; font-size: 12px;">User</span>
</p>

* **Líneas amarillas:** Es el viaje de ida y vuelta. Cada que mueves un dedo, tu teléfono manda una señal y la app te devuelve al instante los siguientes videos.

<p align="center">
  <span style="background-color: #fef3c7; color: #92400e; padding: 4px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">User Request ➔</span>
  &nbsp;
  <span style="background-color: #d1fae5; color: #065f46; padding: 4px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">&#8592; Ranking Result</span>
  &nbsp;
  <span style="background-color: #fef3c7; color: #92400e; padding: 4px 8px; border-radius: 4px; font-weight: bold; font-size: 11px;">User Actions ➔</span>
</p>
