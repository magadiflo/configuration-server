# Servidor de configuración
Tomado del libro: "Microservicios, un enfoque integrado"

# Seguridad
Un aspecto importante en todo tipo de aplicaciones y, quizá todavía más en las distribuidas,
es la seguridad. Si un hacker fuera capaz de controlar el servidor de configuración nos 
enfrentaríamos a un verdadero desastre. Para evitar situaciones como ésta, es necesario 
añadir una capa de seguridad al servidor de configuración.

En el archivo de configuraciones agregamos la dependencia de Spring Security. Esto nos crea
por defecto un esquema de seguridad básico con un usuario: **user** y un password: **aleatorio**
impreso en la consola.   
Para cambiar esos valores (generados por defecto) agregamos la siguiente configuración en el archivo 
application.properties del servidor de configuración:

```
spring.security.user.name=admin
spring.security.user.password=M1C40S3rvices$2022Book
```

Si el servidor de configuración tiene definida la capa de seguridad, los clientes
deben conectarse indicando el usuario y contraseña que se requiera. Para ello, 
deben indicarlo en el fichero bootstrap.properties, tal como se muestra a continuación:

```
spring.cloud.config.username=admin
spring.cloud.config.password=M1C40S3rvices$2022Book
```