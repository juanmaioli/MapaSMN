# Mapa De República Argentina en Leaflet.JS(leafletjs.com)
Este mapa contiene:
  - Barrio
  - Base Militar
  - Caserío
  - Centro de esquí
  - Ciudad
  - Colonia
  - Localidad
  - Observatorio
  - Otro
  - Paraje
  - Parque nacional
  - Paso fronterizo
  - Pueblo
  - Punto Turisitico
  - Villa

En el archivo **listaCiudadesSMN.json** contiene todos los datos geográficos provistos por el SMN, incluyendo el ID para utilizar la nueva API del SMN.

# Como usar la nueva API del SMN argentino
Esta API puede cambiar sin previo aviso. No es publica el SMN no da ningún api oficial.


### Obtener TOKEN:

```bash
TOKEN=$(curl -s https://www.smn.gob.ar/ | grep "localStorage.setItem('token',.*" | grep -o ", '.*'" | tr -d "'" | sed 's-, \(.*\)$-\1-g')
```

### Busca en la web https://www.smn.gob.ar el token que se renueva cada 24hs aprox.
```html
  <script type="text/javascript">
    localStorage.setItem('token', 'XXXXXXXXX');
  </script>
```

### Descargar JSON con datos del clima actualizado:
```bash
curl 'https://ws1.smn.gob.ar/v1/weather/location/4864' -H "Authorization: JWT $TOKEN"
```

### Mas datos sobre esta api:
https://foro.gustfront.com.ar/viewtopic.php?t=5252&start=40