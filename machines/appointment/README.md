# Appointment

| Field | Value |
|---|---|
| OS | Linux |
| Difficulty | Very Easy |
| Date | 2026-11-05 |
| Status | Retired |
| Skills | Starting Point, enumeración web, Apache, inyección SQL en el login |

## Summary
Máquina de Starting Point orientada a una aplicación web. El único servicio útil es HTTP. La página de inicio es un formulario de login que concatena el usuario y la contraseña en una consulta SQL. Cerrar la cadena del usuario y comentar el resto permite entrar sin conocer la contraseña. La página autenticada muestra la flag.

## Recon
```
nmap -sC -sV -oN nmap.txt <IP>
```
Solo el puerto 80 está abierto. Nmap lo reporta como `Apache httpd 2.4.38 ((Debian))`. En el navegador, `http://<IP>` muestra un formulario de login.

## Foothold
El formulario construye una consulta del estilo `username='…' AND password='…'`. En el campo de usuario se envió `admin'#`, que cierra el literal del nombre y comenta la comprobación de la contraseña. La contraseña puede ser cualquiera. Si existe el usuario `admin`, la consulta devuelve una fila y el sitio da por válido el acceso.

## User
No hay shell ni usuario del sistema. La flag aparece en la página que se abre tras el login.

## Privilege escalation
No aplica.

## Lessons learned
Si un login mete el texto del formulario dentro de la consulta, no hace falta adivinar la contraseña. Hay que mirar qué parte de la consulta controla el usuario y qué parte se puede anular con un comentario.

## Evidence
No hay captura guardada en el repositorio.
