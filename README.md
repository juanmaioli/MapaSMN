# 🗺️ Mapa De República Argentina en Leaflet.JS 🇦🇷

Este proyecto visualiza diversos puntos geográficos de Argentina utilizando datos del **Servicio Meteorológico Nacional (SMN)**.

## ✨ Características Nuevas (UpdateUI)
- **🎨 Interfaz Moderna:** Diseño basado en Bootstrap 5.3 con sombras suaves y tarjetas sin bordes.
- **☀️/🌙 Modo Oscuro Automático:** Soporte para temas claro y oscuro con detección automática y switch manual.
- **🚀 Optimización de Rendimiento:** 
  - Implementación de **Leaflet.markercluster** para manejar miles de puntos sin lag.
  - Carga optimizada de datos y renderizado eficiente del DOM.
- **📍 Tipos de Puntos:**
  - Barrio, Base Militar, Caserío, Centro de esquí, Ciudad, Colonia, Localidad, Observatorio, Paraje, Parque nacional, Paso fronterizo, Pueblo, Punto Turístico, Villa.

## 🚀 Ver en vivo
🔗 **[https://juanmaioli.github.io/MapaSMN/](https://juanmaioli.github.io/MapaSMN/)**

---

## 🛠️ Cómo usar la API (No Oficial) del SMN
Esta API es de uso interno del SMN y puede cambiar.

### 1. Obtener TOKEN
```bash
TOKEN=$(curl -s https://www.smn.gob.ar/ | grep "localStorage.setItem('token',.*" | grep -o ", '.*'" | tr -d "'" | sed 's-, \(.*\)$-\1-g')
```

### 2. Descargar datos del clima
```bash
curl 'https://ws1.smn.gob.ar/v1/weather/location/4864' -H "Authorization: JWT $TOKEN"
```

---
*Desarrollado por Juan Gabriel Maioli* 👨‍💻
