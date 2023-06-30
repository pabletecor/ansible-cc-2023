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

# 4. CREAR UN PLAYBOOK PARA HACER PING A AMBAS MÁQUINAS

Creo un playbook llamado ping.yml con el siguiente código:






