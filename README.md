# Laboratorio Ansible con Docker

## Objetivo de la práctica

El objetivo de esta práctica fue crear un laboratorio con dos servidores Linux utilizando contenedores Docker y administrarlos mediante Ansible.

Durante el desarrollo de esta práctica creé dos contenedores Ubuntu llamados `server1` y `server2` utilizando Docker Compose. Luego configuré Ansible para establecer comunicación con ambos servidores y ejecutar tareas automatizadas mediante un playbook.

Con esta práctica aprendí cómo utilizar Ansible para administrar servidores de manera automática, permitiendo ejecutar configuraciones y tareas en diferentes servidores sin realizar cada proceso manualmente.

## Estructura del proyecto

ansible-lab-practica/
│
├── docker-compose.yml
├── inventory.ini
├── playbook.yml
└── README.md

## Creación de los servidores Docker

Para crear los servidores Linux utilicé Docker Compose con la imagen Ubuntu 24.04.

El comando utilizado para iniciar los contenedores fue:

docker compose up -d

Después verifiqué que los servidores estuvieran ejecutándose correctamente utilizando el comando:

docker ps

Luego instalé Python 3 dentro de cada contenedor, ya que es un requisito necesario para que Ansible pueda comunicarse con los servidores.

Los contenedores creados fueron:

- server1
- server2

## Configuración de Ansible

Configuré el archivo `inventory.ini` para definir los servidores que serían administrados por Ansible:

[docker]
server1 ansible_connection=docker
server2 ansible_connection=docker

Para comprobar la conexión entre Ansible y los contenedores ejecuté el comando:

ansible docker -i inventory.ini -m ping

La conexión fue exitosa, ya que ambos servidores respondieron correctamente con el mensaje `pong`.

## Ejecución del Playbook

Creé el archivo `playbook.yml` donde definí las tareas que Ansible debía ejecutar en ambos servidores.

Para ejecutar el playbook utilicé el siguiente comando:

ansible-playbook -i inventory.ini playbook.yml

Mediante el playbook realicé diferentes tareas, entre ellas:

- Mostrar el nombre de los servidores.
- Mostrar el sistema operativo utilizado.
- Crear el directorio `/tmp/ansible-demo`.
- Crear el archivo `info.txt`.
- Escribir información del servidor y del sistema operativo.
- Crear los directorios `logs`, `backup` y `config`.
- Mostrar un mensaje cuando el sistema operativo era Ubuntu.

La ejecución del playbook finalizó correctamente en ambos servidores, obteniendo un resultado exitoso con `failed=0`.

## Evidencia de ejecución exitosa

A continuación se muestra la captura de pantalla de la ejecución correcta del playbook:

![Ejecución exitosa del playbook]
<img width="1650" height="875" alt="Captura de pantalla 2026-07-15 150207" src="https://github.com/user-attachments/assets/0b76b80c-7697-4b1b-983d-829d51fc5c72" />
<img width="1742" height="890" alt="Captura de pantalla 2026-07-15 150400" src="https://github.com/user-attachments/assets/c76436c9-6b78-4825-ac17-8295831e799c" />
<img width="1742" height="890" alt="Captura de pantalla 2026-07-15 150400" src="https://github.com/user-attachments/assets/2f2fbf2b-1aa5-4cfc-afbd-e95f392f88f2" />
<img width="1253" height="496" alt="Captura de pantalla 2026-07-15 150422" src="https://github.com/user-attachments/assets/f4d5960f-2894-4d72-b43a-d2fda624dd80" />



