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