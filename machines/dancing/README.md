# Dancing

| Field | Value |
|---|---|
| OS | Windows |
| Difficulty | Very Easy |
| Date | 2026-05-09 |
| Status | Retired |
| Skills | Starting Point Tier 0, enumeración, SMB |

## Summary
Máquina de Starting Point Tier 0 sobre Windows. El objetivo expone SMB y deja listar y leer un recurso compartido sin contraseña. La flag está en ese recurso.

## Recon
```
nmap -sC -sV -oN nmap.txt <IP>
```
El servicio relevante es SMB.

## Foothold
Enumerar los recursos compartidos y entrar al que no pide contraseña. Descargar el archivo de la flag.

## User
No hay una cuenta intermedia que comprometer. El acceso de lectura al recurso compartido basta.

## Privilege escalation
No aplica.

## Lessons learned
En Windows, un share SMB abierto es tan útil como un servicio con credenciales por defecto: primero se listan los recursos y los permisos, y después se leen.

## Evidence
No hay captura guardada en el repositorio.
