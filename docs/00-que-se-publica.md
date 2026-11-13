# Qué se publica y qué no

Este repositorio lo he configurado como público, así que cualquiera puede leerlo y acceder a la información. Quiero que sirva para entender cómo está montada 
la red de mi casa y por qué lo he hecho así, pero sin entregar información relevante que un atacante pueda usar contra mi red.

La seguridad de la red no depende de ocultar información: depende de exponer a Internet lo mínimo (solo la VPN), usar claves en vez de contraseñas y mantener todo actualizado 
constantemente (Seguridad y Alta Disponibilidad). 
No publicar ciertos datos es una capa más de protección, pero no debe ser la única.

## Qué va al repositorio y qué no

| Público (en el repositorio) | Privado (en `secretos/`, nunca se sube) |
| --- | --- |
| Arquitectura, rangos de IP privadas y decisiones | IP pública, dominio de DNS dinámico y puertos abiertos a Internet |
| Configuraciones con valores de ejemplo | Configuraciones reales, claves y contraseñas |
| Tipo de equipo («router del operador», «EliteDesk SFF») | Modelo y firmware del router, direcciones MAC e inventario |
| Versiones de lo que solo es accesible por VPN | Versiones de lo que está expuesto a Internet |
| — | Capturas de tráfico y registros de DNS de la casa |

Las IP privadas (`192.168.x.x`) sí se publican ya que solo sirven si alguien  ya está dentro de la red.

## Cómo lo cumplo

- **Carpeta `secretos/`:** está en el `.gitignore` y solo existe en mi equipo. Ahí guardo el inventario y los valores reales.
- **Plantillas con etiquetas:** en `config/`, los valores sensibles se sustituyen por etiquetas como `<PUERTO_WG>`, `<DOMINIO_DDNS>` o `<CLAVE_PRIVADA>`.
- **`.gitignore`:** bloquea claves (`*.key`, `*.pem`, `id_ed25519*`), ficheros `.env` y capturas de tráfico (`*.pcap`).
- **Protección de GitHub:** tengo activados *Secret Protection* y *Push protection*, que bloquean un `push` si detectan una clave o un token.
- **Correo privado:** los commits usan la dirección *noreply* de GitHub, no mi correo personal para evitar que me envíen spam.

## Antes de cada commit

1. Revisar con `git diff --staged` todo lo que voy a subir.
2. Comprobar que no aparece ninguna IP pública, dominio, clave, contraseña ni MAC.
3. Comprobar que las capturas de pantalla no muestran nada de la columna privada.

## Si se publica algo privado por error

Una serie de pasos que debo de seguir si algo se filtra o es comprometido:
1. **Considerarlo comprometido**, aunque lo borre enseguida: el historial de Git lo guarda y alguien puede haberlo copiado.
2. **Cambiarlo**: generar claves nuevas, cambiar contraseñas o cambiar el puerto.
3. Después, quitarlo del repositorio y anotar en el registro de decisiones qué pasó y qué he cambiado para que no se repita.
