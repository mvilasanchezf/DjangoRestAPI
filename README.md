# DjangoRestAPI
Buenas, soy Martín Vilasánchez y soy el alumno de segundo encargado de realizar la API sobre la que vais a trabajar en el proyecto para aprender a manejar peticiones a un back desde el front.

Para cualquier duda sobre este proyecto o la documentación que la acompaña, consultadle a vuestro profesor de la asignatura, para que os indique si el problema es de mi parte del trabajo o si es una competencia vuestra.

O en caso de que sea urgente asaltadme cuando queráis (no muerdo).

Sin mucho más que añadir os dejo con la documentación.

Se trata de una API REST desarrollada en Django, que permite la gestión de libros con sus respectivas categorías.


## ASIR

### Instalar Python

Para poder trabajar con Django, se debe tener instalado Python en el equipo. Para ello se debe descargar el instalador de Python desde la página oficial de Python: https://www.python.org/downloads/ y seguir los pasos de instalación. Tambien hay que marcar el checkbox de "Add Python 3.8 to PATH" para poder ejecutar Python desde la consola de comandos.

### Crear el entorno virtual

Ahora indicaré como "iniciar" el entorno virtual, para ello se debe ejecutar el siguiente comando en una consola de comandos (CMD o la del propio IDE) (Esta parte esta pensada para los compañeros de ASIR):

``` python -m venv venv ``` IMPORTANTE: Todo esto mientras estamos en la carpeta del proyecto.

Una vez creado el entorno virtual, se debe activar con el siguiente comando:

``` .\venv\Scripts\activate ``` 

### Instalar Django y Django Rest Framework

Una vez dentro del entorno virtual se debe instalar Django con el siguiente comando:

``` pip install django ``` 

Tambien se debe instalar Django Rest Framework con el siguiente comando:

``` pip install djangorestframework ``` 

A partir de este momento, ya podemos ejecutar el servidor de Django, para ello se debe ejecutar el siguiente comando:

``` python manage.py runserver ``` En la nueva consola de comandos para este espacio virtual.

Tambien hay que tenre en cuenta que esta API esta funcionando en el puerto 8000, por lo que se debe tener en cuenta para poder acceder a ella.

## DAM

Apartir de este punto ya entraria a trabajar el equipo de Desarrollo (DAM), os dejo con la documentación de la API.

## API REST

La API REST que se ha desarrollado en Django, permite la gestión de libros con sus respectivas categorías.

### Libros

A la hora de gestionar los libros, se debe tener en cuenta los siguientes campos:

- **id**: Identificador del libro. Este campo es autoincremental. (Tipo de dato: int)
- **titulo**: Título del libro. (Tipo de dato: string)
- **autor**: Autor del libro. (Tipo de dato: string)
- **precio**: Precio del libro. (Tipo de dato: decimal (es un string, mismo perro distinto collar))
- **descripcion**: Descripción del libro. (Tipo de dato: text)

Estos campos son obligatorios a la hora de crear un libro. Excepto el campo **id**, que es autoincremental.
Tambien hay que tener en cuenta que el campo **precio** es un campo de tipo string, por lo que se debe introducir un valor numérico, pero en formato string. Por ejemplo: "10.50". Esto es debido a que el campo **precio** es un campo de tipo decimal, y Django no permite el uso de este tipo de dato en las peticiones POST y PUT. Por lo que se ha optado por usar un campo de tipo string. Esto no afecta a la funcionalidad de la API. Aun así, se debe tener en cuenta a la hora de realizar las peticiones.

Otro factor a tener en cuenta es que el campo **descripcion** es un campo de tipo text, por lo que se puede introducir un texto de cualquier longitud.

Y por último, se debe tener en cuenta que todos los datos que se "mueven" entre el front y el back, se hacen en formato JSON. Por lo que se debe tener en cuenta a la hora de realizar las peticiones. Por ejemplo, si se quiere crear un libro, se debe enviar un JSON con los campos obligatorios siguiendo esta estructura: 
    
``` { "titulo": "El señor de los anillos", "autor": "J.R.R. Tolkien", "precio": "10.50", "descripcion": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nisl tincidunt nisl, eget aliquet nunc nisl eget nisl. Donec auctor, nisl eget ultricies lacinia, nisl nisl tincidunt nisl, eget aliquet nunc nisl eget nisl. Donec auctor, nisl eget ultricies lacinia, nisl nisl tincidunt nisl, eget aliquet nunc nisl eget nisl. Donec auctor, nisl eget ultricies lacinia, nisl nisl tincidunt nisl, eget aliquet nunc nisl eget nisl. Donec auctor, nisl eget ultricies lacinia, nisl nisl tincidunt nisl, eget aliquet nunc nisl eget nisl."} ```

Para más información sobre el formato JSON, se puede consultar la siguiente URL: https://www.json.org/json-es.html   

A continuación se detallan las peticiones que se pueden realizar a la API para gestionar los libros. Para más información sobre las peticiones, se puede consultar la siguiente URL: https://developer.mozilla.org/es/docs/Web/HTTP/Methods

#### GET

Para obtener todos los libros, se debe realizar una petición GET a la siguiente URL:

``` http://localhost:8000/api/projects/ ```

Para obtener un libro en concreto, se debe realizar una petición GET a la siguiente URL:

``` http://localhost:8000/api/projects/<id>/ ```
#### POST

Para crear un libro, se debe realizar una petición POST a la siguiente URL:

``` http://localhost:8000/api/projects/ ```
#### PUT

Para actualizar un libro, se debe realizar una petición PUT a la siguiente URL:

``` http://localhost:8000/api/projects/<id>/ ```
#### DELETE

Para eliminar un libro, se debe realizar una petición DELETE a la siguiente URL:

``` http://localhost:8000/api/projects/<id>/ ```

Estas peticiones estas documentadas para hacerse en un entorno local, pero si se quiere hacer en un entorno de producción, se debe cambiar la URL por la URL de producción. Por ejemplo, si se quiere hacer en un entorno de producción, se debe cambiar la URL por la siguiente:

Esta nueva URL daberia indicarosla vuestro profesor, pero por si acaso, dejo por aquí el esquema de como hacerlo.

``` http://<URL_PRODUCCION>/api/projects/ ```

``` http://<URL_PRODUCCION>/api/projects/<id>/ ```

Y este es el final de la documentación. Espero que os haya sido de ayuda.