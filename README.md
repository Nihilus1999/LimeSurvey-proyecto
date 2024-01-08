# LimeSurvey CE - Proyecto

Equipo conformado por:

- José El Asmar
- Karina Gonzalez
- Rafael Zappala
- Katherine Mendible
- Maria Gonzalez

## Descripción

Para demostrar la persistencia de datos al dar de baja todos los servicios y volver a crearlos, puedes seguir los siguientes pasos:

1. Asegúrate de que los servicios de LimeSurvey estén en ejecución utilizando el comando:
```
sudo docker ps
```
Esto debería mostrar los contenedores en ejecución para LimeSurvey y MariaDB.

2. Detén y elimina los contenedores de LimeSurvey y MariaDB ejecutando el siguiente comando en el directorio donde se encuentra el archivo `docker-compose.yaml`:
```
sudo docker-compose down
```
Esto detendrá y eliminará los contenedores, pero los volúmenes montados que contienen los datos persistirán.

3. Verifica que los contenedores se hayan detenido y eliminado correctamente ejecutando nuevamente el comando `sudo docker ps`. No deberían aparecer los contenedores de LimeSurvey y MariaDB en la lista de contenedores en ejecución.

4. Vuelve a crear los servicios de LimeSurvey y MariaDB utilizando el comando:
```
sudo docker-compose up -d
```
Esto iniciará los contenedores nuevamente utilizando la configuración definida en el archivo `docker-compose.yaml`.

5. Una vez que los contenedores estén en ejecución, accede a LimeSurvey a través de la dirección `http://localhost:8082` o `http://host-ip:8082` en tu navegador web.

6. Verifica que los datos persistan y estén intactos. Deberías poder ver las encuestas, temas y configuraciones que habías creado anteriormente.

Al dar de baja y volver a crear los servicios, los datos se mantendrán debido a los volúmenes montados en los directorios `./plugins`, `./upload` y `./config`. Estos volúmenes no se eliminan durante el proceso de dar de baja y volver a crear los contenedores, lo que garantiza la persistencia de los datos.

Recuerda que estos pasos son específicos para el tutorial proporcionado en el blog de Claudiu y pueden variar dependiendo de tu entorno y configuración particular.

https://claudiu.psychlab.eu/post/homelab-5-docker-limesurvey-plugins-nginxpm-proxy-automatic-batabase-backup/


