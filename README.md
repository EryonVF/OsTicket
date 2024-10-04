# OsTicket Usuarios
API para la creacion de usuarios para Osticket

Utilizaremos las herramientas:
XAMPP Y POSTMAN

### Instalación 
Para esta instalacion no recomiendo realizar una copia del repositorio completo ya que puede generarte errores al intentar ejecutarlo.
Crearemos el archivo upload\include\api.users.php que es necesario para el funcionamiento de esta API

_Una vez tengas Osticket funcional y configurado sera necesario:_
1. Iniciar sesion como un agente Osticket.
2. Ir al panel de administracion/admin panel
3. Dirigimos al apartado Manage > API
4. Creamos nueva API key
5. Ingresamos la direccion IP donde se encuentra alojandose nuestra aplicacion(en este caso 127.0.0.1), ademas daremos click en las casillas para habilitar los permisos a la API key de JSON, XML e EMAIL
6. Despues la usaremos ya sea como un 'parametro' o como un 'header' para hacer llamados a nuestra API.

_Ahora para hacer un llamado a la API utilizaremos una aplicacion para pruebas ( PostMan )_
- Para hacer un llamado a la API sera necesario hacer un POST hacia la direccion: http://dominio-aplicacion/api/users.json\xml\email
  
1. Por ejemplo si alojas tu aplicacion utilizando XAMPP y quieres utilizar un formato json sera necesario utilizar una direccion asi:
- http://dominio-aplicacion/osticket/upload/api/users.json

En mi caso utilice : 
- http://127.0.0.1/api/users.json

2. Finalmente deberemos ingresar los datos necesarios para la creacion de usuarios, en este caso, en un formato json
   Nos dirigimos al Body > raw
   pegamos el siguiente codigo para la creacion del usuario
   
```
   {
    "email": "TheOne@ejemplo.com",
    "full_name": "TheOne",
    "phone": "123456789X686",
    "timezone": "America/Los_Angeles",
    "password": "123456",
    "confirm_password": "123456"
}
```

3.Confirmamos la creacion presionando el boton Send y nos arroja un mensaje en la parte inferior donde nos confirma si el usuario a sido creado o ya existe

Para validar la creacion del usuario en la base, se encuentra en el archivo "ost_user" 
