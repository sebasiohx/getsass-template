
  

# Arquitectura

  

La finalidad de este modelo es poder dividir el codigo en partes pequeñas para que sea mas facil mantener el codigo y reutilizarlo caso sea necesario.

 Se recomienda usar carpetas segun sea necesario, respetando la estructura original.

## Estructura de archivos

    |-components/
    |	|-_all.scss
    |	|-_button.scss *archivo ejemplo*
    |-layout/
    |	|-_all.scss	
    |	|-_header.scss *archivo ejemplo*
    |-pages/
    |	|-_all.scss	
    |	|-_home.scss *archivo ejemplo*
    |-utilities/
    |	|-_all.scss	
    |	|-_variables.scss
    |	|-_mixins.scss
    |	|-_fonts.scss
    |-style.scss *archivo principal*
    

## Reglas generales
**Components**: Archivo especifico de cada componente.
**Layout**: Partes del layout del sitio, ej: Header, Footer, Nav.
**Pages**: Archivo scss para modificaciones especificas de cada pagina.
**Utilities**: Carpeta para funciones, mixins, variables, etc.

## Componentes
Debemos pensar en las interfaces como un conjunto de componentes. Los componentes deben cumplir algunas reglas:

 - Cumple una sola funcion.
 - Es reutilizable en el proyecto.
 - Es independiente.

Ejemplo, un searchbar cumple la misma funcion da igual el lugar donde se ponga. El searchbar es un componente reutilizable, y es independiente.

  

## Estructura de un componente
Los componentes deben tener su propio archivo de css describiendo:

* El estilo del componente.

* Modificadores, estados y variantes.

* Si el componente tiene hijos, deben estilarse tambien.

Ejemplo:
 

    `.button {    
       &.active { 
         p { }
       }
     }`    

            


### Carpeta Layout
En esta carpeta se guardan los archivos que son responsables de las secciones especificas de nuestra aplicacion, y si es necesario hacer una moficacion en especifico de un componente debe hacerse aca.

### Carpeta Pages
Si tenemos un estilo muy especifico para una pagina en concreto, debemos hacerlo en este sitio. Por ejemplo, hay botones que se comportan de una manera solo en el home, en este caso agregamos el archivo _home.scss y modificamos el componente segun sea necesario.
  

### Carpeta Utilities
Por regla general, esta carpeta no deberia emitir ninguna linea de codigo si se compila por si sola.
Generalmente se declaran utilidades como las siguientes: 
  

*  `_variables.scss`

*  `_mixins.scss`

*  `_functions.scss`

*  `_placeholders.scss`

### Archivo principal

  

El archivo principal ( `style.scss`) es el unico archivo que no debe comenzar su nombre con underscore. Este archivo solo debe contener `@import` y comentarios.

Por conveniencia, el orden de imports deberia ser el siguiente:

1.  `utilities/`

1.  `layout/`

1.  `components/`

1.  `pages/`

Para mantener el codigo limpio debemos seguir los siguientes lineamientos:

* Un archivo por `@import`;

* Un  `@import` por linea;

* Una linea nueva entre imports de distintas carpetas;

* Omitir los underscore y tipos de archivo, ejemplo: 
 `@import 'utilities/all'`.

 Otra manera valida seria:
 
* Un `@import` por carpeta;

* Un line break despues del `@import`;

* Cada archivo en su propia linea;

* Una linea nueva despues del `@import`;
* Omitir los underscore y tipos de archivo, ejemplo: 
 `@import 'utilities/all'`.
