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
### ¿Cómo entender el esquema usando los colores?

Para leer la imagen sin complicarse, solo sigue el código de colores:

* **Bloques azules** Son tus datos. El azul oscuro guarda lo que has visto antes; el azul claro atrapa lo que haces justo en este segundo.

<p align="center">
  <img src="https://img.shields.io/badge/Data_(Batch_Training)-3b82f6?style=for-the-badge&labelColor=1d4ed8" />
  <img src="https://img.shields.io/badge/Data_(Online_Training)-60a5fa?style=for-the-badge&labelColor=2563eb" />
</p>

* **Bloques verdes** Son las máquinas de ByteDance procesando la información y ajustando lo que te gusta en tiempo real.

<p align="center">
  <img src="https://img.shields.io/badge/Training_Worker-10b981?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Training_PS-10b981?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Serving_PS-10b981?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Model_Server-10b981?style=for-the-badge" />
</p>

* **Bloque amarillo** Eres tú con el teléfono en la mano.

<p align="center">
  <img src="https://img.shields.io/badge/User-f59e0b?style=for-the-badge" />
</p>

* **Líneas amarillas** Es el viaje de ida y vuelta. Cada que mueves un dedo, tu teléfono manda una señal y la app te devuelve al instante los siguientes videos.

<p align="center">
  <img src="https://img.shields.io/badge/User_Request_%E2%9E%94-f59e0b?style=flat-square" />
  <img src="https://img.shields.io/badge/%E2%86%90_Ranking_Result-10b981?style=flat-square" />
  <img src="https://img.shields.io/badge/User_Actions_%E2%9E%94-f59e0b?style=flat-square" />
</p>

