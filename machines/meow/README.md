# Meow

| Field | Value |
|---|---|
| OS | Linux |
| Difficulty | Very Easy |
| Date | 2026-05-08 |
| Status | Retired |
| Skills | Starting Point Tier 0, enumeración, Telnet, credenciales por defecto |

## Summary
Máquina de Starting Point pensada para el primer contacto con el laboratorio: conectar la VPN, ver qué escucha el objetivo y entrar por un servicio Telnet que acepta credenciales por defecto. El acceso que se consigue ya es el de mayor privilegio.

## Recon
```
nmap -sC -sV -oN nmap.txt <IP>
```
El servicio relevante es Telnet.

## Foothold
Conectar al servicio Telnet e iniciar sesión con la credencial por defecto del administrador. Desde esa sesión se lee la flag.

## User
No hay un usuario intermedio. La misma sesión del servicio entrega la flag.

## Privilege escalation
No aplica. La sesión ya entra como administrador.

## Lessons learned
En un objetivo nuevo, el primer paso es confirmar la VPN y enumerar. Un servicio antiguo expuesto con credenciales por defecto puede ser todo el camino.

## Evidence
No hay captura guardada en el repositorio.
