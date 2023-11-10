# Servicio de ejemplo: autenticación

Este es un pequeño ejemplo de implementación de un servicio simple de autenticación. El servicio permite crear cuentas de usuario y asociar un token a dichas cuentas. Este token puede ser validado posteriormente para verificar la autenticidad de una acción.

## Instalación
Descargar el repositorio:
```
git clone https://github.com/ptobiasdiaz/auth_service.git
```
Crear y activar un entorno virtual de python:
```
cd auth_service
python3 -m venv .venv
source .venv/bin/activate
```
Instalar dependencias:
```
pip install -r requirements.txt
```
## Ejecución
Ahora se puede ejecutar directamente el servicio:
```
python -m adiauth.server
```
O también, se puede instalar en el entorno virtual y ejecutar como comando independiente:
```
pip install ./
auth_service
```
## Opciones
Por defecto el servicio escuchará en todas las interfaces IP disponibles y en el puerto TCP 3001. Por defecto generará un token administrativo que se mostrará por pantalla:
```
Admin token: NMp01lQuX7QeD0gpGjFL_Jit9WA
```
Además, se usará como archivo de persistencia el fichero _users.json_ que se creará si no existe.

Se puede obtener una ayuda mediante la opción -h/--help:
```
$ python -m adiauth.server --help
usage: server.py [-h] [-a ADMIN_TOKEN] [-p PORT] [-l ADDRESS] [-d DB_FILE]

Auth server

options:
  -h, --help            show this help message and exit
  -a ADMIN_TOKEN, --admin-token ADMIN_TOKEN
                        Admin token
  -p PORT, --port PORT  Listening port (default: 3001)
  -l ADDRESS, --listening ADDRESS
                        Listening address (default: all interfaces)
  -d DB_FILE, --db DB_FILE
                        Database to use (default: users.json
```

Para establecer un token administrativo usaremos la opción -a/--admin-token:
```
$ python -m adiauth.server -a secret_administrative_token
```
Se pueden combiar las opciones disponibles de cualquier forma. La opcion de ayuda cancela la ejecución del programa.
