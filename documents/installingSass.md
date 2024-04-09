# Compilando **SASS**

En esta lección one hundred fifty nine (159) se instalaran las dependencias de SASS, porque esta se va a encargar de identificar el código y de compilarlo; a su vez nos informará en caso de que se tenga algún error, y de inmediato advierte. Por decir algo, tiene toda la base del conocimiento para instalar dependencias.

Ahora, como ya tenemos instalado npm solamente escribimos en una nueva terminal (ctrl + ñ) install npm y posteriormente el nombre de la dependencia, en este caso SASS. ÇDesde el inicio el paquete se llamaba SASS, este era una **[API](https://www.redhat.com/es/topics/api/what-are-application-programming-interfaces)** escrita en **Js**. Después fue renombrada a NOdSass porque crearon una llamada [dart-sass](https://sass-lang.com/dart-sass/).

Con el anterior comando, se instalaron las dependencias y sí se abre el archivo package.json se observa que aparece la dependencia de sass, para mí caso se encuentra en la línea quince (15); Analizando, en este archivo existen dos (2) tipos de dependencia unas son las dependencias normales como la que aparece ne la línea quince de mi archivo y las otras son las dependencias de desarrollo.

Las que son dependencias, una vez que realicemos un deployment a un servidor que soporta notjs las va a instalar; pero, las que son de desarrollo no; aunque las tendremos localmente mientras se va creando el proyecto. En el caso mío esta dependencies de la línea quince (15) sí va a ser una dependencia de desarrollo, por lo tanto lo que se debe de hacer es, eliminar ese código e instalarlo como dependencia de desarrollo.

Teniendo en cuenta lo anterior, en una terminal se escribe `npm install sass --save-dev` y de esta forma la va a colocar como una dependencia de desarrollo. En el caso del proyecto que se inicia en este tutorial todas van a ser dependencias de desarrollo porque se debe de mejorar el código de JavaScript y al compilar las hojas de estilos, de sass, se va a aligerar todas las imagenes; pero todo esto se hace en desarrollo.

Al final se debe de tener un proyecto compilado y listo; Ahora este archivo package.json va a mantener la referencia de la dependencia y tambien de su versión; Notese que cuando se instaló esta dependencia, se crearon otros archivos, una carpeta llamada `node_modules` en esta es donde se van a descargar esas dependencias.
