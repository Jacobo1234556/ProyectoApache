## ProyectoApache
Para levantarlo debemos configurar el fichero ***docker-compose.yml*** donde anotaremos lo siguiente:


* **Version**

Indicamos la version del VSC en micaso la versión 3,9

* **Services**

Nombre de nuestro servicio (Proyecto apache)

* **Nombre del contenedor**

Aquí le indico el nombre del contenedor y el nombre de la imagen ( apache)

image: php:7.4-apache
container_name: asir-apache

* **Puertos**

Le indicacms en el docker compose que puerto debe superponer en mi equipo con los puertos del docker

ports:
- '80:80'
- '8000:8000'
- '8080:8080'

Añadir puerto en port.conf y yml, añadir los puertos a los listen en port.conf **000-default.conf, 002-default.conf, 000-default.conf** la dirección de los html de la siguiente manera:

Tambien añadir  

```
<VirtualHost *:8000>
	
	ServerAdmin webmaster@localhost
	DocumentRoot /var/www/html/site2
```

Para poder usar los documentos.html/.php tememos que crear 2 directorios, 1 para cada uno:

_site1>
index.html_

_site2>
index.php_

_site3>
sitio3.php_

Para mapear nuestro sitio y usarlo en el server de Apache, tenemos que indicar en nuestros docker compose el mapeo de los puertos como indico a continuaci

* **Volumes**

Indicamos que nuestro directorio Sitio1 se corresponde con el /var/www/html que creamos en una carpeta html de Apache.

``` 
volumes:
- ./html:/var/www/html
- ./confApache:/etc/apache2
```
* **Conexion via Localhost**
 
- Ahora Para comprobar que funciona nos conectamos como localhost con el puerto que hemos indicado. 


