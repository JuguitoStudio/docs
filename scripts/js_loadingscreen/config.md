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

## 🎬 Fondos & Vídeo de YouTube (`Config.Backgrounds`)

### Para usar un vídeo de YouTube a pantalla completa:

```lua
Config.Backgrounds = {
    Type           = 'video',         -- Establece 'video'
    YoutubeVideoId = 'dQw4w9WgXcQ',   -- El ID de tu video de YouTube
}
```

> 📌 **¿Dónde encuentro el ID de YouTube?**
> En la URL `https://www.youtube.com/watch?v=dQw4w9WgXcQ`, el ID es la parte final: `dQw4w9WgXcQ`.

### Para usar un carrusel de imágenes:

```lua
Config.Backgrounds = {
    Type              = 'slideshow',  -- Establece 'slideshow'
    SlideshowInterval = 6500,         -- Tiempo en ms entre cada cambio de imagen
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
