# 3.7 React Hooks

## Introducción

En esta sesión vamos a aprender una nueva manera de manipular el estado de nuestra aplicación, los React Hooks. 

Hasta ahora hemos visto que, para manejar nuestro `state` necesitamos trabajar en un componente principal, App.js, que controla de manera global los datos que cambian en nuestra apliacación y para ello necesitamos conocer los componentes de clase. Esta manera de manejar el `state` hace que nuestro componente principal sea el que tiene "el mando" de nuestra aplicación, dejando al resto de componentes a las órdenes de lo que suceda en este componente. Es decir, el resto de componentes no manejaban estado. Con los React Hooks esto va a cambiar.

Vamos a hacer que nuestros componentes funcionales también manejen el estado.

## ¿Para qué sirve lo que vamos a ver en esta sesión?

Ya sabemos lo que es el estado de nuestra aplicación y cómo lo hemos manejado hasta ahora a través de componentes de clase. A medida que las aplicaciones crecían y se volvían más grandes los componentes de clase se volvían más complejos por eso a partir de la versión 16.8 de React surgió una nueva manera de manipular el estado a través de componentes funcionales, evitando así todo el "engorro" de tener que escribir un componente de clase cada vez que necesitaba manejar el estado de una aplicación. En el mundo React actualmente conviven las dos maneras de trabajar, ya que los React Hooks son un concepto muy nuevo y aún no están completamente extendidos.
Antes de continuar, debes saber que los Hooks son:

 - Completamente opcionales. Es necesario que sepas que existen pero su uso no es obligatorio.
 - 100% compatibles con versiones anteriores de React. 
 - Por el momento no hay planes para eliminar el modelo de clases de React. 
 
Los Hooks no reemplazan tu conocimiento de los conceptos de React. Todo lo contrario, los Hooks complementan y amplian estos conceptos que ya conoces: props, estado... y otros que veremos más adelante. 



