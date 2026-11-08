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

Configuración ultra-limpia sin duplicaciones:

```lua
Config.Background = {
    -- Options: 'video' | 'images'
    Mode = 'video',

    -- [Mode: 'video'] Local video file path inside web/ folder
    Video = 'assets/video/video.mp4',

    -- [Mode: 'video'] Enable video audio:
    -- true  -> Plays audio directly from the video. Bottom player controls volume/mute/pause.
    --          The background music playlist is disabled automatically to avoid audio clashes.
    -- false -> Keeps the video muted so the Config.Audio playlist plays instead.
    EnableAudio = false,

    -- [Mode: 'images'] Image slideshow list (local paths or external URLs)
    Images = {
        'https://images.unsplash.com/photo-1518709268805-4e9042af9f23?q=80&w=1920&auto=format&fit=crop',
        'https://images.unsplash.com/photo-1509198397868-475647b2a1e5?q=80&w=1920&auto=format&fit=crop',
    },

    -- [Mode: 'images'] Slideshow rotation interval in seconds
    Interval = 6,
}
```

---

## 🎵 Music Player (`Config.Audio`)

```lua
Config.Audio = {
    -- Enable background music player
    Enabled       = true,

    -- Automatically start playing when loading screen opens
    Autoplay      = true,

    -- Default volume percentage (0 to 100)
    DefaultVolume = 30,

    -- Local song playlist: Add as many local audio tracks as you want
    -- Audio files should be placed inside web/assets/audio/
    Playlist = {
        {
            Title  = 'Synthwave Chill',
            Artist = 'Juguito Studio',
            File   = 'assets/audio/song.mp3',
        },
        {
            Title  = 'Night Drive',
            Artist = 'Retro Wave',
            File   = 'assets/audio/song.mp3',
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
