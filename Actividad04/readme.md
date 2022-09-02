# Creación de un API en Node.js

## Comenzando un proyecto con Nodejs y Express 

Comenzaremos nuestro proyecto de Node con express. Usaremos una herramienta muy útil para comenzar un proyecto con express: el express generation tool: [https://expressjs.com/en/starter/generator.html](https://expressjs.com/en/starter/generator.html).

Esta herramienta nos permite crear toda la estructura de un proyecto desde línea de comandos, simplemente ingresando el nombre del proyecto. Definirá algunas dependencias útiles en todo proyecto express, que luego podremos modificar, si lo necesitamos. Lo primero que haremos es instalar la herramienta:

```
npm install express-generator -g
```

Si ejecutas: ```express –help```, verás las opciones disponibles para la creación de tu proyecto. Podrás configurar el view engines que desees o dejar el que viene por defecto que se llama jade; lo mismo puedes hacer con los preprocesadores de css como SASS o LESS.

Los view engine permiten crear documentos HTML para las vistas de tu proyecto. Las vistas mezclan código estático HTML y código de programación dinámico, tales como atributos de determinados objetos de tu modelo. De esta forma, podrías tener una vista de un modelo tales como un objeto que representa una bicicleta y, luego, con el view engine, definir la vista, de acuerdo al objeto bicicleta que se utilice como parámetro de la generación de la vista.

Creamos nuestro primer proyecto:

```
express red-bicicletas --view=pug
```

Fíjate que ahora usamos el view engine <a href="https://github.com/pugjs/pug" target="_blank">Pug</a>.

Instalamos las dependencias con:
````
npm install
````

Ahora crearemos el archivo ‘.gitignore’ y dentro del archivo escribimos node_modules. Esa carpeta incluirá muchos archivos de las librerías que utilizaremos en nuestro proyecto. La excluimos porque npm trae el comando install, que permite instalar todas las dependencias de nuestro proyecto y eso
implica que se guardan los archivos de las mismas en la carpeta node_modules. Por lo tanto, no es necesario versionar node_modules ya que no aporta ningún valor y podría generar conflictos de versiones innecesarios.

Podemos iniciar nuestro proyecto con:

````
npm start
````

Puedes ver en la consola que el servidor está disponible y escuchando nuevas conexiones. Desde un browser si ingresamos a http://localhost:3000 podemos ver el mensaje de bienvenida de Express. A partir de ahora iremos creando nuestro modelo, siguiendo interfaces web (páginas HTML) y una API REST. Vamos a trabajar con una arquitectura MVC, Model View Controller.


Antes de comenzar a trabajar, instalaremos nodemon para agilizar las recargas de la página:

````
npm install nodemon --save-dev
````

Agregamos un comando para iniciar el proyecto usando nodemon. En el archivo ```package.json``` añadir:

````
"scripts": {
  "start": "node ./bin/www",
  "devstart" : "nodemon ./bin/www"
},
````

Ahora podemos iniciar el proyecto con el comando:

````
npm run devstart
````

  
En este momento podemos agregar algo de diseño, para este caso usaremos unos [themes](https://startbootstrap.com/) Bootstrap.

Para la parte de PUG podemos usar un [traductor](https://html-to-pug.com/).

