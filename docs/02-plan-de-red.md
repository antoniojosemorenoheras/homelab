# Plan de direccionamiento

La red de casa usa una sola subred, `192.168.1.0/24` (Por ahora solo una subred hasta la v2). Cada tipo de equipo tiene su rango para que sea fácil saber qué es cada IP y para que no haya choques entre 
direcciones fijas y dinámicas.

## Rangos de la red de casa

| Rango | Uso | Cómo se asigna |
| --- | --- | --- |
| .1 | Router del operador (puerta de enlace) | Fija |
| .2 – .19 | Red: punto de acceso, equipo 24/7, firewall | IP fija configurada en el propio equipo |
| .20 – .49 | Servidores: pve-lab, máquinas virtuales, NAS | IP fija configurada en el propio equipo |
| .50 – .69 | Equipos de administración | Reserva por MAC en el router |
| .70 – .99 | Dispositivos fijos: televisores, impresora | Reserva por MAC en el router |
| .100 – .199 | Libre, para próximos equipos | — |
| .200 – .254 | Dispositivos dinámicos: móviles e invitados | DHCP del router |

## Equipos de infraestructura

| Equipo | IP | Estado |
| --- | --- | --- |
| Router | 192.168.1.1 | Asignada por defecto |
| Punto de acceso TP-Link | 192.168.1.2 | Por asignar |
| Equipo 24/7 (VPN y Wake on LAN) | 192.168.1.10 | Planificado |
| pve-lab (Proxmox) | 192.168.1.20 | Por asignar |
| NAS | 192.168.1.30 | Planificado |

## Reglas

- Los equipos de red y los servidores llevan **IP fija configurada en el propio equipo**, para que funcionen aunque falle el DHCP del router.
- Los equipos de administración y los dispositivos fijos usan **reserva por MAC**: siempre reciben la misma IP, pero se gestionan desde el router mediante DHCP.
- En los móviles y portátiles he asignado una parte aislada de la red en la que se asignarán las IPs mediante DHCP dinámico ya que la reserva por MAC no funciona con estos porque usan MAC aleatoria.
- Antes de dar una IP a un equipo nuevo, se apunta en el inventario privado.

## Pendiente

- Confirmar que el router permite cambiar el rango del DHCP y hacer reservas fuera de él (#12 y #13).
- Documentar las redes wifi y la zona que cubre cada punto de acceso (#14).
