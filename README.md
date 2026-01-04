# TerrorMeter

**Addon exclusivo de El Séquito del Terror**

Un medidor de daño ligero y eficiente, diseñado específicamente para los miembros del clan **El Séquito del Terror**. El registro de combate se analiza de manera independiente del idioma y funciona en clientes basados en 1.12 (vanilla) y 2.4.3 (burning crusade).

Este addon está optimizado para ofrecer un seguimiento de daño simple, rápido y que utiliza la menor cantidad de recursos posible.

---

## 🏴 El Séquito del Terror

```
┌─────────────────────────────────────────────────────────────┐
│                   EL SÉQUITO DEL TERROR                     │
│                                                             │
│  ╔═══════════════════════════════════════════════════════╗ │
│  ║                    TerrorMeter                        ║ │
│  ║              Medidor de Daño Exclusivo                ║ │
│  ╚═══════════════════════════════════════════════════════╝ │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │   Parser    │  │   Window    │  │  Settings   │        │
│  │  Combat Log │→ │   Display   │← │   Config    │        │
│  └─────────────┘  └─────────────┘  └─────────────┘        │
│         ↓                ↓                 ↓               │
│  ┌──────────────────────────────────────────────┐          │
│  │         Core Engine (core.lua)               │          │
│  └──────────────────────────────────────────────┘          │
│                                                             │
│  Características:                                           │
│  • Análisis en tiempo real del registro de combate         │
│  • Interfaz minimalista y personalizable                   │
│  • Bajo consumo de recursos                                │
│  • Compatible con Vanilla (1.12) y TBC (2.4.3)             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Arquitectura del Addon

```
TerrorMeter/
├── core.lua              # Motor principal del addon
├── parser.lua            # Analizador de combate (genérico)
├── parser-vanilla.lua    # Analizador específico para Vanilla
├── parser-tbc.lua        # Analizador específico para TBC
├── window.lua            # Interfaz gráfica y ventana principal
├── settings.lua          # Gestión de configuración
├── TerrorMeter.toc       # Descriptor del addon (Vanilla)
└── TerrorMeter-tbc.toc   # Descriptor del addon (TBC)
```

---

![TerrorMeter](screenshot.jpg)

![TerrorMeter](screenshot2.jpg)

## Instalación (Vanilla, 1.12)
1. Descarga la última versión del addon
2. Descomprime el archivo Zip
3. Renombra la carpeta a "TerrorMeter"
4. Copia "TerrorMeter" en Wow-Directory\Interface\AddOns
5. Reinicia WoW

## Instalación (The Burning Crusade, 2.4.3)
1. Descarga la última versión del addon
2. Descomprime el archivo Zip
3. Renombra la carpeta a "TerrorMeter-tbc"
4. Copia "TerrorMeter-tbc" en Wow-Directory\Interface\AddOns
5. Reinicia WoW

## Comandos

Los siguientes comandos pueden usarse para acceder a la configuración:
* **/terrormeter**
* **/tmeter**
* **/tm**

Si alguno ya está en uso por otro addon, simplemente usa un comando alternativo.
Opciones disponibles:

```
/tm visible 1        Mostrar ventana principal (0 o 1)
/tm height 17        Altura de las barras (cualquier número)
/tm trackall 0       Rastrear todas las unidades cercanas (0 o 1)
/tm texture 2        Establecer textura de la barra de estado (1 a 4)
/tm pastel 0         Usar colores pastel (0 o 1)
/tm backdrop 1       Mostrar fondo y borde de ventana (0 o 1)
/tm lock 0           Bloquear ventana y evitar que se mueva
/tm toggle           Alternar visibilidad de la ventana principal
```

## Rango del Registro de Combate

TerrorMeter se basa completamente en el registro de combate y no tiene ningún tipo de sincronización entre jugadores.
Esto significa que lo que ves está limitado por el rango máximo que tu registro de combate puede mostrar. Los valores predeterminados del juego están establecidos en 40 yardas.
Si deseas aumentar ese rango, puedes ejecutar el siguiente comando para establecerlo en 200:

    /run for _,n in pairs({"Party", "PartyPet", "FriendlyPlayers", "FriendlyPlayersPets", "HostilePlayers", "HostilePlayersPets", "Creature" }) do SetCVar("CombatLogRange"..n, 200) end

Alternativamente, puedes configurarlo manualmente en tu Config.wtf:

    SET CombatLogRangeParty "200"
    SET CombatLogRangePartyPet "200"
    SET CombatLogRangeFriendlyPlayers "200"
    SET CombatLogRangeFriendlyPlayersPets "200"
    SET CombatLogRangeHostilePlayers "200"
    SET CombatLogRangeHostilePlayersPets "200"
    SET CombatLogRangeCreature "200"

Ten en cuenta que algunos addons de marcos de unidad dependen de que el rango del registro de combate esté establecido exactamente en "40".
Aumentar el rango puede romper las verificaciones de rango de 40y de esos addons, y otros podrían simplemente restablecerlo a "40".

---

## 🛡️ Exclusivo para El Séquito del Terror

Este addon ha sido desarrollado y optimizado exclusivamente para los miembros del clan **El Séquito del Terror** en Turtle WoW.

**¡Por el Terror y la Gloria!**
