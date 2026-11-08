# 🔌 Integraciones Abiertas — js_loadingscreen

Todos los archivos dentro de `integrations/` son **100% de código abierto**. Están exentos del cifrado de Cfx.re Escrow (`escrow_ignore`) para que puedas adaptar cualquier comportamiento a la medida de tu servidor.

---

## 💻 Cliente (`integrations/client.lua`)

### `Integrations.onLoadingComplete(playerPed)`
Se ejecuta automáticamente en el momento en que la pantalla de carga se cierra y el jugador entra al mundo de FiveM.

```lua
function Integrations.onLoadingComplete(playerPed)
    -- Transición suave de pantalla
    DoScreenFadeIn(Config.Shutdown.FadeOutDurationMs or 800)

    -- Reproducir sonido de checkpoint
    if Config.UI.SoundEffects then
        PlaySoundFrontend(-1, 'CHECKPOINT_PERFECT', 'HUD_MINI_GAME_SOUNDSET', true)
    end

    -- 💡 Puedes agregar aquí:
    -- Iniciar cinemática de bienvenida
    -- Abrir menú de selección de personaje
    -- Sincronizar clima o tiempo inicial
end
```

### `Integrations.requestShutdown()`
Invocado para cerrar la ventana nativa de NUI de la pantalla de carga:

```lua
function Integrations.requestShutdown()
    ShutdownLoadingScreenNui()
    ShutdownLoadingScreen()
end
```

---

## 🖥️ Servidor (`integrations/server.lua`)

### `ServerIntegrations.getPlayerStats()`
Provee la cantidad de jugadores conectados y los slots máximos del servidor:

```lua
function ServerIntegrations.getPlayerStats()
    local online = #GetPlayers()
    local max = GetConvarInt('sv_maxclients', 48)
    return online, max
end
```

### `ServerIntegrations.onPlayerLoaded(source)`
Se dispara cuando el cliente confirma que ha cargado todos los recursos:

```lua
function ServerIntegrations.onPlayerLoaded(source)
    local name = GetPlayerName(source)
    -- Puedes enviar un webhook a Discord aquí:
    -- ServerIntegrations.discordLog(Config.Webhook, 'Jugador conectado', name .. ' ha entrado al servidor')
end
```
