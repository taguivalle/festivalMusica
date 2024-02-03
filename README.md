# Proyecto Festival de Música

Inicialmente, como es el común en esta clase one hundred fifty eight (158) llamada comenzando el proyecto llamado **Festival de Música** tenemos a su vez unos archivos entregados por el señor instructor **Juan Pablo De la torre Valdez**; en estos tenemos unas carpetas llamadas img, video y un index; no es mayor cosa; pero, es la base para el inicio de nuestro proyecto.

Ahora para iniciar a trabajar con [GULP](https://medium.com/@leoalipazaga/incluye-gulp-en-tus-proyectos-y-notar%C3%A1s-la-diferencia-51028fa49a22) y SAhttps://sass-lang.com/guide/SS; de otra parte, tenemos que crear un archivo llamado Package punto JSon (`.json`). Para esto, vamos a abrir una terminal, podemos dirigirnos hasta la ventana de la parte superior de nuestro editor de texto llamada Terminal; o si se prefiere un atajo se oprime la tecla Ctrl más la letra "ñ".

Al encontrarnos dentro de la terminal debemos escribir npm init; seguidamente, oprimimos la tecla enter, nos va a realizar un a serie de preguntas; pero solamente oprimimos nuevamente la tecla enter. Vamos a escribir al lado del título descripcion así: Proyecto con Gulp, SASS y HTML y damos enter. Además, vamos a colocar el proyecto en un repositorio; podemos colocar el url en el título keywords escribimos SASS, Gulp y enter; en el autor colocamos nuestros nombres; sucecivamente enter.

Y como todo ha salido bién; observamos que, en la parte derecha de nuestra carpeta se crea el archivo `package.json`; este archivo nos sirve para ejecutar comandos dentro de npm; pero, también para instalar lo que se conoce como **dependencias** de npm. Siendo esta un librería muy grande de [dependencias](https://platzi.com/discusiones/1763-npm/138895-cual-es-la-diferencia-entre-libreria-modulo-paquete-dependencia/); Notemos que, no vamos a escribir todo el código nosotros mismos; en muchas ocaciones vamos a descargar alguna de las librería que estemos necesitando. 

Continuando con el hilo de la discución, este archivo `package.json` nos sirve para tener una serie de scripts, acciones que se van a ejecutar y también el nombre de la dependencia; además, su versión es muy útil en un equipo de trabajo; de esta forma se puede compartir un package punto json y todas las personas involucradas en ese equipo de trabajo van a saber que dependencias se utilizan como la misma versión.

## Instalación de dependencias de **SASS**

Es necesario descargar la dependencia; porque, essta se va a encargar de identificar el código, compilarlo y También va a decirnos en caso de que tengamos un error; "sabes que eso es un error, no puedo compilarlo, etc." Por decir algo, tiene toda la base del conocimiento para instalar dependencias. Ahora que, ya tenemos instalado npm, posteriormente nos sale la siguiente línea: "Run npm instal -g npm to update!" (sin las comillas) y procedemos a escribir `npm install` y el nombre de la dependencia en este caso es **SASS**.

Desde el inicio, el paquete se llamaba sass, esta era una API escrita en [Nordjs](https://github.com/Nordjs), después fue renombrada a [Nodsass](https://www.npmjs.com/package/node-sass); debido a que crearon una llamada dart-sass; entonces, la de [dart-sass](https://www.npmjs.com/package/dart-sass) tiene más performance que la de nord y recientemente decidieron de implimentar esta de dart-sass. POr lo tanto vamos a instalarla como sass.

Al darle enter, esto nos instala un dependencia; en este momento es prudente mencionar que, se han instalado para mi caso diez y siete (17) dependencias y que una ha sido auditada para un total de diez y ocho (18); ahora, si cerramos este archivo y lo volvemos a abrir, vemos que en la parte inferior tenemos las dependencias de sass y para este caso tenemos algo así: "^1.70.0".

Análogamente, tenemos dos tipos de dependencias en este archivo `package.json`; una de ellas son las dependencias normales como las que acabamos de ver al momento de la apertura de este archivo y las otra es, las dependencias de desarrollo; es decir una vez que realicemos un deployment a un servidor que soporta NodeJs, las va a instalar esas dependencias. O se a que, las que son a desarrollo no lo va a hacer, pero, las vamos a poder tener localmente mientras vamos creando un poryecto.

```json
  "license": "ISC",
  "dependencies": {
    "sass": "^1.70.0"
  }
  ```

  En nuestro caso va a ser una dependencia de desarrollo; por lo tanto vamos con el anterior código es eliminar las dos últimas líneas e instalar como dependencia de desarrollo y escribimos en nuestra terminal "npm install sass --save-dev" (sin las comillas) y de esta forma nos la va a colocar como una dependencia de desarrollo. En el caso de nuestro proyecto que vamos a realizar, todas van a ser dependencia de desarrollo porque vamos a mejorar nuestro código de [JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript) a su vez, vamos a compilar las hojas de estilos de sass; también vamos a mejorar las imágenes; pero, todo esto lo vamos a hace den desarrollo. Debido a que, la idea original es subir un poryecto compilado y listo.

  De acuerdo con nuestro código, que más adelante lo escribiremos en este documento este va a ser una dependencia de desarrollo y de la que ya tenemos instalado **SASS**; ahora, el package.json va a mantener la referencia de la dependencia y también de su versión "^1.70.0"; pero notemos que cuando instalamos esta dependencia nos ha creado otros archivos; primero vamos a escribir las dependencias del código de nuestro archivo package.json.

  ```json
  "author": "Hector Gustavo Vallejo Espinosa",
  "license": "ISC",
  "devDependencies": {
    "sass": "^1.70.0"
  }
  ```

Como venimos diciendo que, los nuevos archivos; tenemos una carpeta llamada node_modules, en esta es donde se van a descargar esas dependencias; como la de nuestro archivo `package.json` que es llamada sass; seguidamente, vemos otra carpet llamada package-lock.json; procedamos a abrirlo. Podemos obervar que tiene al rededor de doscientas (200) líneas de código; es natural que esta clase de archivo tenga mucha información; pero en realidad a nosotros por el momento nos nos interesa nada esta situación; lo único es que contiene las dependencias de nuestro archivo package.json; que esta estructura nos permite trabajar con mayor libertad sobre nuestro proyecto.

Como recomendación especial este archivo `package-lock-json` debe de permanecer intacto, así com está. De otra parte tenemos la carpeta node_modules que si la abrimos observamos que, tiene también una gran cantidad de carpetas; más hacia abajo tenemos nuestra carpeta SASS en un color diferente; pero, lo importante es que aparece un archivo  `sass.dart.js`; siendo la versión más nueva de **SASS**.

Otra carpeta que, también llama la atención es `.bin`; esto datos que se encuentran son archivo binarios y son scripts que podemos ejecutar; manifestando que, más adelante estaremos tocando el tema de cómo ejecutar estos scripts para poder compilar una hoja estilos con npm. Otro aspecto a tener en cuenta es que , esta carpeta de node_modulos a medida que vayamos trabajando sobre el código esta va creciendo paulatinamente. Aunque esta es una carpeta que al momento de terminar le proyecto la podemos eliminar; porque esta se puede recuperar con el archivo `package.json`. El único que no se debe de eliminar ese mismo `package.json` debido a que, este es el que tiene las dependencias.

Entonces, vamos a suponer que hemos eliminado las dependencias y dentro de la terminal vamos a escribir la siguiente línea: `npm install` o el comando más corto`npm i` y este lo que va a hacer es abrir nuestro archivo `package.json` busca las dependencias y nos recupera la carpeta de **node_modules**; como información especial, esta es una carpeta que puede llegar a pesar de cuatrocientos (400) a quinientos (500) megas en algunos proyectos. Y si se prefiere esta se puede eliminar para solucionar unos problemas de espacio en la computadora.

Además, en un equipo de trabajo por ejemplo, se encuentran trabajando todos las personas involucradas en el proyecto y si se comparte un proyecto de **npm** este es muy pesado; por lo que, se puede eliminar la carpeta **node_modules** y ellos los pueden recuperar escribiendo `npm install` o el comando más corto`npm i`. Para finalizar, en la siguiente clase one hundred fifty nine 159 vamos a tratar el tema de como ejecutar el archivo binario para poder compilar nuestras hojas de estilos de **SASS**.
