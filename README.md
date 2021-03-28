# ecosistema-drupal-mapas

#detener el servidor de apache
  sudo /etc/init.d/apache2 stop

*Borrar el archivo composer.lock en docroot




#Iniciar contenedor
    ```
 $ fin system start
    ```

En la carpeta docroot
    ```
 $ fin composer update
     ```
 Luego
     ```
 $ fin composer install
    ```
    
2. Setup VM.
Before setting up the VM on your local, you'll need to install Docksal on your machine. Visit [Docksal Installation Page](https://docksal.io/installation) for more info. Also, consider visiting [The Official Documentation Site](https://docs.docksal.io/).
    ```
    $ fin vm start (only if you're using VirtualBox)
    ```
    ```
    $ fin p start
    ```
    ```
    $ fin hosts add
    ```


Agregar la clave ssh https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04-es 
$ fin ssh-key add ${id_rsa}


Install basic site using this command.


Importar Base de datos descomprimir archivo y cambiar el nombre a "mapas.sql"
Desde la carpeta raiz:
    ```
    $ fin db import dumps/mapas.sql
    
 
 $ fin drush si -Borrar tablas y restablece la base de datos
Log into your site with drush. Access the site and do necessary work at http://local.mintic-mapas.com/ mas lo que se genera con el sigueinte comando desde/user
    ```
 $ fin drush uli
    ```
    
Se ha instalado:
Admin-toolbar,Ludwig,Bootstrap, Webform, Taxonomy Manager, Csv importador, Taxonomy Place,Coutry_state_city, Geofield, LeftLet, prfile

despues de hacer cambios en la plataforma puedes seguir este tutorial para mas informacion https://www.solucionex.com/blog/como-trabajar-en-grupo-con-drupal-8-git-composer-config-split-de-forma-correcta


para hacer cambios crear rama git checkout -b nombre_rama

en la carpeta docroot corres exporantando los cambios del .yaml

 $ fin drush cex -y

 $ git add config/sync

 $ git commit -m "uploading needed packages"

 $ git push orgin nombre_rama --- es en la que esta


 $ git pull 

Para trar los cambios que han hecho en el repositorio

Borrar Cache 

 $ sudo systemd-resolve --flush-caches


en la carpeta Docroot

 $ fin drush cim -y

si sale error ir a la ruta docroot/core/lib/Drupal/Core/Config/ConfigImporter.php y comentar la linea 755










