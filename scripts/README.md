# Scripts

Scripts de administración del homelab.

| Carpeta | Contenido |
| --- | --- |
| `wol/` | Encendido remoto de equipos con Wake on LAN |
| `backup/` | Copias de seguridad y restauración |

Reglas:

- Ningún script lleva contraseñas, claves, IP pública ni dominios reales. Los valores reales se leen de `secretos/` o de variables de entorno.
- Cada script explica su uso con `--help` y se detiene con un error si algo falla.
