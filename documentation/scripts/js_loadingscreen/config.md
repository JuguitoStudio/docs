# ⚙️ Configuración — js_loadingscreen

Toda la configuración del script se encuentra en dos archivos:
- `config.lua`: Para comportamiento del servidor y control de spawn.
- `web/config.js`: Para el renderizado inmediato del navegador CEF al conectarse.

Ambos archivos contienen exactamente las mismas opciones para que todo esté sincronizado.

---

## 🌐 Configuración General

```lua
Config.Locale = 'es'          -- Idioma: 'es' | 'en' | añade tu propio archivo en locales/
Config.Framework = 'auto'     -- 'auto' | 'esx' | 'qb' | 'qbx' | 'standalone'
Config.Debug = false          -- Logs de depuración en consola
```

---

## 🎨 Estética & Modo Minimalista (`Config.UI`)

| Opción | Tipo | Descripción | Por Defecto |
|---|---|---|---|
| `AccentColor` | `string` | Color principal de realce (hex) | `'#5b7cff'` |
| `Minimalist` | `boolean` | Deja el centro 100% despejado para vídeos | `true` |
| `StartWithModalOpen` | `boolean` | Si es `true`, abre una tarjeta al inicio. Si es `false`, inicia con la pantalla totalmente libre. | `false` |
| `VignetteOnly` | `boolean` | Elimina desenfoques sobre el vídeo, dejando solo sombra suave en los bordes | `true` |
| `Darkness` | `number` | Nivel de oscuridad sobre el fondo (0.0 a 1.0) | `0.18` |
| `CinemaModeKey` | `string` | Tecla para alternar el Modo Cine (ocultar toda la UI) | `'H'` |
| `SoundEffects` | `boolean` | Activar efectos de sonido al interactuar | `true` |
| `ShowVisualizer` | `boolean` | Mostrar u ocultar el mini ecualizador procedural | `true` |

---

## 🎬 Fondos & Vídeo (`Config.Background`)

Elige el modo deseado en `Mode`. Cada modo tiene su parámetro dedicado, evitando duplicaciones:

```lua
Config.Background = {
    -- Modos disponibles: 'local_video' | 'url_video' | 'youtube' | 'images'
    Mode = 'local_video',

    -- [1] Modo 'local_video' (Recomendado): Coloca tu .mp4 en web/assets/video/
    LocalVideo = 'assets/video/video.mp4',

    -- [2] Modo 'url_video': Enlace directo web a un video .mp4 o .webm
    UrlVideo = 'https://miservidor.com/trailer.mp4',

    -- [3] Modo 'youtube': Enlace o ID de YouTube
    Youtube = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ',

    -- [4] Modo 'images': Carrusel de imágenes
    Images = {
        'assets/images/fondo1.png',
        'https://miservidor.com/fondo2.jpg',
    },
    SlideshowInterval = 6500,
}
```

> ⚡ **Recomendación:** `local_video` ofrece la mayor fluidez y calidad de imagen a 60 FPS, sin depender de la conexión a internet ni de bloqueos de YouTube.
    Images            = {
        'assets/images/fondo1.png',
        'https://tuservidor.com/fondo2.jpg',
    },
}
```

---

## 🎵 Reproductor de Música (`Config.Audio`)

```lua
Config.Audio = {
    Enabled       = true,  -- Habilitar reproductor de música
    Autoplay      = true,  -- Iniciar música automáticamente al entrar
    DefaultVolume = 25,    -- Volumen inicial (0 a 100)
    Playlist      = {
        {
            Title  = 'Midnight City (Synthwave)',
            Artist = 'Juguito Beats',
            File   = 'https://assets.mixkit.co/music/preview/mixkit-game-level-music-689.mp3',
        },
    },
}
```

---

## 🚀 Control de Salida (`Config.Shutdown`)

```lua
Config.Shutdown = {
    -- Si es true, el jugador debe presionar [ESPACIO] o [ENTER] al llegar al 100% para entrar
    -- Si es false, se cierra automáticamente al terminar de cargar
    RequireKeyPress    = true,

    -- Retraso en ms antes de cerrar (si RequireKeyPress = false)
    AutoCloseDelayMs   = 1200,

    -- Duración del desvanecimiento (fade out) de la UI y del audio
    FadeOutDurationMs  = 800,
}
```
