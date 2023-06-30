# ansible-cc-2023
Practica de Ansible de la asignatura Cloud Computing del master de Ingeniería Informática de la UHU

PASOS A SEGUIR

# 1. Instalar ansible en GCP

Abrimos la cloud shell e instalamos ansible con el comando

`pip install ansible`

# 2. Creación de dos máquinas virtuales (database, webserver)

La creación de ambas máquinas será de forma manual desde el compute engine de GCP.

# 3. Crear un inventario con ambas máquinas

En el editor de cloud shell creamos el archivo inventory.ini

```
[all]
34.175.159.163
34.175.23.5
```

Que contendrá las IPs publicas de nuestras máquinas

# 4. Crear un playbook para hacer ping a ambas máquinas

Creo un playbook llamado ping.yml con el siguiente código:

```
---

- hosts: all
  tasks:
  - name: Ping a los otros equipos
    action: ping
```

Para que el ping funcione, primero generamos una clave ssh con el comando

`ssh-keygen -t rsa`

En la carpeta oculta .ssh, se habrá generado la clave, abrimos el archivo id_rsa.pub y copiamos la clave generada.

La clave la copiamos en los ajustes de metadatos de google cloud compute engine, que las extiende a todas las instancias.

Para hacer ping usamos el comando

`ansible-playbook -i inventory.ini ping.yml`

Y podemos ver que funciona correctamente.

# 5. Crear un playbook para instalar apache y PHP en webserver y mysql en database

Modificamos el fichero inventory.ini y creamos el playbook playbook_instalador.yml, que se encuentran en el repositorio.

Para ejecutarlo simplemente usamos el comando `ansible-playbook -i inventory.ini playbook_instalador.yml`



