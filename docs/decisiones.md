# Registro de decisiones

## D-001 · Equipo de segunda mano para el laboratorio

- **Fecha:** octubre de 2026
- **Estado:** aceptada

**Contexto:** necesitaba un equipo dedicado para el laboratorio. Mi Lenovo es antiguo y no da la talla para virtualizar, y además es con el que hago las tareas de ASIR y desde el que voy a administrar toda la red. Tenía que poder ejecutar varias máquinas virtuales a la vez sin gastarme mucho dinero.

**Decisión:** he comprado un HP EliteDesk de segunda mano por 60 € con un procesador i5-4590 y 16 GB de RAM DDR3. Le he puesto un SSD de 1 TB que he reutilizado de un portátil antiguo, conectado por SATA.

**Alternativas descartadas:**
- Comprar un ordenador de sobremesa nuevo para las tareas de ASIR, el laboratorio y jugar, que es lo que más presupuesto se llevaba. Lo descarté porque costaba entre 600 y 800 €, cubría más de lo que necesitaba el laboratorio y no era un gasto necesario.
- Reutilizar la torre antigua que tengo en casa (Pentium 4). La descarté porque es demasiado antigua y tiene muy poca RAM para virtualizar. La usaré solo para pruebas cortas y aisladas de firewall y captura de tráfico.

**Consecuencias:**
- Gano: un laboratorio completo por muy poco dinero, aprovechando piezas que ya tenía de un portátil antiguo.
- Pierdo: el hardware es antiguo, gasta más luz que uno moderno y no tiene garantía. Si se rompe, se cae todo el laboratorio. Además, es poco ampliable: los 4 slots de RAM ya están ocupados (solo podría ampliarla cambiando los módulos por otros más grandes) y solo queda hueco para un disco más.

## D-002 · Proxmox VE como base del laboratorio

- **Fecha:** octubre de 2026
- **Estado:** aceptada

**Contexto:** quería ejecutar varias máquinas virtuales y contenedores a la vez en el mismo equipo, tanto para las prácticas de ASIR como para montar laboratorios de ciberseguridad con máquinas vulnerables.

**Decisión:** he instalado Proxmox VE en el equipo de la D-001. Es una herramienta que se usa en empresas y me sirve para orientarme hacia la ciberseguridad, porque en ella puedo montar laboratorios vulnerables aislados.

**Alternativas descartadas:**
- Seguir con VirtualBox en mi Lenovo, que es lo que uso para las prácticas de clase. Lo descarté porque el portátil solo tiene 8 GB de RAM y no puede tener el laboratorio funcionando mientras trabajo con él. El Lenovo queda para administrar toda la red.

**Consecuencias:**
- Gano: máquinas virtuales y contenedores LXC en un solo equipo, snapshots, copias de seguridad con vzdump y gestión desde el navegador, sin pagar licencias.
- Pierdo: todo depende de un único equipo con hardware antiguo, y tengo que aprender a administrar Proxmox, que lleva su tiempo y dedicación.
