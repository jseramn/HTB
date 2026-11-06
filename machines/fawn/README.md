# Fawn

| Field | Value |
|---|---|
| OS | Linux |
| Difficulty | Very Easy |
| Date | 2026-05-09 |
| Status | Retired |
| Skills | Starting Point Tier 0, enumeración, FTP anónimo |

## Summary
Máquina de Starting Point Tier 0. El objetivo expone FTP y permite entrar sin cuenta, en modo anónimo. Dentro del directorio accesible está la flag; no hace falta una shell ni escalar privilegios.

## Recon
```
nmap -sC -sV -oN nmap.txt <IP>
```
El servicio relevante es FTP.

## Foothold
Conectar por FTP como usuario anónimo, listar el directorio y descargar el archivo de la flag.

## User
No hay separación entre usuario y sistema. La flag se obtiene del propio recurso FTP.

## Privilege escalation
No aplica.

## Lessons learned
Un servicio de transferencia mal configurado puede entregar archivos sensibles sin autenticación. Conviene mirar el listado antes de asumir que hace falta explotar otra cosa.

## Evidence
No hay captura guardada en el repositorio.
