# Linux Server Lab

## Descripción

Laboratorio de administración de servidores Linux realizado en Ubuntu Server.
Se configuran usuarios, permisos, acceso remoto SSH, servidor web Apache, firewall y copias de seguridad.

---

## Objetivos

* Instalar y configurar un servidor Linux
* Gestionar usuarios y permisos
* Configurar acceso remoto SSH
* Instalar y configurar servidor web Apache
* Configurar firewall
* Realizar copias de seguridad
* Documentar el proceso

---

## Arquitectura del sistema

Servidor Ubuntu Server con:

* Acceso SSH
* Servidor web Apache
* Firewall UFW
* Sistema de copias de seguridad
* Gestión de usuarios y permisos

---

## Configuración

### Actualización del sistema

```
sudo apt update
sudo apt upgrade
```

### Creación de usuarios

```
sudo adduser juan
sudo adduser fernando
sudo usermod -aG sudo juan
con estos comandos creamos los dos usuarios y añadimos juan al grupo sudo para que obtenga
permisos de administrador.
![usuarios](usuarios.png)
```

### Permisos y directorios

```
mkdir /empresa
mkdir /empresa/publico
mkdir /empresa/privado
chmod 755 /empresa/publico
chmod 700 /empresa/privado
chown usuario1 /empresa/privado
```

### SSH

```
sudo apt install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh
```

### Apache

```
sudo apt install apache2
sudo systemctl start apache2
```

### Firewall

```
sudo ufw allow ssh
sudo ufw allow 80
sudo ufw enable
```

### Backup

```
tar -czvf backup.tar.gz /empresa
```

---

## Pruebas de funcionamiento

* Conexión SSH correcta
* Acceso al servidor web desde navegador
* Firewall activo
* Backup generado correctamente
* Permisos funcionando correctamente

---

## Comandos utilizados

* adduser
* chmod
* chown
* systemctl
* ufw
* tar
* apt

---

## Conclusiones

Este laboratorio permite practicar tareas básicas de administración de sistemas Linux como gestión de usuarios, permisos, servicios, seguridad y copias de seguridad.
