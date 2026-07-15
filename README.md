# Laboratorio Ansible con Docker

## Objetivo

El objetivo de esta práctica fue crear un laboratorio con dos servidores Linux utilizando contenedores Docker y administrarlos mediante Ansible.

Se crearon dos contenedores Ubuntu llamados `server1` y `server2`, los cuales fueron configurados para permitir la administración automática mediante Ansible. A través del playbook se realizaron diferentes tareas como mostrar información del sistema, crear directorios y generar archivos dentro de los servidores.

## Estructura del proyecto
ansible-lab-practica/
│
├── docker-compose.yml
├── inventory.ini
├── playbook.yml
└── README.md

## Creación de los servidores Docker

Los servidores fueron creados utilizando Docker Compose con la imagen Ubuntu 24.04.

Para iniciar los contenedores se utilizó el comando:

```bash
docker compose up -d

## Evidencia de ejecución

A continuación se muestra la captura de la ejecución exitosa del playbook:
<img width="1650" height="875" alt="Captura de pantalla 2026-07-15 150207" src="https://github.com/user-attachments/assets/e6a6f328-749f-46f8-995e-a095b1529466" />
<img width="1742" height="890" alt="Captura de pantalla 2026-07-15 150400" src="https://github.com/user-attachments/assets/8c507991-28ef-4186-bd0c-4aa81b79466c" />
<img width="1253" height="496" alt="Captura de pantalla 2026-07-15 150422" src="https://github.com/user-attachments/assets/3ae7996c-cf19-47f2-9bed-0ad573cb662c" />



