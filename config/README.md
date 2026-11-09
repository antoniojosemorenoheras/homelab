# Configuración

Plantillas de configuración de los servicios del homelab.

| Carpeta | Contenido |
| --- | --- |
| `wireguard/` | VPN para el acceso remoto |
| `nginx/` | Servidor web |

Estos ficheros son **plantillas**: los valores sensibles están sustituidos por etiquetas como `<PUERTO_WG>`, `<DOMINIO_DDNS>` o `<CLAVE_PRIVADA>`. Los valores reales están en `secretos/`, que no se sube al repositorio (ver la política de publicación en `docs/00-que-se-publica.md`).
