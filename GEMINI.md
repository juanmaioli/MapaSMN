# 🗺️ MapaSMN - Contexto del Proyecto

Este proyecto es una herramienta de visualización geográfica que muestra diversas localidades y puntos de interés de la República Argentina, utilizando datos provistos por el SMN.

---

## 1. 📋 Descripción General 🇦🇷
El objetivo principal es mapear puntos geográficos (Ciudades, Parajes, Bases Militares, etc.) sobre un mapa interactivo basado en **Leaflet.js** y **OpenStreetMap**. El proyecto también documenta cómo interactuar con la API interna (no oficial) del SMN para obtener datos climáticos en tiempo real.

### Tecnologías Principales:
- **Frontend:** HTML5, JavaScript (ES6+).
- **Estilos:** Bootstrap 5.3.
- **Mapas:** Leaflet.js v1.9.3.
- **Datos:** JSON estático (`listaCiudadesSMN.json`).

---

## 2. 🚀 Ejecución y Despliegue 🛠️

Al ser una aplicación web estática, no requiere un proceso de compilación complejo.

### Ejecución Local:
Para visualizar el proyecto localmente, puedes:
1.  Abrir el archivo `index.html` directamente en cualquier navegador moderno.
2.  Usar un servidor estático simple para evitar problemas de CORS al cargar el JSON:
    ```bash
    # Usando Python
    python3 -m http.server 8000
    # Usando Node.js (si tienes serve instalado)
    npx serve .
    ```

### Despliegue:
El proyecto está configurado para funcionar en **GitHub Pages**.
- **URL:** [https://juanmaioli.github.io/MapaSMN/](https://juanmaioli.github.io/MapaSMN/)

---

## 3. 📂 Estructura de Archivos Clave 📄

| Archivo | Descripción |
| :--- | :--- |
| `index.html` | Contiene la estructura de la página, los estilos CSS y toda la lógica de JavaScript para renderizar el mapa y la tabla de ciudades. |
| `listaCiudadesSMN.json` | Base de datos en formato JSON que contiene el listado de puntos geográficos con sus coordenadas, nombres, provincias y IDs internos del SMN. |
| `README.md` | Documentación del proyecto e instrucciones detalladas sobre cómo obtener el TOKEN y consumir la API del SMN. |

---

## 4. ⚙️ Convenciones de Desarrollo 📝

- **Lógica Centralizada:** Actualmente, toda la lógica de inicialización del mapa y manipulación del DOM reside dentro de etiquetas `<script>` en `index.html`.
- **Manejo de Datos:** Los datos se cargan de forma asíncrona mediante `fetch()` desde el archivo `listaCiudadesSMN.json`.
- **Estilos:** Se utiliza una combinación de clases de Bootstrap y estilos embebidos para componentes específicos como el contenedor del mapa (`.minimapa`).
- **Codificación:** El proyecto utiliza `UTF-8` y está orientado a ser ligero y funcional sin dependencias de backend.

---

## 5. 💡 Notas sobre la API del SMN ☁️

El proyecto incluye una guía para extraer el token de sesión de la web oficial del SMN y realizar peticiones autenticadas a:
`https://ws1.smn.gob.ar/v1/weather/location/{id}`
Donde `{id}` corresponde al campo `smn_id_interno` presente en el archivo JSON.
