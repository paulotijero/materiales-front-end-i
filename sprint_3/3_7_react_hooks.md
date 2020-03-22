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
 
Los Hooks no reemplazan tu conocimiento de los conceptos de React. Todo lo contrario, complementan y amplian estos conceptos que ya conoces: props, estado,lifting... y otros que veremos más adelante. Además seguiremos manejando la estructura que ya conocemos con un componente principal que "dirija" nuestra aplicación, la única diferencia es que ya podríamos usarlo como componente funcional y seguir controlando el estado.

## Qué son los hooks

La palabra Hook se traduce como Gancho en español, y la razón de este nombre, es que un Hook en React te permite "colgarte" del estado y los métodos del ciclo de vida de un componente, desde un componente funcional.

Vamos a recordar cómo escribíamos hasta ahora un componente de clase con estado, por ejemplo App.js. Imagina que desde App.js se llama a otro componene RandomInteger que tiene un botón para generar un número aleatorio y pintarlo. La estructura de App.js sería la siguiente:

**App.js como componente de clase**
``````
class App extends React.Component {
  constructor(props) {
    super(props);
    this.handleRandomInteger = this.handleRandomInteger.bind(this);
    this.getRandomInteger = this.getRandomInteger.bind(this);
    this.state = {
      number : 0
    }
  }

  getRandomInteger() {
    return Math.floor(Math.random() * 100)
  }

  handleRandomInteger() {
    this.setState((prevState) => {
      return prevState.number = this.getRandomInteger();
    })
  }
  
  render() {
    return (
      <div className="App">
        <RandomInteger getRandom={this.handleRandomInteger} randomNumber={this.state.number}/>
      </div>
    );
  }
}
``````

Bien, hasta aquí es terreno conocido, y ahora ¿cómo podríamos pasar App.js a componente funcional utilizando hooks? La respuesta es sencilla por medio de nuestro nuevo mejor amigo `useState`. Echa un vistazo a cómo quedaría App.js con hooks:

**App.js como componente funcional con el hook useState**
``````
const App = function() {
  const [number,setNumber] = useState(0);
  const generateRandomInteger = () => Math.floor(Math.random() * 100);

  const handleRandomInteger = () => {
    setNumber(generateRandomInteger())
  }

  return (
    <div className="App">
      <RandomInteger getRandom={handleRandomInteger} randomNumber={number}/>
    </div>
  );
}
``````
Como puedes ver, y aunque explicaremos más adelante este primer hook, `useState`, el tamaño y la complejidad del componente se ha reducido. Además se ha eliminado la posible confusión que generan el uso de componentes de clase.

## Manejando el estado con hooks. useState()

Existen dos tipos de Hooks en React, los hooks de la propia librería, que vienen predefinidos y los hooks personalizados (que no veremos de momento).

Uno de los hooks predefinidos más populares y útiles es `useState`, por cierto, la convención para nombrar un Hook es usar la palabra use, seguida de otra palabra que lo describa, como en este caso 'state' porque a través de este hook podemos manejar el estado del componente.

Para usar un Hook primero necesitamos un componente funcional, ojo, los hooks sólo funcionan con componentes funcionales y no con componentes clase:

**App.js**
````````
import React from 'react';

function App(){
  return(
        <div>{name}</div>
    )
}
````````

`{name}` será una propiedad de nuestro componente funcional que aún no hemos definido, pero que tiene la particularidad de poder ser modificado, por lo que es parte del estado del componente, hasta antes de los hooks eso significaba que teníamos que migrar nuestro componente funcional a uno de clase, pero ya no más.

Para definir una propiedad del estado del componente con hooks usamos algo así:

``````````
const [name, setName] = useState('Elena');
``````````


