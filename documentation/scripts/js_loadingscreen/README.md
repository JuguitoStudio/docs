# 🧃 js_loadingscreen — Visión General

**js_loadingscreen** es una pantalla de carga minimalista, moderna y de alto rendimiento para FiveM. Diseñada pensando en la mejor experiencia estética y en el menor impacto de rendimiento posible.

---

## ✨ Características Principales

- 🎬 **Enfoque Cinematográfico Minimalista:** Centro 100% despejado y libre de desenfoques para lucir vídeos locales en alta definición (con soporte de playlist y sonido integrado) o carruseles de imágenes.
- 📱 **Tarjetas Flotantes a la Derecha:** Al pulsar cualquiera de las pestañas superiores (*Inicio, Reglas, Novedades, Equipo, Teclas*), se despliega una tarjeta acoplada a la derecha que flota suavemente entre el menú superior y los botones inferiores.
- ⌨️ **Modo Cine (<kbd>H</kbd>):** Atajo para ocultar toda la interfaz y disfrutar del vídeo sin interrupciones.
- 🎵 **Reproductor de Música con Visualizador:** Lista de reproducción con paso de canciones, pausar/reanudar, control de volumen, silenciador y mini ecualizador procedural reactivo dibujado en Canvas.
- 🚀 **Control de Carga & Cierre Suave:** Opción para requerir confirmación por tecla (<kbd>ESPACIO</kbd> o <kbd>ENTER</kbd>) al completar el 100% de la carga con fade out de interfaz y audio.
- 🌐 **Multi-Framework & Multiidioma:** Compatible con ESX, QB-Core, QBX y Standalone. Traducciones listas en español (`es.json`) e inglés (`en.json`).
- 🔌 **Integraciones 100% Abiertas:** Transiciones de cámara (`DoScreenFadeIn`), sonidos de spawn y contadores de jugadores personalizables en `integrations/`.

---

## 📸 Estructura Visual

```text
┌─────────────────────────────────────────────────────────────┐
│ [Logo] Servidor         [Inicio] [Reglas] [Equipo] [Teclas] │
│                                                             │
│                                           ┌───────────────┐ │
│                                           │  Tarjeta      │ │
│                 [ VÍDEO 100% ]            │  Flotante     │ │
│                 [ DESPEJADO  ]            │  a la Derecha │ │
│                                           │  (Opcional)   │ │
│                                           └───────────────┘ │
│                                                             │
│ [♫ Audio & Visualizador]   [Entrar]   [Discord] [Modo Cine] │
│ ─────────────────────────────────────────────────────────── │
│ [============== 100% Carga Completa ======================] │
└─────────────────────────────────────────────────────────────┘
```

---

## 📑 Siguientes Pasos

- 👉 [Guía de Instalación](scripts/js_loadingscreen/installation.md)
- 👉 [Referencia de Configuración](scripts/js_loadingscreen/config.md)
- 👉 [Adaptadores de Integración](scripts/js_loadingscreen/integrations.md)
- 👉 [Preguntas Frecuentes](scripts/js_loadingscreen/faq.md)
