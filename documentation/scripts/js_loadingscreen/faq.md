# ❓ Preguntas Frecuentes & Solución de Problemas

Aquí encontrarás respuesta a las dudas más comunes sobre **js_loadingscreen**.

---

### ¿Por qué mi vídeo de YouTube no se reproduce?
1. Verifica que hayas puesto `Type = 'video'` en `config.lua` y `web/config.js`.
2. Asegúrate de poner únicamente el **ID** del vídeo (ejemplo: `dQw4w9WgXcQ`), no el enlace completo.
3. Algunos vídeos en YouTube tienen restricciones de inserción en sitios web de terceros configuradas por el autor. Prueba con otro vídeo público si la pantalla permanece negra.

---

### ¿Cómo cambio las canciones de música?
En `config.lua` y `web/config.js`, edita la tabla `Playlist`:
- Puedes usar URLs directas a archivos `.mp3` (que terminen en `.mp3`).
- O puedes guardar los archivos `.mp3` dentro de `web/assets/audio/` y poner la ruta relativa (por ejemplo: `assets/audio/cancion1.mp3`).

---

### ¿Cómo desactivo que el jugador tenga que presionar espacio para entrar?
Cambia la siguiente opción en `config.lua` y `web/config.js`:

```lua
Config.Shutdown = {
    RequireKeyPress = false, -- Entrará automáticamente cuando la carga llegue al 100%
}
```

---

### ¿Cómo cambio el logo y las imágenes locales?
1. Coloca tu archivo de imagen dentro de `js_loadingscreen/web/assets/images/`.
2. En `config.lua` y `web/config.js`, ajusta la ruta:
   ```lua
   Config.Server.Logo = 'assets/images/tu_logo.png'
   ```

---

### ¿Cómo agrego un nuevo idioma?
1. Duplica el archivo `locales/es.json`.
2. Nómbralo con el código ISO de tu idioma (ejemplo: `locales/pt.json`).
3. Traduce los textos dentro de ese archivo.
4. En `config.lua` cambia:
   ```lua
   Config.Locale = 'pt'
   ```
