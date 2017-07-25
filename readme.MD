## Prerequisitos
Se debe instalar [wp-cli](http://wp-cli.org/)

#### Alternativa de instalación de wp-cli para windows
Es posible instalarlo sin usar curl o wget siguiendo [estas instrucciones](https://make.wordpress.org/cli/handbook/installing/#installing-on-windows)

### Prerrequisitos adicionales en Windows
Las carpetas en las que están los ejecutables de git.exe, mysql.exe y ep-cli.exe deben agregarse al path 

## Instalación

1. Crear la base de datos (si se está usando Xampp se puede crear en phpmyadmin)

2. Se clona el repositorio en la carpeta en donde debería ir el proyecto (por ejemplo, si el servidor es xampp debería in en la carpeta ```htdocs```)

```bash
git clone https://github.com/cier-centro/pd-zipaquira.git
```

3. Se descarga [versionpress 3.0.2](https://versionpress.net/) y se copia dentro del repositorio en la carpeta ```wp-content/plugins/```

4. Para crear el archivo ```wp-config.php``` automáticamente se corre el comando

```bash
cd pd-zipaquira
wp core config --dbname=NOMBRE_DE_LA_BASE_DE_DATOS --dbuser=USUARIO_DE_LA_BASE_DE_DATOS --dbpass=PASSWORD_USUARIO
```

Por lo general el usuario de la base de datos es root, de cualquier forma es conveniente verificar.

5. Para restaurar el sitio se corre el comando 

```bash
wp vp restore-site --siteurl=http://localhost/pd-zipaquira --require=wp-content/plugins/versionpress/src/Cli/vp.php
```
Para la linea anterior se recomienda usar el dominio o la ip registrada
