
# Compilando **SASS** con **npm**

En esta clase one hundred sixty (160) tocaremos el tema de como algunas dependencias tienen un binario que podemos ejecutar desde npm; abrimos node_modules y podemos ver esa carpeta llamada punto bin (.bin) y dentro de esta tenemos un archivo llamado sass, sass.cd y sass.ps1 (para mi caso).

Inicialmente. lo que vamos a hacer es crear una carpeta y la llamaremos **src** y dentro de esta también creamos otra carpeta que la llamaremos como **scss** y vamos a colocar el código de sass; finalmente vamos a un archivo dentro de esta última carpeta y que la llamaremos **app.scss**; este va a ser nuestro archivo original de **SASS**.

Sabemos que, existen dependencias, Entonces, vamos a buscar en el área de extensiones una que se llama live sass compiler y nos sirve para compilar esa no requiere configuración prácticamente sino que es un poco limitada porque solamente compila hojas de estilo; Y como vamos a ver **gulp** siendo esta mucho más avanzado que lo que nos ofrece esta extensión.

Ahora, vamos utilizar nuestro archivo app.scss y vamos a crear una variable; recordemos que esta en sass se utiliza el signo pesos ($) seguido de un nombre; para nuestro caso, vamos llamarla por ejemplo, rojo; también recordemos que las convenciones nos dicen que deben ser acordes a lo que estamos trabajando. NO debe contener caracteres extraños, sin espacios, en especial que siga las [reglas](https://www.ibm.com/docs/es/spss-statistics/saas?topic=view-variable-names) de una variable en programación.

Continuando con nuestro tema, vamos a nombrar nuestra variable rojo seguido de dos puntos y escribimos red; Es menester recordar que nuestro editor de código nos ayuda con el autocompletado en muchos casos; vamos a colocarle unos atributos al body abrimos llaves { y dentro de estas laves vamos a escribir background-color:} y llamaremos a nuestra variable $rojo.

Podemos ver que a diferencia de los custom properties, eso siempre se registran en el root y dentro de las llaves {escribimos doble guión, por ejemplo rojo} y lo utilizabamos con un var(--rojo) esta es una sintaxis un poco diferente. Veamos como queda el código.

```css
:root {

}
var(--rojo)
```

En el caso de sass las definimos donde nosotros así lo requiramos y se utilizan con la misma sintaxis. No tenemos que colocarle `var` ni nada de eso. De inmediato sass ya sabe que es una variable; bién como ya tenemos una hoja de estilos y no podemos abrir nuestro archivo `index.html` ni agregarla, no podemos colocarle anted antes de la etiqueta final `</head>` un `<link rel="stylesheet" href="src/scss/app.scss>`.

Esto debido a que, sí le damos abri podemos ver que no le aplica los cambios de color de fondo, para nuestro caso rojo. Y si le damos inspeccionar podemos ver que se encuentra agregado esa línea y tampoco nos marca un error; El navegador dice bueno, ya se encuentra esta extensión por lo que la va a ignorar. Es aquí, en donde tenemos que compilarlo y esto se hace con el `package.json`.

Recordemos que, tenemos un archivo `.bin` con una sección que dice scripts; o sea que, el archivo package.json puede ejecutar esos binarios y también puede almacenar las dependencias; en esa línea del `"script": {"test": "echo\"Error: no test specified\" && exist 1"},` y en donde dice "test" le podemos escribir sass y por lo tanto ya tenemos un script llamado sass; ahora, en la parte "echo\"Error: no test specified\" && exist 1" vamos reemplazarlo para cuando mandemos a llamar o ejecutarlo; entonces escribimos sass; este va a ser el contenido que tenemos en los binarios.

Veamos el archivo node_modules y ese archivo sass es el mismo que tenemos en el script el que acabamos de crear; la función que va a realizar es buscar la carpeta de binarios y detecta que sí hay un archivo llamado sass y nos dice bueno, lo voy a ejecutar. como recomendación, no le podemos colocar cualquier nombre o cualquier cosa, debido a que, no todas las dependencias tienen binarios; pero, en este caso se encuentra sass.

Seguidamente, vamos a llamar lass carpetas que contienen el archivo sass; entonces le colocamos la ubicacion de la hoja de estilos de sass qe podemos ver an la carpeta src y después scss; le escribimos "sass src/scss" no olvidemos que, lo compila pero, lo tiene que guardar en algún lugar; porque, tenemos el archivo app con la extensión punt scss; entonces, podemos colocar en la misma línea los do puntos y decirle compilalo en una carpeta en específico y lo vamos a colocar aquí mismo. Por lo tanto lo vamos a colocar en una carpeta llamada "build/css"; nuestras líneas quedan así:

```json
"scripts": {
    "sass": "sass src/scss:build/css"
}
```

Este anterior código lo que hace es abrir el binario de sass que tiene toda la clase de conocimiento; pués conoce que son las variables, que es los mixin y lo va a leer en la carpeta "src/scss" y por lo tanto lo almacena la versión una vez compilada en la otra carpeta "build/css"; pero, vamos a ver si es cierto toda esta teoría. Nos trasladamos a nuestra terminal y la forma en que mandamos a llamar los scripts; escribimos "npm run" seguido del nombre del script en este caso sass; y nuestra linea queda así: `nmp run sass`.

Entonces, esto lo que hace es ir la línea de nuestro script y va a ejecutar las tareas que hayamos definido; para nuestro caso "build/css". O sea abrir el binario de sass identificar la hoja de estilos y compilarla en la carpeta que acabamos de nombrar. Podemos ver en nuestra terminal que, la línea se ejecuta normalmente `sass src/scss:guild/css` y si observamos nos ha creado la carpeta build css y dentro de esta ha creado una carpeta `app.css`.

Es de entender que, esta acción no se va a ver reflejado nada en nuestro navegador porque en nuestro archivo `index.html` seguimos apuntando a la hoja de estilos; pero, si en ese archivo html es escribir o colocar la carpeta de `build/css/app.css` y si guardamos cambios vemos que efectivamente aparece nuestra página en color rojo. La siguiente es la línea de código en el archivo index.html.

```html
<link rel="stylesheet" href="build/css/app.css">
```

Con base en lo anterior, podemos utilizar este package punto json `package.json` para compilar nuestras hojas de estilos de sass; ahora, supongamos que, abrimos otro archivo y en lugar de que sea de color rojo de fondo le coloco blue; guardamos cambios y vemos los cambios en nuestra página web. Pudimos observar que, al momento de abrir nuestra página no sucedió nada; porque debemos de compilar nuevamente en la terminal el `npm run sass` y Efectivamente, nuestro cambio surtió efecto.

Existe algo llamado watch; básicamente este se la pasa viendo o escuchando por los cambios que suceden en un archivo y si sucede una acción; por lo tanto, en este archivo `package.json` y le podemos colocar después de que habilita y watch con doble guión; de esta forma va a estar escuchando por los cambios que pasen en este archivo `src/scss` y va a estar ejecutando una y otra vez esas tareas; entonces, de nuevo, si le colocamos aquí en nuestra terminal `npm run sass` y le damos enter; observemos que cambios tiene esta siguiente línea.

```json
"scripts": {
    "sass": "sass --watch src/scss:build/css"
}
```

Pudimos observar que, en nuestra terminal nos aparece un mensaje "Sass is watching for changes. Press Ctrl-C to stop"; y nos dice que sass etá observando o está escuchando por cambios y que presionemos las teclas ctrl + C; Pero si yo realizo cambios aquí en nuestro archivo `apps.scss`, lo regreso a rojo (red); guardo cambios miremos que sucede en nuestra terminal.

Nuevamente, en nuestra terminal aparece "Compiled src\scss\app.scss to build\css\app.css." en color verde y con la fecha y hora actual. Con esto observamos que, se va a ejecutar todo el tiempo mientras haya cambios en los archivos **SASS**; ahora, una vez que, finaliza de trabajar, una vez que finaliza el proyecto, presionamos la tecla "control c" Y no importa si es Windows, Mac o Linux, presionas "control c" y esto va a detener ese watch.

Esta forma viene a ser la forma más fácil de comenzar a trabajar con **sass**, más adelante vemos a ver el tema de "gulp" nos ofrece más opciones; siendo esta una excelente herramienta porque tiene muchas dependencias y podemos realizar muchas cosas; así que, en la próxima clase one hundred sixty one (161) llamada instalando gulp y creando un gulpfile.
