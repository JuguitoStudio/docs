# 🏁 Guía General de Inicio

Esta guía cubre los requisitos comunes y recomendaciones para la instalación de cualquier recurso de **JuguitoStudio** en tu servidor FiveM.

---

## 📋 Requisitos del Servidor

1. **Artifact de FiveM:**
   - Recomendamos utilizar el artifact de servidor **7290 o superior**.
2. **OneSync:**
   - Se recomienda `set onesync on` o `set onesync_enableInfinity 1` en tu `server.cfg`.
3. **Versión de Lua:**
   - Todos nuestros scripts usan Lua 5.4 nativo (`lua54 'yes'`).

---

## 📂 Organización Recomendada en `resources/`

Para mantener tu servidor limpio y ordenado, recomendamos agrupar todos los scripts de JuguitoStudio dentro de una subcarpeta corchete:

```text
📂 resources/
└── 📂 [juguito]/
    └── 📂 js_loadingscreen/
    └── 📂 js_futuroscript/
```

En tu `server.cfg`, puedes iniciar los scripts individualmente o la carpeta completa:

```cfg
# Opción A: Iniciar script individual
ensure js_loadingscreen

# Opción B: Iniciar todo el paquete JuguitoStudio
ensure [juguito]
```

---

## 🔒 Sistema Cfx.re Asset Escrow

La mayoría de los recursos para la venta en nuestra tienda utilizan el cifrado oficial de **Cfx.re (Keymaster)**.

### Lo que NUNCA está cifrado:
- `config.lua`: Para configurar al 100% el comportamiento del script.
- `web/config.js`: Opciones visuales y contenidos multimedia.
- `integrations/`: Adaptadores para tus inventarios, sistemas de target, llaves, gasolinas, etc.
- `locales/`: Todos los archivos JSON de traducción de idiomas.

> ⚠️ **Importante:** Asegúrate de descargar los scripts desde la cuenta de Keymaster vinculada a la licencia del servidor donde se ejecutarán.
