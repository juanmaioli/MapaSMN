# SMN New Api

### Obtener TOKEN

```bash
TOKEN=$(curl -s https://www.smn.gob.ar/ | grep "localStorage.setItem('token',.*" | grep -o ", '.*'" | tr -d "'" | sed 's-, \(.*\)$-\1-g')
```

### Busca en la web https://www.smn.gob.ar el token que se renueva cada 24hs
```html
  <script type="text/javascript">
    localStorage.setItem('token', 'XXXXXXXXX');
  </script>
```

### Descargar JSON
```bash
curl 'https://ws1.smn.gob.ar/v1/weather/location/4864' -H "Authorization: JWT $TOKEN"
```

### Mas datos
https://foro.gustfront.com.ar/viewtopic.php?t=5252&start=40