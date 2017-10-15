# Infraestructura Ansible para Moodle

[![N|Solid](http://savio.utbvirtual.edu.co/theme/image.php/materialdesign/theme/1501600329/logoutb_green)](evaluacion.utbvirtual.edu.co)

Configuración de 3 Máquinas
  - Ingenierias-1
  - Ingenierias-2
  - Ingenierias-3

### Ingenierias-1
Para que funcione solo es necesario instalar **Docker** y **pip**

Esta maquina es configurada mediante **ansible**, haciendo uso del modulo [docker_image](https://nodejs.org/) y un mini Dockerfile. Se construye una imagen llamada **php_apache** y con esto contruimos nuestro container.

```yaml
- name: Construir imagen
  docker_image:
    ...
- name: Create container
  docker_container:
    ...
```

Guardamos un rol *app* en Templates que posteriormente guardamos en nuestra maquina **ingenierias-1** y copiamos en la carpeta *opt/app*

Para ejecutar y configurar nuestra maquina **ingenierias-1** ejecutamos:
```sh
$ ansible-playbook web.yml [optional -i ../hosts]
```
