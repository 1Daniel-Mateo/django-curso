# DJANGO CURSO

**Prequisitos**

1. Instalar Python y pip
2. Crear un proyecto nuevo con django

# Guía para Windows

Crea el entorno virtual:

```
python -m venv venv
```

Corre tu proyecto y ejecutalo en el entorno virtual.

```
venv\Scripts\activate
```

Instala las dependencias del archivo requirements.txt

```
pip install -r requirements.txt
```

# Guía para Gestionar MySQL en Ubuntu/WSL

## 1. Instalación de MySQL

### 1.1. Actualizar el Sistema

Antes de instalar MySQL, es recomendable actualizar el sistema:

```
sudo apt update
sudo apt upgrade
```

### 1.2. Instalar MySQL Server y Librerías

Instala MySQL Server y las librerías necesarias:

```
sudo apt install mysql-server libmysqlclient-dev
```

### 1.3. Iniciar el Servicio de MySQL

Asegúrate de que el servicio de MySQL esté en funcionamiento:

```
sudo service mysql start
```

verificar  que esta activo

```
sudo service mysql status
```

## 2. Configuración Inicial de MySQL
### 2.1. Acceder a MySQL

Conéctate a MySQL como el usuario root:

```
sudo mysql
```
### 2.2. Configurar la Seguridad de MySQL

Ejecuta el siguiente comando para mejorar la seguridad de la instalación de MySQL:

```
sudo mysql_secure_installation
```
Sigue las instrucciones en pantalla para establecer una contraseña para el usuario root y configurar otras opciones de seguridad.

## 3. Crear una Base de Datos
### 3.1. Crear la Base de Datos

Una vez dentro de la consola de MySQL, crea una nueva base de datos:

```
CREATE DATABASE your_database_name;
```
### 3.2. Crear un Usuario

Crea un nuevo usuario y otórgale acceso a la base de datos. Si deseas usar el usuario root, puedes omitir este paso.

```
CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';
```
### 3.3. Otorgar Privilegios
Otorga privilegios al usuario para que pueda interactuar con la base de datos:

```
GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';
```

### 3.4. Flushing Privileges

Asegúrate de que MySQL reconozca los cambios:

```
FLUSH PRIVILEGES;
```

### 3.5 Salir

Sal de la consola de MySQL:


```
EXIT;
```

## 4 Ejecutar Migraciones 

**Nota:** Aplica para todos los sistemas operativos

### 4.1. Ir a la carpeta de la aplicación

Verifica que tu entorno este activo y que estés en la carpeta de tu aplicación.

Ejecuta las migraciones de Django para aplicar los cambios en la base de datos:
```
python manage.py migrate
```

## 5. Ejecutar Servidor

Ejecuta el servidor para desarrollo Django para que tu aplicación esté disponible en el navegador:

```
python manage.py runserver
```


