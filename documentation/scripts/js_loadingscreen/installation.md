# 🛠️ Instalación — js_loadingscreen

Sigue estos sencillos pasos para instalar y verificar **js_loadingscreen** en tu servidor FiveM.

---

## 1. Requisitos

- Servidor FiveM con Artifact **7290 o superior**.
- No requiere base de datos MySQL.
- Compatible con cualquier framework (ESX, QB-Core, QBX o Standalone).

---

## 2. Paso a Paso

### Paso 1: Colocar la carpeta
Copia la carpeta `js_loadingscreen` dentro del directorio `resources/` de tu servidor:

```text
📂 resources/
└── 📂 [juguito]/
    └── 📂 js_loadingscreen/
```

### Paso 2: Agregar a `server.cfg`
Añade la siguiente línea en tu archivo `server.cfg`:

```cfg
ensure js_loadingscreen
```

> 💡 **Tip:** Asegúrate de iniciarlo antes de los scripts de framework para que la pantalla de carga tome efecto de inmediato mientras los recursos se descargan.

### Paso 3: Configurar
Abre `config.lua` y `web/config.js` para personalizar:
- El nombre y eslogan de tu servidor.
- El ID del vídeo de YouTube o imágenes de fondo.
- Enlaces de Discord, Tienda y Web.
- Lista de canciones de música de fondo.
- Reglas, miembros del Staff y teclas de rol.

---

## 3. Verificación en Consola

Al iniciar el servidor en la consola verás la línea de confirmación:

```text
[JuguitoStudio] Loading Screen v1.0.0 — Loaded OK [framework: auto]
```

Si ves ese mensaje, la pantalla de carga está lista y operativa.
